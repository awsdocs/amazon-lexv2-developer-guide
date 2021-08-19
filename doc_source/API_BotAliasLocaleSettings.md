# BotAliasLocaleSettings<a name="API_BotAliasLocaleSettings"></a>

Specifies settings that are unique to a locale\. For example, you can use different Lambda function depending on the bot's locale\.

## Contents<a name="API_BotAliasLocaleSettings_Contents"></a>

 **codeHookSpecification**   <a name="lexv2-Type-BotAliasLocaleSettings-codeHookSpecification"></a>
Specifies the Lambda function that should be used in the locale\.  
Type: [CodeHookSpecification](API_CodeHookSpecification.md) object  
Required: No

 **enabled**   <a name="lexv2-Type-BotAliasLocaleSettings-enabled"></a>
Determines whether the locale is enabled for the bot\. If the value is `false`, the locale isn't available for use\.  
Type: Boolean  
Required: Yes

## See Also<a name="API_BotAliasLocaleSettings_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [ AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/models.lex.v2-2020-08-07/BotAliasLocaleSettings) 
+  [ AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/models.lex.v2-2020-08-07/BotAliasLocaleSettings) 
+  [ AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/models.lex.v2-2020-08-07/BotAliasLocaleSettings) 
+  [ AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/models.lex.v2-2020-08-07/BotAliasLocaleSettings) 