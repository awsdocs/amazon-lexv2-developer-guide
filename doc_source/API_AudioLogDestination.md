# AudioLogDestination<a name="API_AudioLogDestination"></a>

The location of audio log files collected when conversation logging is enabled for a bot\.

## Contents<a name="API_AudioLogDestination_Contents"></a>

 **s3Bucket**   <a name="lexv2-Type-AudioLogDestination-s3Bucket"></a>
The Amazon S3 bucket where the audio log files are stored\. The IAM role specified in the `roleArn` parameter of the [CreateBot](API_CreateBot.md) operation must have permission to write to this bucket\.  
Type: [S3BucketLogDestination](API_S3BucketLogDestination.md) object  
Required: Yes

## See Also<a name="API_AudioLogDestination_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [ AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/models.lex.v2-2020-08-07/AudioLogDestination) 
+  [ AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/models.lex.v2-2020-08-07/AudioLogDestination) 
+  [ AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/models.lex.v2-2020-08-07/AudioLogDestination) 
+  [ AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/models.lex.v2-2020-08-07/AudioLogDestination) 