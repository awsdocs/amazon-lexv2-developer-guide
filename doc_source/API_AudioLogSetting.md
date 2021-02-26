# AudioLogSetting<a name="API_AudioLogSetting"></a>

Settings for logging audio of conversations between Amazon Lex and a user\. You specify whether to log audio and the Amazon S3 bucket where the audio file is stored\.

## Contents<a name="API_AudioLogSetting_Contents"></a>

 **destination**   <a name="lexv2-Type-AudioLogSetting-destination"></a>
The location of audio log files collected when conversation logging is enabled for a bot\.  
Type: [AudioLogDestination](API_AudioLogDestination.md) object  
Required: Yes

 **enabled**   <a name="lexv2-Type-AudioLogSetting-enabled"></a>
Determines whether audio logging in enabled for the bot\.  
Type: Boolean  
Required: Yes

## See Also<a name="API_AudioLogSetting_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/models.lex.v2-2020-08-07/AudioLogSetting) 
+  [AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/models.lex.v2-2020-08-07/AudioLogSetting) 
+  [AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/models.lex.v2-2020-08-07/AudioLogSetting) 
+  [AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/models.lex.v2-2020-08-07/AudioLogSetting) 