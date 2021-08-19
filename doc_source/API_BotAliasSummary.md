# BotAliasSummary<a name="API_BotAliasSummary"></a>

Summary information about bot aliases returned from the [ListBotAliases](API_ListBotAliases.md) operation\.

## Contents<a name="API_BotAliasSummary_Contents"></a>

 **botAliasId**   <a name="lexv2-Type-BotAliasSummary-botAliasId"></a>
The unique identifier assigned to the bot alias\. You can use this ID to get detailed information about the alias using the [DescribeBotAlias](API_DescribeBotAlias.md) operation\.  
Type: String  
Length Constraints: Fixed length of 10\.  
Pattern: `^(\bTSTALIASID\b|[0-9a-zA-Z]+)$`   
Required: No

 **botAliasName**   <a name="lexv2-Type-BotAliasSummary-botAliasName"></a>
The name of the bot alias\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 100\.  
Pattern: `^([0-9a-zA-Z][_-]?)+$`   
Required: No

 **botAliasStatus**   <a name="lexv2-Type-BotAliasSummary-botAliasStatus"></a>
The current state of the bot alias\. If the status is `Available`, the alias is ready for use\.  
Type: String  
Valid Values:` Creating | Available | Deleting | Failed`   
Required: No

 **botVersion**   <a name="lexv2-Type-BotAliasSummary-botVersion"></a>
The version of the bot that the bot alias references\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 5\.  
Pattern: `^(DRAFT|[0-9]+)$`   
Required: No

 **creationDateTime**   <a name="lexv2-Type-BotAliasSummary-creationDateTime"></a>
A timestamp of the date and time that the bot alias was created\.  
Type: Timestamp  
Required: No

 **description**   <a name="lexv2-Type-BotAliasSummary-description"></a>
The description of the bot alias\.  
Type: String  
Length Constraints: Minimum length of 0\. Maximum length of 200\.  
Required: No

 **lastUpdatedDateTime**   <a name="lexv2-Type-BotAliasSummary-lastUpdatedDateTime"></a>
A timestamp of the date and time that the bot alias was last updated\.  
Type: Timestamp  
Required: No

## See Also<a name="API_BotAliasSummary_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [ AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/models.lex.v2-2020-08-07/BotAliasSummary) 
+  [ AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/models.lex.v2-2020-08-07/BotAliasSummary) 
+  [ AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/models.lex.v2-2020-08-07/BotAliasSummary) 
+  [ AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/models.lex.v2-2020-08-07/BotAliasSummary) 