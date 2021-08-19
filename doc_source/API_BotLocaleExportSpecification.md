# BotLocaleExportSpecification<a name="API_BotLocaleExportSpecification"></a>

Provides the bot locale parameters required for exporting a bot locale\.

## Contents<a name="API_BotLocaleExportSpecification_Contents"></a>

 **botId**   <a name="lexv2-Type-BotLocaleExportSpecification-botId"></a>
The identifier of the bot to create the locale for\.  
Type: String  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$`   
Required: Yes

 **botVersion**   <a name="lexv2-Type-BotLocaleExportSpecification-botVersion"></a>
The version of the bot to export\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 5\.  
Pattern: `^(DRAFT|[0-9]+)$`   
Required: Yes

 **localeId**   <a name="lexv2-Type-BotLocaleExportSpecification-localeId"></a>
The identifier of the language and locale to export\. The string must match one of the locales in the bot\.  
Type: String  
Required: Yes

## See Also<a name="API_BotLocaleExportSpecification_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [ AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/models.lex.v2-2020-08-07/BotLocaleExportSpecification) 
+  [ AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/models.lex.v2-2020-08-07/BotLocaleExportSpecification) 
+  [ AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/models.lex.v2-2020-08-07/BotLocaleExportSpecification) 
+  [ AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/models.lex.v2-2020-08-07/BotLocaleExportSpecification) 