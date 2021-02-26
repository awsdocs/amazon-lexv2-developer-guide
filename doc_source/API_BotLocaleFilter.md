# BotLocaleFilter<a name="API_BotLocaleFilter"></a>

Filters responses returned by the `ListBotLocales` operation\.

## Contents<a name="API_BotLocaleFilter_Contents"></a>

 **name**   <a name="lexv2-Type-BotLocaleFilter-name"></a>
The name of the field to filter the list of bots\.  
Type: String  
Valid Values:` BotLocaleName`   
Required: Yes

 **operator**   <a name="lexv2-Type-BotLocaleFilter-operator"></a>
The operator to use for the filter\. Specify `EQ` when the `ListBotLocales` operation should return only aliases that equal the specified value\. Specify `CO` when the `ListBotLocales` operation should return aliases that contain the specified value\.  
Type: String  
Valid Values:` CO | EQ`   
Required: Yes

 **values**   <a name="lexv2-Type-BotLocaleFilter-values"></a>
The value to use for filtering the list of bots\.  
Type: Array of strings  
Array Members: Fixed number of 1 item\.  
Length Constraints: Minimum length of 1\. Maximum length of 100\.  
Pattern: `^[0-9a-zA-Z_()\s-]+$`   
Required: Yes

## See Also<a name="API_BotLocaleFilter_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/models.lex.v2-2020-08-07/BotLocaleFilter) 
+  [AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/models.lex.v2-2020-08-07/BotLocaleFilter) 
+  [AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/models.lex.v2-2020-08-07/BotLocaleFilter) 
+  [AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/models.lex.v2-2020-08-07/BotLocaleFilter) 