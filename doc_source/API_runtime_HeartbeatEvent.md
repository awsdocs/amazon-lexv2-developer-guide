# HeartbeatEvent<a name="API_runtime_HeartbeatEvent"></a>

Event that Amazon Lex sends to indicate that the stream is still open between the client application and Amazon Lex 

## Contents<a name="API_runtime_HeartbeatEvent_Contents"></a>

 **eventId**   <a name="lexv2-Type-runtime_HeartbeatEvent-eventId"></a>
A unique identifier of the event sent by Amazon Lex\. The identifier is in the form `RESPONSE-N`, where N is a number starting with one and incremented for each event sent by Amazon Lex in the current session\.  
Type: String  
Length Constraints: Minimum length of 2\. Maximum length of 100\.  
Pattern: `[0-9a-zA-Z._:-]+`   
Required: No

## See Also<a name="API_runtime_HeartbeatEvent_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/runtime.lex.v2-2020-08-07/HeartbeatEvent) 
+  [AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/runtime.lex.v2-2020-08-07/HeartbeatEvent) 
+  [AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/runtime.lex.v2-2020-08-07/HeartbeatEvent) 
+  [AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/runtime.lex.v2-2020-08-07/HeartbeatEvent) 