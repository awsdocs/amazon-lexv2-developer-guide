# PromptSpecification<a name="API_PromptSpecification"></a>

Specifies a list of message groups that Amazon Lex sends to a user to elicit a response\.

## Contents<a name="API_PromptSpecification_Contents"></a>

 **allowInterrupt**   <a name="lexv2-Type-PromptSpecification-allowInterrupt"></a>
Indicates whether the user can interrupt a speech prompt from the bot\.  
Type: Boolean  
Required: No

 **maxRetries**   <a name="lexv2-Type-PromptSpecification-maxRetries"></a>
The maximum number of times the bot tries to elicit a resonse from the user using this prompt\.  
Type: Integer  
Valid Range: Minimum value of 0\. Maximum value of 5\.  
Required: Yes

 **messageGroups**   <a name="lexv2-Type-PromptSpecification-messageGroups"></a>
A collection of messages that Amazon Lex can send to the user\. Amazon Lex chooses the actual message to send at runtime\.  
Type: Array of [MessageGroup](API_MessageGroup.md) objects  
Array Members: Minimum number of 1 item\. Maximum number of 5 items\.  
Required: Yes

## See Also<a name="API_PromptSpecification_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [ AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/models.lex.v2-2020-08-07/PromptSpecification) 
+  [ AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/models.lex.v2-2020-08-07/PromptSpecification) 
+  [ AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/models.lex.v2-2020-08-07/PromptSpecification) 
+  [ AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/models.lex.v2-2020-08-07/PromptSpecification) 