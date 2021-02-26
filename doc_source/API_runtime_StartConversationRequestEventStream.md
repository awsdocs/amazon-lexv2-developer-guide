# StartConversationRequestEventStream<a name="API_runtime_StartConversationRequestEventStream"></a>

Represents a stream of events between your application and Amazon Lex\.

## Contents<a name="API_runtime_StartConversationRequestEventStream_Contents"></a>

 **AudioInputEvent**   <a name="lexv2-Type-runtime_StartConversationRequestEventStream-AudioInputEvent"></a>
Speech audio sent from your client application to Amazon Lex\. Audio starts accumulating when Amazon Lex identifies a voice and continues until a natural pause in the speech is found before processing\.  
Type: [AudioInputEvent](API_runtime_AudioInputEvent.md) object  
Required: No

 **ConfigurationEvent**   <a name="lexv2-Type-runtime_StartConversationRequestEventStream-ConfigurationEvent"></a>
Configuration information sent from your client application to Amazon Lex  
Type: [ConfigurationEvent](API_runtime_ConfigurationEvent.md) object  
Required: No

 **DisconnectionEvent**   <a name="lexv2-Type-runtime_StartConversationRequestEventStream-DisconnectionEvent"></a>
Event sent from the client application to indicate to Amazon Lex that the conversation is over\.  
Type: [DisconnectionEvent](API_runtime_DisconnectionEvent.md) object  
Required: No

 **DTMFInputEvent**   <a name="lexv2-Type-runtime_StartConversationRequestEventStream-DTMFInputEvent"></a>
DTMF information sent to Amazon Lex by your application\. Amazon Lex accumulates the DMTF information from when the user sends the first character and ends  
+ when there's a pause longer that the value configured for the end timeout\.
+ when there's a digit that is the configured end character\.
+ when Amazon Lex accumulates characters equal to the maximum DTMF character configuration\.
Type: [DTMFInputEvent](API_runtime_DTMFInputEvent.md) object  
Required: No

 **PlaybackCompletionEvent**   <a name="lexv2-Type-runtime_StartConversationRequestEventStream-PlaybackCompletionEvent"></a>
Event sent from the client application to Amazon Lex to indicate that it has finished playing audio and that Amazon Lex should start listening for user input\.  
Type: [PlaybackCompletionEvent](API_runtime_PlaybackCompletionEvent.md) object  
Required: No

 **TextInputEvent**   <a name="lexv2-Type-runtime_StartConversationRequestEventStream-TextInputEvent"></a>
Text sent from your client application to Amazon Lex\. Each `TextInputEvent` is processed individually\.  
Type: [TextInputEvent](API_runtime_TextInputEvent.md) object  
Required: No

## See Also<a name="API_runtime_StartConversationRequestEventStream_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/runtime.lex.v2-2020-08-07/StartConversationRequestEventStream) 
+  [AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/runtime.lex.v2-2020-08-07/StartConversationRequestEventStream) 
+  [AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/runtime.lex.v2-2020-08-07/StartConversationRequestEventStream) 
+  [AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/runtime.lex.v2-2020-08-07/StartConversationRequestEventStream) 