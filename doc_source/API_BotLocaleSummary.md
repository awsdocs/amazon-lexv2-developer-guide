# BotLocaleSummary<a name="API_BotLocaleSummary"></a>

Summary information about bot locales returned by the [ListBotLocales](API_ListBotLocales.md) operation\.

## Contents<a name="API_BotLocaleSummary_Contents"></a>

 **botLocaleStatus**   <a name="lexv2-Type-BotLocaleSummary-botLocaleStatus"></a>
The current status of the bot locale\. When the status is `Built` the locale is ready for use\.  
Type: String  
Valid Values:` Creating | Building | Built | ReadyExpressTesting | Failed | Deleting | NotBuilt`   
Required: No

 **description**   <a name="lexv2-Type-BotLocaleSummary-description"></a>
The description of the bot locale\.  
Type: String  
Length Constraints: Minimum length of 0\. Maximum length of 200\.  
Required: No

 **lastBuildSubmittedDateTime**   <a name="lexv2-Type-BotLocaleSummary-lastBuildSubmittedDateTime"></a>
A timestamp of the date and time that the bot locale was last built\.  
Type: Timestamp  
Required: No

 **lastUpdatedDateTime**   <a name="lexv2-Type-BotLocaleSummary-lastUpdatedDateTime"></a>
A timestamp of the date and time that the bot locale was last updated\.  
Type: Timestamp  
Required: No

 **localeId**   <a name="lexv2-Type-BotLocaleSummary-localeId"></a>
The language and locale of the bot locale\.  
Type: String  
Required: No

 **localeName**   <a name="lexv2-Type-BotLocaleSummary-localeName"></a>
The name of the bot locale\.  
Type: String  
Required: No

## See Also<a name="API_BotLocaleSummary_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/models.lex.v2-2020-08-07/BotLocaleSummary) 
+  [AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/models.lex.v2-2020-08-07/BotLocaleSummary) 
+  [AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/models.lex.v2-2020-08-07/BotLocaleSummary) 
+  [AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/models.lex.v2-2020-08-07/BotLocaleSummary) 