# Starting a stream to a bot<a name="start-stream-conversation"></a>

You use the [StartConversation](API_runtime_StartConversation.md) operation to start a stream between the user and the Amazon Lex bot in your application\. The `POST` request from the application establishes a connection between your application and the Amazon Lex bot\. This enables your application and the bot to start exchanging information with each other through events\.

The first event your application must send to the Amazon Lex bot is a [ConfigurationEvent](API_runtime_ConfigurationEvent.md)\. This event includes information such as the response type format\. The following are the parameters that you can use in a configuration event:
+ **responseContentType** – Determines whether the bot responds to user input with text or speech\.
+ **sessionState** – Information relating to the streaming session with the bot such as predetermined intent or dialog state\.
+ **welcomeMessages** – Specifies the welcome messages that play for the user at the beginning of their conversation with a bot\. These messages play before the user provides any input\. To enable a welcome message, you must also specify values for the `sessionState` and `dialogAction` parameters\. 
+ **disablePlayback** – Determines whether the bot should wait for a cue from the client before it starts listening for caller input\. By default, playback is enabled, so the value of this field is `false`\.
+ **requestAttributes** – Provides additional information for the request\.

For information about how to specify values for the preceding parameters, see the [ConfigurationEvent](API_runtime_ConfigurationEvent.md) data type of the [StartConversation](API_runtime_StartConversation.md) operation\.

Each stream between a bot and your application can only have one configuration event\. After your application has sent a configuration event, the bot can take additional communication from your application\.

If you've specified that your user is using audio to communicate with the Amazon Lex bot, your application can send the following events to the bot during the course of that conversation:
+ [AudioInputEvent](API_runtime_AudioInputEvent.md) – Contains an audio chunk that has maximum size of 320 bytes\. Your application must use multiple audio input events to send a message from the server to the bot\. Every audio input event in the stream must have the same audio format\.
+ [DTMFInputEvent](API_runtime_DTMFInputEvent.md) – Sends a DTMF input to the bot\. Each DTMF key press corresponds to a single event\.
+ [PlaybackCompletionEvent](API_runtime_PlaybackCompletionEvent.md) – Informs the server that a response from the user's input has been played back to them\. You must use a playback completion event if you're sending an audio response to the user\. If `disablePlayback` of your configuration event is `true`, you can't use this feature\.
+ [DisconnectionEvent](API_runtime_DisconnectionEvent.md) – Informs the bot that the user has disconnected from the conversation\.

If you've specified that the user is using text to communicate with the bot, your application can send the following events to the bot during the course of that conversation:
+ [TextInputEvent](API_runtime_TextInputEvent.md) – Text that is sent from your application to the bot\. You can have up to 512 characters in a text input event\.
+ [PlaybackCompletionEvent](API_runtime_PlaybackCompletionEvent.md) – Informs the server that a response from the user's input has been played back to them\. You must use this event if you're playing audio back to the user\. If `disablePlayback` of your configuration event is `true`, you can't use this feature\.
+ [DisconnectionEvent](API_runtime_DisconnectionEvent.md) – Informs the bot that the user has disconnected from the conversation\.

You must encode every event that you send to an Amazon Lex bot in the correct format\. For more information, see [Event stream encoding](event-stream-encoding.md)\.

Every event has an event ID\. To help troubleshoot any issues that might occur in the stream, assign a unique event ID to each input event\. This enables you to troubleshoot any processing failures with the bot\.

Amazon Lex also uses timestamps for each event\. You can use these timestamps in addition to the event ID to help troubleshoot any network transmission issues\.

During the course of the conversation between the user and the Amazon Lex bot, the bot can send the following outbound events in response to the user:
+ [IntentResultEvent](API_runtime_IntentResultEvent.md) – Contains the intent that Amazon Lex determined from the user utterance\. Each internal result event includes:
  + **InputMode** – The type of user utterance\. Valid values are `Speech`, `DTMF`, or `Text`\.
  + **Interpretations** – Interpretations that Amazon Lex determines from the user utterance\.
  + **RequestAttributes** – If you haven't modified the request attributes by using a lambda function, these are the same attributes that have been passed in at the start of the conversation\.
  + **SessionId** – Session identifier used for the conversation\.
  + **SessionState** – The state of the user's session with Amazon Lex\.
