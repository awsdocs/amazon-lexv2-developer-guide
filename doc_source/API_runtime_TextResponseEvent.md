# TextResponseEvent<a name="API_runtime_TextResponseEvent"></a>

The event sent from Amazon Lex to your application with text to present to the user\.

## Contents<a name="API_runtime_TextResponseEvent_Contents"></a>

 **eventId**   <a name="lexv2-Type-runtime_TextResponseEvent-eventId"></a>
A unique identifier of the event sent by Amazon Lex\. The identifier is in the form `RESPONSE-N`, where N is a number starting with one and incremented for each event sent by Amazon Lex in the current session\.  
Type: String  
Length Constraints: Minimum length of 2\. Maximum length of 100\.  
Pattern: `[0-9a-zA-Z._:-]+`   
Required: No

 **messages**   <a name="lexv2-Type-runtime_TextResponseEvent-messages"></a>
A list of messages to send to the user\. Messages are ordered based on the order that you returned the messages from your Lambda function or the order that the messages are defined in the bot\.  
Type: Array of [Message](API_runtime_Message.md) objects  
Array Members: Maximum number of 10 items\.  
Required: No

## See Also<a name="API_runtime_TextResponseEvent_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/runtime.lex.v2-2020-08-07/TextResponseEvent) 
+  [AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/runtime.lex.v2-2020-08-07/TextResponseEvent) 
+  [AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/runtime.lex.v2-2020-08-07/TextResponseEvent) 
+  [AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/runtime.lex.v2-2020-08-07/TextResponseEvent) 