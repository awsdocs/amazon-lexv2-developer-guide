# Analyzing the sentiment of user utterances<a name="using-sentiment"></a>

You can use sentiment analysis to determine the sentiments expressed in a user utterance\. With the sentiment information you can manage conversation flow or perform post\-call analysis\. For example, if the user sentiment is negative you can create a flow to hand over a conversation to a human agent\.

Amazon Lex integrates with Amazon Comprehend to detect user sentiment\. The response from Amazon Comprehend indicates whether the overall sentiment of the text is positive, neutral, negative, or mixed\. The response contains the most likely sentiment for the user utterance and the scores for each of the sentiment categories\. The score represents the likelihood that the sentiment was correctly detected\.

 You enable sentiment analysis for a bot using the console or by using the Amazon Lex API\. You enable sentiment analysis on an alias for the bot\. On the Amazon Lex console:

1. Choose an alias\.

1. In **Details**, choose **Edit**\.

1. Choose **Enable sentiment analysis** to sentiment analysis on or off\.

1. Choose **Confirm** to save your changes\.

If you are using the API, call the [CreateBotAlias](API_CreateBotAlias.md) operation with the `detectSentiment` field set to `true`\. 

When sentiment analysis is enabled, the response from the [RecognizeText](API_runtime_RecognizeText.md) and [RecognizeUtterance](API_runtime_RecognizeUtterance.md) operations return a field called `sentimentResponse` in the `interpretations` structure with other metadata\. The `sentimentResponse` field has two fields, `sentiment` and `sentimentScore`, that contain the result of the sentiment analysis\. If you are using a Lambda function, the `sentimentResponse` field is included in the event data sent to your function\.

The following is an example of the `sentimentResponse` field returned as part of the `RecognizeText` or `RecognizeUtterance` response\.

```
sentimentResponse {
    "sentimentScore": {
        "mixed": 0.030585512690246105,
        "positive": 0.94992071056365967,
        "neutral": 0.0141543131828308,
        "negative": 0.00893945890665054
    },
    "sentiment": "POSITIVE"
}
```

Amazon Lex calls Amazon Comprehend on your behalf to determine the sentiment in every utterance processed by the bot\. By enabling sentiment analysis, you agree to the service terms and agreements for Amazon Comprehend\. For more information about pricing for Amazon Comprehend, see [Amazon Comprehend Pricing](http://aws.amazon.com/comprehend/pricing/)\.

For more information about how Amazon Comprehend sentiment analysis works, see [ Determine the sentiment ](https://docs.aws.amazon.com/comprehend/latest/dg/how-sentiment.html) in the *Amazon Comprehend Developer Guide*\.