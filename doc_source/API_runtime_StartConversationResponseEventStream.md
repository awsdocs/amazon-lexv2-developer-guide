# StartConversationResponseEventStream<a name="API_runtime_StartConversationResponseEventStream"></a>

Represents a stream of events between Amazon Lex and your application\.

## Contents<a name="API_runtime_StartConversationResponseEventStream_Contents"></a>

 **AccessDeniedException**   <a name="lexv2-Type-runtime_StartConversationResponseEventStream-AccessDeniedException"></a>
Exception thrown when the credentials passed with the request are invalid or expired\. Also thrown when the credentials in the request do not have permission to access the `StartConversation` operation\.  
Type: Exception  
Required: No

 **AudioResponseEvent**   <a name="lexv2-Type-runtime_StartConversationResponseEventStream-AudioResponseEvent"></a>
An event sent from Amazon Lex to your client application containing audio to play to the user\.   
Type: [AudioResponseEvent](API_runtime_AudioResponseEvent.md) object  
Required: No

 **BadGatewayException**   <a name="lexv2-Type-runtime_StartConversationResponseEventStream-BadGatewayException"></a>
  
Type: Exception  
Required: No

 **ConflictException**   <a name="lexv2-Type-runtime_StartConversationResponseEventStream-ConflictException"></a>
Exception thrown when two clients are using the same AWS account, Amazon Lex bot, and session ID\.  
Type: Exception  
Required: No

 **DependencyFailedException**   <a name="lexv2-Type-runtime_StartConversationResponseEventStream-DependencyFailedException"></a>
  
Type: Exception  
Required: No

 **HeartbeatEvent**   <a name="lexv2-Type-runtime_StartConversationResponseEventStream-HeartbeatEvent"></a>
Event that Amazon Lex sends to indicate that the stream is still open between the client application and Amazon Lex   
Type: [HeartbeatEvent](API_runtime_HeartbeatEvent.md) object  
Required: No

 **IntentResultEvent**   <a name="lexv2-Type-runtime_StartConversationResponseEventStream-IntentResultEvent"></a>
Event sent from Amazon Lex to the client application containing the current state of the conversation between the user and Amazon Lex\.  
Type: [IntentResultEvent](API_runtime_IntentResultEvent.md) object  
Required: No

 **InternalServerException**   <a name="lexv2-Type-runtime_StartConversationResponseEventStream-InternalServerException"></a>
An error occurred with Amazon Lex\.  
Type: Exception  
Required: No

 **PlaybackInterruptionEvent**   <a name="lexv2-Type-runtime_StartConversationResponseEventStream-PlaybackInterruptionEvent"></a>
Event sent from Amazon Lex to indicate to the client application should stop playback of audio\. For example, if the client is playing a prompt that asks for the user's telephone number, the user might start to say the phone number before the prompt is complete\. Amazon Lex sends this event to the client application to indicate that the user is responding and that Amazon Lex is processing their input\.  
Type: [PlaybackInterruptionEvent](API_runtime_PlaybackInterruptionEvent.md) object  
Required: No

 **ResourceNotFoundException**   <a name="lexv2-Type-runtime_StartConversationResponseEventStream-ResourceNotFoundException"></a>
Exception thrown if one of the input parameters points to a resource that does not exist\. For example, if the bot ID specified does not exist\.  
Type: Exception  
Required: No

 **TextResponseEvent**   <a name="lexv2-Type-runtime_StartConversationResponseEventStream-TextResponseEvent"></a>
The event sent from Amazon Lex to your application with text to present to the user\.  
Type: [TextResponseEvent](API_runtime_TextResponseEvent.md) object  
Required: No

 **ThrottlingException**   <a name="lexv2-Type-runtime_StartConversationResponseEventStream-ThrottlingException"></a>
Exception thrown when your application exceeds the maximum number of concurrent requests\.   
Type: Exception  
Required: No

 **TranscriptEvent**   <a name="lexv2-Type-runtime_StartConversationResponseEventStream-TranscriptEvent"></a>
Event sent from Amazon Lex to your client application that contains a transcript of voice audio\.   
Type: [TranscriptEvent](API_runtime_TranscriptEvent.md) object  
Required: No

 **ValidationException**   <a name="lexv2-Type-runtime_StartConversationResponseEventStream-ValidationException"></a>
Exception thrown when one or more parameters could not be validated\. The `message` contains the name of the field that isn't valid\.  
Type: Exception  
Required: No

## See Also<a name="API_runtime_StartConversationResponseEventStream_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/runtime.lex.v2-2020-08-07/StartConversationResponseEventStream) 
+  [AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/runtime.lex.v2-2020-08-07/StartConversationResponseEventStream) 
+  [AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/runtime.lex.v2-2020-08-07/StartConversationResponseEventStream) 
+  [AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/runtime.lex.v2-2020-08-07/StartConversationResponseEventStream) 