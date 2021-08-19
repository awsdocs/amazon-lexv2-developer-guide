# ConversationLogSettings<a name="API_ConversationLogSettings"></a>

Configures conversation logging that saves audio, text, and metadata for the conversations with your users\.

## Contents<a name="API_ConversationLogSettings_Contents"></a>

 **audioLogSettings**   <a name="lexv2-Type-ConversationLogSettings-audioLogSettings"></a>
The Amazon S3 settings for logging audio to an S3 bucket\.  
Type: Array of [AudioLogSetting](API_AudioLogSetting.md) objects  
Array Members: Fixed number of 1 item\.  
Required: No

 **textLogSettings**   <a name="lexv2-Type-ConversationLogSettings-textLogSettings"></a>
The Amazon CloudWatch Logs settings for logging text and metadata\.  
Type: Array of [TextLogSetting](API_TextLogSetting.md) objects  
Array Members: Fixed number of 1 item\.  
Required: No

## See Also<a name="API_ConversationLogSettings_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [ AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/models.lex.v2-2020-08-07/ConversationLogSettings) 
+  [ AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/models.lex.v2-2020-08-07/ConversationLogSettings) 
+  [ AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/models.lex.v2-2020-08-07/ConversationLogSettings) 
+  [ AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/models.lex.v2-2020-08-07/ConversationLogSettings) 