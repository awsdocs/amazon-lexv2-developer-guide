# S3BucketLogDestination<a name="API_S3BucketLogDestination"></a>

Specifies an Amazon S3 bucket for logging audio conversations

## Contents<a name="API_S3BucketLogDestination_Contents"></a>

 **kmsKeyArn**   <a name="lexv2-Type-S3BucketLogDestination-kmsKeyArn"></a>
The Amazon Resource Name \(ARN\) of an AWS Key Management Service \(KMS\) key for encrypting audio log files stored in an S3 bucket\.  
Type: String  
Length Constraints: Minimum length of 20\. Maximum length of 2048\.  
Pattern: `^arn:[\w\-]+:kms:[\w\-]+:[\d]{12}:(?:key\/[\w\-]+|alias\/[a-zA-Z0-9:\/_\-]{1,256})$`   
Required: No

 **logPrefix**   <a name="lexv2-Type-S3BucketLogDestination-logPrefix"></a>
The S3 prefix to assign to audio log files\.  
Type: String  
Length Constraints: Maximum length of 1024\.  
Required: Yes

 **s3BucketArn**   <a name="lexv2-Type-S3BucketLogDestination-s3BucketArn"></a>
The Amazon Resource Name \(ARN\) of an Amazon S3 bucket where audio log files are stored\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 2048\.  
Pattern: `^arn:[\w\-]+:s3:::[a-z0-9][\.\-a-z0-9]{1,61}[a-z0-9]$`   
Required: Yes

## See Also<a name="API_S3BucketLogDestination_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/models.lex.v2-2020-08-07/S3BucketLogDestination) 
+  [AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/models.lex.v2-2020-08-07/S3BucketLogDestination) 
+  [AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/models.lex.v2-2020-08-07/S3BucketLogDestination) 
+  [AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/models.lex.v2-2020-08-07/S3BucketLogDestination) 