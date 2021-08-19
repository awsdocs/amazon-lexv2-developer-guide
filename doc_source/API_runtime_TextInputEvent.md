# TextInputEvent<a name="API_runtime_TextInputEvent"></a>

The event sent from your client application to Amazon Lex V2 with text input from the user\.

## Contents<a name="API_runtime_TextInputEvent_Contents"></a>

 **clientTimestampMillis**   <a name="lexv2-Type-runtime_TextInputEvent-clientTimestampMillis"></a>
A timestamp set by the client of the date and time that the event was sent to Amazon Lex V2\.  
Type: Long  
Required: No

 **eventId**   <a name="lexv2-Type-runtime_TextInputEvent-eventId"></a>
A unique identifier that your application assigns to the event\. You can use this to identify events in logs\.  
Type: String  
Length Constraints: Minimum length of 2\. Maximum length of 100\.  
Pattern: `[0-9a-zA-Z._:-]+`   
Required: No

 **text**   <a name="lexv2-Type-runtime_TextInputEvent-text"></a>
The text from the user\. Amazon Lex V2 processes this as a complete statement\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 1024\.  
Required: Yes

## See Also<a name="API_runtime_TextInputEvent_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [ AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/runtime.lex.v2-2020-08-07/TextInputEvent) 
+  [ AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/runtime.lex.v2-2020-08-07/TextInputEvent) 
+  [ AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/runtime.lex.v2-2020-08-07/TextInputEvent) 
+  [ AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/runtime.lex.v2-2020-08-07/TextInputEvent) 