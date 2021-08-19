# ConfigurationEvent<a name="API_runtime_ConfigurationEvent"></a>

The initial event sent from the application to Amazon Lex V2 to configure the conversation, including session and request attributes and the response content type\.

## Contents<a name="API_runtime_ConfigurationEvent_Contents"></a>

 **clientTimestampMillis**   <a name="lexv2-Type-runtime_ConfigurationEvent-clientTimestampMillis"></a>
A timestamp set by the client of the date and time that the event was sent to Amazon Lex V2\.  
Type: Long  
Required: No

 **disablePlayback**   <a name="lexv2-Type-runtime_ConfigurationEvent-disablePlayback"></a>
Determines whether Amazon Lex V2 should send audio responses to the client application\. When this parameter if `false`, the client application needs to create responses for the user\.   
Type: Boolean  
Required: No

 **eventId**   <a name="lexv2-Type-runtime_ConfigurationEvent-eventId"></a>
A unique identifier that your application assigns to the event\. You can use this to identify events in logs\.  
Type: String  
Length Constraints: Minimum length of 2\. Maximum length of 100\.  
Pattern: `[0-9a-zA-Z._:-]+`   
Required: No

 **requestAttributes**   <a name="lexv2-Type-runtime_ConfigurationEvent-requestAttributes"></a>
Request\-specific information passed between the client application and Amazon Lex V2\.  
The namespace `x-amz-lex:` is reserved for special attributes\. Don't create any request attributes for prefix `x-amz-lex:`\.  
Type: String to string map  
Key Length Constraints: Minimum length of 1\.  
Required: No

 **responseContentType**   <a name="lexv2-Type-runtime_ConfigurationEvent-responseContentType"></a>
The message that Amazon Lex V2 returns in the response can be either text or speech based on the `responseContentType` value\.  
+ If the value is `text/plain;charset=utf-8`, Amazon Lex V2 returns text in the response\.
+ If the value begins with `audio/`, Amazon Lex V2 returns speech in the response\. Amazon Lex V2 uses Amazon Polly to generate the speech using the configuration that you specified in the `requestContentType` parameter\. For example, if you specify `audio/mpeg` as the value, Amazon Lex V2 returns speech in the MPEG format\.
+ If the value is `audio/pcm`, the speech returned is audio/pcm in 16\-bit, little\-endian format\.
+ The following are the accepted values:
  + audio/mpeg
  + audio/ogg
  + audio/pcm
  + audio/\* \(defaults to mpeg\)
  + text/plain; charset=utf\-8
Type: String  
Length Constraints: Minimum length of 1\.  
Required: Yes

 **sessionState**   <a name="lexv2-Type-runtime_ConfigurationEvent-sessionState"></a>
The state of the user's session with Amazon Lex V2\.  
Type: [SessionState](API_runtime_SessionState.md) object  
Required: No

 **welcomeMessages**   <a name="lexv2-Type-runtime_ConfigurationEvent-welcomeMessages"></a>
A list of messages to send to the user\.  
Type: Array of [Message](API_runtime_Message.md) objects  
Array Members: Maximum number of 10 items\.  
Required: No

## See Also<a name="API_runtime_ConfigurationEvent_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [ AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/runtime.lex.v2-2020-08-07/ConfigurationEvent) 
+  [ AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/runtime.lex.v2-2020-08-07/ConfigurationEvent) 
+  [ AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/runtime.lex.v2-2020-08-07/ConfigurationEvent) 
+  [ AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/runtime.lex.v2-2020-08-07/ConfigurationEvent) 