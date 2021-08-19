# Monitoring Amazon Lex V2 with Amazon CloudWatch<a name="monitoring-cloudwatch"></a>

You can monitor Amazon Lex V2 using CloudWatch, which collects raw data and processes it into readable, near real\-time metrics\. These statistics are kept for 15 months, so that you can access historical information and gain a better perspective on how your web application or service is performing\. You can also set alarms that watch for certain thresholds, and send notifications or take actions when those thresholds are met\. For more information, see the [Amazon CloudWatch User Guide](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/)\.

The Amazon Lex V2 service reports the following metrics in the `AWS/Lex` namespace\.


| Metric | Description | 
| --- | --- | 
|  `KendraIndexAccessError`  |  The number of times that Amazon Lex V2 could not access your Amazon Kendra index\. [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/lexv2/latest/dg/monitoring-cloudwatch.html) Unit: Count  | 
|  `KendraLatency`  |  The amount of time that it takes Amazon Kendra to respond to a request from the `AMAZON.KendraSearchIntent`\. Valid dimensions:  [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/lexv2/latest/dg/monitoring-cloudwatch.html) Unit: Milliseconds  | 
|  `KendraSuccess`  |  The number of times that Amazon Lex V2 couldn't access your Amazon Kendra index\. Valid dimensions: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/lexv2/latest/dg/monitoring-cloudwatch.html) Unit: Count  | 
|  `KendraSystemErrors`  |  The number of times that Amazon Lex V2 couldn't query the Amazon Kendra index\. Valid dimensions: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/lexv2/latest/dg/monitoring-cloudwatch.html) Unit: Count  | 
|  `KendraThrottledEvents`  |  The number of times Amazon Kendra throttled requests from the `AMAZON.KendraSearchIntent`\. Valid dimensions: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/lexv2/latest/dg/monitoring-cloudwatch.html) Unit: Count  | 
|  `MissedUtteranceCount`  |  The number of utterances that were not recognized in the specified time period\. Valid dimensions: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/lexv2/latest/dg/monitoring-cloudwatch.html) Unit: Count  | 
|  `RuntimeInvalidLambdaResponses`  |  The number of invalid AWS Lambda responses in the specified period\. Valid dimensions: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/lexv2/latest/dg/monitoring-cloudwatch.html) Unit: Count  | 
|  `RuntimeLambdaErrors`  |  The number of Lambda runtime errors in the specified time period\. Valid dimensions: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/lexv2/latest/dg/monitoring-cloudwatch.html) Unit: Count  | 
|  `RuntimePollyErrors`  |  The number of invalid Amazon Polly responses in the specified time period\. Valid dimensions: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/lexv2/latest/dg/monitoring-cloudwatch.html) Unit: Count  | 
|  `RuntimeRequestCount`  |  The number of runtime requests in the specified time period\. Valid dimensions: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/lexv2/latest/dg/monitoring-cloudwatch.html) Unit: Count  | 
| `RuntimeRequestLength` | Total length of a conversation with a Amazon Lex V2 bot\. Only applicable to the [StartConversation](API_runtime_StartConversation.md) operation\. Valid dimensions: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/lexv2/latest/dg/monitoring-cloudwatch.html) Unit: milliseconds | 
|  `RuntimeSuccessfulRequestLatency`  |  The latency for successful requests between the time the request was made and the response was passed back\. Valid dimensions: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/lexv2/latest/dg/monitoring-cloudwatch.html) Unit: milliseconds  | 
|  `RuntimeSystemErrors`  |  The number of system errors in the specified period\. The response code range for a system error is 500 to 599\. Valid dimensions: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/lexv2/latest/dg/monitoring-cloudwatch.html) Unit: Count  | 
|  `RuntimeThrottledEvents`  |  The number of throttled events\. Amazon Lex V2 throttles an event when it receives more requests than th eilmit of transactions per second set for your account\. If the limit set for your account is frequently exceeded, you can request a limit increase\. To request an increase, see [AWS service limits](https://docs.aws.amazon.com/general/latest/gr/aws_service_limits.html)\. Valid dimensions: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/lexv2/latest/dg/monitoring-cloudwatch.html) Unit: Count  | 
|  `RuntimeUserErrors`  |  The number of user errors in the specified period\. The response code range for a user error is 400 to 499\. Valid dimensions: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/lexv2/latest/dg/monitoring-cloudwatch.html) Unit: Count  | 

The following dimensions are supported for the Amazon Lex V2 metrics\.


|  Dimension  |  Description  | 
| --- | --- | 
|  Operation  |  The name of the Amazon Lex V2 operation – `RecognizeText`, `RecognizeUtterance`, `StartConversation`, `GetSession`, `PutSession`, `DeleteSession` – that generated the entry\.  | 
|  BotId  |  The alphanumeric unique identifier for the bot\.  | 
|  BotAliasId  |  The alphanumeric unique identifier for the bot alias\.  | 
|  BotVersion  |  The numeric version of the bot\.  | 
|  InputMode  |  The type of input to the bot – speech, text, or DTMF\.  | 
|  LocaleId  |  The identifier of the bot's locale, such as en\-US or fr\-CA\.  | 