+ [TranscriptEvent](API_runtime_TranscriptEvent.md) – If the user provides an input to your application, this event contains the transcript of the user's utterance to the bot\. Your application does not receive a `TranscriptEvent` when there is no user input\.

  The value of the transcript event sent to your application depends on whether you've specified audio \(speech and DMTF\) or text as a conversation mode:
  + Transcript of speech input – If the user is speaking with the bot, the transcript event is the transcription of the user's audio\. It's a transcript of all the speech from the time the user begins speaking to the time they end speaking\.
  + Transcript of DTMF input – If the user is typing on a keypad, the transcript event contains all the digits the user pressed in their input\.
  + Transcript of text input – If the user is providing text input, the transcript event contains all of the text in the user's input\.
+ [TextResponseEvent](API_runtime_TextResponseEvent.md) – Contains the bot response in text format\. A text response is returned by default\. If you've configured Amazon Lex to return an audio response, this text is used to generate an audio response\. Each text response event contains an array of message objects that the bot returns to the user\.
+ [AudioResponseEvent](API_runtime_AudioResponseEvent.md) – Contains the audio response synthesized from the text generated in the `TextResponseEvent`\. To receive audio response events, you must configure Amazon Lex to provide an audio response\. All audio response events have the same audio format\. Each event contains audio chunks that have a maximum size of 100 bytes\. Amazon Lex sends an empty audio chunk with the `bytes` field set to `null` to indicate that the end of the audio response event to your application\.
+ [PlaybackInterruptionEvent](API_runtime_PlaybackInterruptionEvent.md) – When a user interrupts a response that the bot has sent to your application, Amazon Lex triggers this event to stop the playback of the response\.
+ [HeartbeatEvent](API_runtime_HeartbeatEvent.md) – Amazon Lex sends this event back periodically to keep the connection between your application and the bot from timing out\.

## Time sequence of events for an audio conversation<a name="audio-conversation-sequence"></a>

The following diagrams show a streaming audio conversation between a user and an Amazon Lex bot\. The application continuously streams audio to the bot, and the bot looks for user input from the audio\. In this example, both the user and the bot are using speech to communicate\. Each diagram corresponds to a user utterance and the response of the bot to that utterance\.

The following diagram shows the beginning of a conversation between the application and the bot\. The stream begins at time zero \(t0\)\. 

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/lexv2/latest/dg/images/Streaming-Page-1.png)

The following list describes the events of the preceding diagram\.
+ t0: The application sends a configuration event to the bot to start the stream\.
+ t1: The application streams audio data\. This data is broken up into a series of input events from the application\.
+ t2: For *user utterance 1*, the bot detects an audio input event when the user begins speaking\.
+ t2: While the user is speaking, the bot sends a heartbeat event to maintain the connection\. It sends these events intermittently to make sure the connection doesn't time out\.
+ t3: The bot detects the end of the user's utterance\.
+ t4: The bot sends back a transcript event that contains a transcript of the user's speech to the application\. This is the beginning of *Bot response to user utterance 1*\.
+ t5: The bot sends an intent result event to indicate the action that the user wants to perform\.
+ t6: The bot begins providing its response as text in a text response event\.
+ t7: The bot sends a series of audio response events to the application to play for the user\.
+ t8: The bot sends another heartbeat event to intermittently maintain the connection\.

The following diagram is a continuation of the previous diagram\. It shows the application sending a playback completion event to the bot to indicate that it has stopped playing the audio response for the user\. The application plays back *Bot response to user utterance 1* to the user\. The user responds to *Bot response to user utterance 1* with *User utterance 2*\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/lexv2/latest/dg/images/Streaming-Page-2.png)

The following list describes the events of the preceding diagram:
+ t10: The application sends a playback completion event to indicate that it has finished playing the bot's message to the user\.
+ t11: The application sends the user response back to the bot as *User utterance 2*\.
+ t12: For *Bot response to user utterance 2*, the bot waits for the user to stop speaking and then begins to provide an audio response\.
+ t13: While the bot sends *Bot response to user utterance 2* to the application, the bot detects the start of *User utterance 3*\. The bot stops *Bot response to user utterance 2* and sends a playback interruption event\.
+ t14: The bot sends a playback interruption event to the application to signal that the user has interrupted the prompt\.

The following diagram shows the *Bot response to user utterance 3*, and that the conversation continues after the bot responds to the user utterance\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/lexv2/latest/dg/images/Streaming-Page-3.png)