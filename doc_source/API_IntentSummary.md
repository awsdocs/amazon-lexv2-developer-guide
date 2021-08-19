# IntentSummary<a name="API_IntentSummary"></a>

Summary information about an intent returned by the `ListIntents` operation\.

## Contents<a name="API_IntentSummary_Contents"></a>

 **description**   <a name="lexv2-Type-IntentSummary-description"></a>
The description of the intent\.  
Type: String  
Length Constraints: Minimum length of 0\. Maximum length of 200\.  
Required: No

 **inputContexts**   <a name="lexv2-Type-IntentSummary-inputContexts"></a>
The input contexts that must be active for this intent to be considered for recognition\.  
Type: Array of [InputContext](API_InputContext.md) objects  
Array Members: Minimum number of 0 items\. Maximum number of 5 items\.  
Required: No

 **intentId**   <a name="lexv2-Type-IntentSummary-intentId"></a>
The unique identifier assigned to the intent\. Use this ID to get detailed information about the intent with the `DescribeIntent` operation\.  
Type: String  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$`   
Required: No

 **intentName**   <a name="lexv2-Type-IntentSummary-intentName"></a>
The name of the intent\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 100\.  
Pattern: `^([0-9a-zA-Z][_-]?)+$`   
Required: No

 **lastUpdatedDateTime**   <a name="lexv2-Type-IntentSummary-lastUpdatedDateTime"></a>
The timestamp of the date and time that the intent was last updated\.  
Type: Timestamp  
Required: No

 **outputContexts**   <a name="lexv2-Type-IntentSummary-outputContexts"></a>
The output contexts that are activated when this intent is fulfilled\.  
Type: Array of [OutputContext](API_OutputContext.md) objects  
Array Members: Minimum number of 0 items\. Maximum number of 10 items\.  
Required: No

 **parentIntentSignature**   <a name="lexv2-Type-IntentSummary-parentIntentSignature"></a>
If this intent is derived from a built\-in intent, the name of the parent intent\.  
Type: String  
Required: No

## See Also<a name="API_IntentSummary_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [ AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/models.lex.v2-2020-08-07/IntentSummary) 
+  [ AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/models.lex.v2-2020-08-07/IntentSummary) 
+  [ AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/models.lex.v2-2020-08-07/IntentSummary) 
+  [ AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/models.lex.v2-2020-08-07/IntentSummary) 