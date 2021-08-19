# Interpretation<a name="API_runtime_Interpretation"></a>

An intent that Amazon Lex V2 determined might satisfy the user's utterance\. The intents are ordered by the confidence score\. 

## Contents<a name="API_runtime_Interpretation_Contents"></a>

 **intent**   <a name="lexv2-Type-runtime_Interpretation-intent"></a>
A list of intents that might satisfy the user's utterance\. The intents are ordered by the confidence score\.  
Type: [Intent](API_runtime_Intent.md) object  
Required: No

 **nluConfidence**   <a name="lexv2-Type-runtime_Interpretation-nluConfidence"></a>
Determines the threshold where Amazon Lex V2 will insert the `AMAZON.FallbackIntent`, `AMAZON.KendraSearchIntent`, or both when returning alternative intents in a response\. `AMAZON.FallbackIntent` and `AMAZON.KendraSearchIntent` are only inserted if they are configured for the bot\.  
Type: [ConfidenceScore](API_runtime_ConfidenceScore.md) object  
Required: No

 **sentimentResponse**   <a name="lexv2-Type-runtime_Interpretation-sentimentResponse"></a>
The sentiment expressed in an utterance\.   
When the bot is configured to send utterances to Amazon Comprehend for sentiment analysis, this field contains the result of the analysis\.  
Type: [SentimentResponse](API_runtime_SentimentResponse.md) object  
Required: No

## See Also<a name="API_runtime_Interpretation_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [ AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/runtime.lex.v2-2020-08-07/Interpretation) 
+  [ AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/runtime.lex.v2-2020-08-07/Interpretation) 
+  [ AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/runtime.lex.v2-2020-08-07/Interpretation) 
+  [ AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/runtime.lex.v2-2020-08-07/Interpretation) 