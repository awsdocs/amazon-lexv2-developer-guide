# SentimentResponse<a name="API_runtime_SentimentResponse"></a>

Provides information about the sentiment expressed in a user's response in a conversation\. Sentiments are determined using Amazon Comprehend\. Sentiments are only returned if they are enabled for the bot\.

For more information, see [ Determine Sentiment ](https://docs.aws.amazon.com/comprehend/latest/dg/how-sentiment.html) in the *Amazon Comprehend developer guide*\.

## Contents<a name="API_runtime_SentimentResponse_Contents"></a>

 **sentiment**   <a name="lexv2-Type-runtime_SentimentResponse-sentiment"></a>
The overall sentiment expressed in the user's response\. This is the sentiment most likely expressed by the user based on the analysis by Amazon Comprehend\.  
Type: String  
Valid Values:` MIXED | NEGATIVE | NEUTRAL | POSITIVE`   
Required: No

 **sentimentScore**   <a name="lexv2-Type-runtime_SentimentResponse-sentimentScore"></a>
The individual sentiment responses for the utterance\.  
Type: [SentimentScore](API_runtime_SentimentScore.md) object  
Required: No

## See Also<a name="API_runtime_SentimentResponse_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [ AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/runtime.lex.v2-2020-08-07/SentimentResponse) 
+  [ AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/runtime.lex.v2-2020-08-07/SentimentResponse) 
+  [ AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/runtime.lex.v2-2020-08-07/SentimentResponse) 
+  [ AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/runtime.lex.v2-2020-08-07/SentimentResponse) 