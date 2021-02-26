# Streaming to an Amazon Lex bot<a name="streaming"></a>

You can use the Amazon Lex streaming API to start a bidirectional stream between an Amazon Lex bot and your application\. Starting a stream enables the bot to manage the conversation between the bot and the user\. The bot responds to user input without you writing code to handle responses from the user\. The bot can:
+ Handle interruptions from the user while it's playing a prompt\. For more information, see [Enabling your bot to be interrupted by your user](interrupt-bot.md)\.
+ Wait for the user to provide input\. For example, the bot can wait for the user to gather credit card information\. For more information, see [Enabling the bot to wait for the user to provide additional information](wait-and-continue.md)\.
+ Take both dual\-tone multiple\-frequency \(DTMF\) and audio input in the same stream\.
+ Handle pauses in user input better than if you were managing the conversation from your application\.

Not only does the Amazon Lex bot respond to data sent from your application, but it also sends information about the state of the conversation to your application\. You can use this information to change how your application responds to customers\.

The Amazon Lex bot also monitors the connection between the bot and your application\. It can determine if the connection has timed out\.

To use the API to start a stream to an Amazon Lex bot, see [Starting a stream to a bot](start-stream-conversation.md)\.

When you start streaming to an Amazon Lex bot from your application, you can configure the bot to accept either audio input or text input from the user\. You can also choose whether the user receives audio or text in response to their input\.

If you've configured the Amazon Lex bot to accept audio input from the user, it can't take text input\. If you've configured the bot to accept text input, the user can only use written text to communicate with it\.

When an Amazon Lex bot takes a streaming audio input, the bot determines when a user begins speaking and when they stop speaking\. It handles any pauses or any interruptions from the user\. It can also take both DTMF \(dual\-tone multi\-frequency\) input and speech input in the same stream\. This enables the user to interact with the bot more naturally\. You can present users with welcome messages and prompts\. You can also enable users to interrupt those messages and prompts\.

When you start a bidirectional stream, Amazon Lex uses the [HTTP/2 protocol](https://http2.github.io/)\. Your application and the bot exchange data in a single stream as a series of *events*\. An event can be one of the following:
+ Text, audio, or DTMF input from the user\.
+ Signals from the application to the Amazon Lex bot\. These include an indication that audio playback of a message has been completed, or that the user has disconnected from the session\.

 For more information about events, see [Starting a stream to a bot](start-stream-conversation.md)\. For information about how to encode events, see [Event stream encoding](event-stream-encoding.md)\.

**Topics**
+ [Starting a stream to a bot](start-stream-conversation.md)
+ [Event stream encoding](event-stream-encoding.md)