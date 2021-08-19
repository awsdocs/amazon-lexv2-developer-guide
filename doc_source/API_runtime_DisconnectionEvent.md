# DisconnectionEvent<a name="API_runtime_DisconnectionEvent"></a>

A notification from the client that it is disconnecting from Amazon Lex V2\. Sending a `DisconnectionEvent` event is optional, but can help identify a conversation in logs\.

## Contents<a name="API_runtime_DisconnectionEvent_Contents"></a>

 **clientTimestampMillis**   <a name="lexv2-Type-runtime_DisconnectionEvent-clientTimestampMillis"></a>
A timestamp set by the client of the date and time that the event was sent to Amazon Lex V2\.  
Type: Long  
Required: No

 **eventId**   <a name="lexv2-Type-runtime_DisconnectionEvent-eventId"></a>
A unique identifier that your application assigns to the event\. You can use this to identify events in logs\.  
Type: String  
Length Constraints: Minimum length of 2\. Maximum length of 100\.  
Pattern: `[0-9a-zA-Z._:-]+`   
Required: No

## See Also<a name="API_runtime_DisconnectionEvent_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [ AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/runtime.lex.v2-2020-08-07/DisconnectionEvent) 
+  [ AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/runtime.lex.v2-2020-08-07/DisconnectionEvent) 
+  [ AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/runtime.lex.v2-2020-08-07/DisconnectionEvent) 
+  [ AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/runtime.lex.v2-2020-08-07/DisconnectionEvent) 