# WaitAndContinueSpecification<a name="API_WaitAndContinueSpecification"></a>

Specifies the prompts that Amazon Lex uses while a bot is waiting for customer input\. 

## Contents<a name="API_WaitAndContinueSpecification_Contents"></a>

 **active**   <a name="lexv2-Type-WaitAndContinueSpecification-active"></a>
Specifies whether the bot will wait for a user to respond\. When this field is false, wait and continue responses for a slot aren't used and the bot expects an appropriate response within the configured timeout\. If the `active` field isn't specified, the default is true\.  
Type: Boolean  
Required: No

 **continueResponse**   <a name="lexv2-Type-WaitAndContinueSpecification-continueResponse"></a>
The response that Amazon Lex sends to indicate that the bot is ready to continue the conversation\.  
Type: [ResponseSpecification](API_ResponseSpecification.md) object  
Required: Yes

 **stillWaitingResponse**   <a name="lexv2-Type-WaitAndContinueSpecification-stillWaitingResponse"></a>
A response that Amazon Lex sends periodically to the user to indicate that the bot is still waiting for input from the user\.  
Type: [StillWaitingResponseSpecification](API_StillWaitingResponseSpecification.md) object  
Required: No

 **waitingResponse**   <a name="lexv2-Type-WaitAndContinueSpecification-waitingResponse"></a>
The response that Amazon Lex sends to indicate that the bot is waiting for the conversation to continue\.  
Type: [ResponseSpecification](API_ResponseSpecification.md) object  
Required: Yes

## See Also<a name="API_WaitAndContinueSpecification_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [ AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/models.lex.v2-2020-08-07/WaitAndContinueSpecification) 
+  [ AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/models.lex.v2-2020-08-07/WaitAndContinueSpecification) 
+  [ AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/models.lex.v2-2020-08-07/WaitAndContinueSpecification) 
+  [ AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/models.lex.v2-2020-08-07/WaitAndContinueSpecification) 