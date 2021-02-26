# IntentConfirmationSetting<a name="API_IntentConfirmationSetting"></a>

Provides a prompt for making sure that the user is ready for the intent to be fulfilled\.

## Contents<a name="API_IntentConfirmationSetting_Contents"></a>

 **declinationResponse**   <a name="lexv2-Type-IntentConfirmationSetting-declinationResponse"></a>
When the user answers "no" to the question defined in `promptSpecification`, Amazon Lex responds with this response to acknowledge that the intent was canceled\.   
Type: [ResponseSpecification](API_ResponseSpecification.md) object  
Required: Yes

 **promptSpecification**   <a name="lexv2-Type-IntentConfirmationSetting-promptSpecification"></a>
Prompts the user to confirm the intent\. This question should have a yes or no answer\.  
Amazon Lex uses this prompt to ensure that the user acknowledges that the intent is ready for fulfillment\. For example, with the `OrderPizza` intent, you might want to confirm that the order is correct before placing it\. For other intents, such as intents that simply respond to user questions, you might not need to ask the user for confirmation before providing the information\.   
Type: [PromptSpecification](API_PromptSpecification.md) object  
Required: Yes

## See Also<a name="API_IntentConfirmationSetting_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/models.lex.v2-2020-08-07/IntentConfirmationSetting) 
+  [AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/models.lex.v2-2020-08-07/IntentConfirmationSetting) 
+  [AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/models.lex.v2-2020-08-07/IntentConfirmationSetting) 
+  [AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/models.lex.v2-2020-08-07/IntentConfirmationSetting) 