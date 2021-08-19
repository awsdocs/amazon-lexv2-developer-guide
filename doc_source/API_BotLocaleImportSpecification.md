# BotLocaleImportSpecification<a name="API_BotLocaleImportSpecification"></a>

Provides the bot locale parameters required for importing a bot locale\.

## Contents<a name="API_BotLocaleImportSpecification_Contents"></a>

 **botId**   <a name="lexv2-Type-BotLocaleImportSpecification-botId"></a>
The identifier of the bot to import the locale to\.  
Type: String  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$`   
Required: Yes

 **botVersion**   <a name="lexv2-Type-BotLocaleImportSpecification-botVersion"></a>
The version of the bot to import the locale to\. This can only be the `DRAFT` version of the bot\.  
Type: String  
Length Constraints: Fixed length of 5\.  
Pattern: `^DRAFT$`   
Required: Yes

 **localeId**   <a name="lexv2-Type-BotLocaleImportSpecification-localeId"></a>
The identifier of the language and locale that the bot will be used in\. The string must match one of the supported locales\. All of the intents, slot types, and slots used in the bot must have the same locale\. For more information, see [Supported languages](https://docs.aws.amazon.com/lexv2/latest/dg/how-languages.html)\.  
Type: String  
Required: Yes

 **nluIntentConfidenceThreshold**   <a name="lexv2-Type-BotLocaleImportSpecification-nluIntentConfidenceThreshold"></a>
Determines the threshold where Amazon Lex will insert the `AMAZON.FallbackIntent`, `AMAZON.KendraSearchIntent`, or both when returning alternative intents\. `AMAZON.FallbackIntent` and `AMAZON.KendraSearchIntent` are only inserted if they are configured for the bot\.   
For example, suppose a bot is configured with the confidence threshold of 0\.80 and the `AMAZON.FallbackIntent`\. Amazon Lex returns three alternative intents with the following confidence scores: IntentA \(0\.70\), IntentB \(0\.60\), IntentC \(0\.50\)\. The response from the `PostText` operation would be:  
+  `AMAZON.FallbackIntent` 
+  `IntentA` 
+  `IntentB` 
+  `IntentC` 
Type: Double  
Valid Range: Minimum value of 0\. Maximum value of 1\.  
Required: No

 **voiceSettings**   <a name="lexv2-Type-BotLocaleImportSpecification-voiceSettings"></a>
Defines settings for using an Amazon Polly voice to communicate with a user\.  
Type: [VoiceSettings](API_VoiceSettings.md) object  
Required: No

## See Also<a name="API_BotLocaleImportSpecification_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [ AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/models.lex.v2-2020-08-07/BotLocaleImportSpecification) 
+  [ AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/models.lex.v2-2020-08-07/BotLocaleImportSpecification) 
+  [ AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/models.lex.v2-2020-08-07/BotLocaleImportSpecification) 
+  [ AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/models.lex.v2-2020-08-07/BotLocaleImportSpecification) 