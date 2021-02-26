# CloudWatchLogGroupLogDestination<a name="API_CloudWatchLogGroupLogDestination"></a>

The Amazon CloudWatch Logs log group where the text and metadata logs are delivered\. The log group must exist before you enable logging\.

## Contents<a name="API_CloudWatchLogGroupLogDestination_Contents"></a>

 **cloudWatchLogGroupArn**   <a name="lexv2-Type-CloudWatchLogGroupLogDestination-cloudWatchLogGroupArn"></a>
The Amazon Resource Name \(ARN\) of the log group where text and metadata logs are delivered\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 2048\.  
Pattern: `^arn:[\w\-]+:logs:[\w\-]+:[\d]{12}:log-group:[\.\-_/#A-Za-z0-9]{1,512}(?::\*)?$`   
Required: Yes

 **logPrefix**   <a name="lexv2-Type-CloudWatchLogGroupLogDestination-logPrefix"></a>
The prefix of the log stream name within the log group that you specified   
Type: String  
Length Constraints: Maximum length of 1024\.  
Required: Yes

## See Also<a name="API_CloudWatchLogGroupLogDestination_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/models.lex.v2-2020-08-07/CloudWatchLogGroupLogDestination) 
+  [AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/models.lex.v2-2020-08-07/CloudWatchLogGroupLogDestination) 
+  [AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/models.lex.v2-2020-08-07/CloudWatchLogGroupLogDestination) 
+  [AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/models.lex.v2-2020-08-07/CloudWatchLogGroupLogDestination) 