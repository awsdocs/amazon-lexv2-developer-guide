# BotSummary<a name="API_BotSummary"></a>

Summary information about a bot returned by the [ListBots](API_ListBots.md) operation\.

## Contents<a name="API_BotSummary_Contents"></a>

 **botId**   <a name="lexv2-Type-BotSummary-botId"></a>
The unique identifier assigned to the bot\. Use this ID to get detailed information about the bot with the [DescribeBot](API_DescribeBot.md) operation\.  
Type: String  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$`   
Required: No

 **botName**   <a name="lexv2-Type-BotSummary-botName"></a>
The name of the bot\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 100\.  
Pattern: `^([0-9a-zA-Z][_-]?)+$`   
Required: No

 **botStatus**   <a name="lexv2-Type-BotSummary-botStatus"></a>
The current status of the bot\. When the status is `Available` the bot is ready for use\.  
Type: String  
Valid Values:` Creating | Available | Inactive | Deleting | Failed | Versioning`   
Required: No

 **description**   <a name="lexv2-Type-BotSummary-description"></a>
The description of the bot\.  
Type: String  
Length Constraints: Minimum length of 0\. Maximum length of 200\.  
Required: No

 **lastUpdatedDateTime**   <a name="lexv2-Type-BotSummary-lastUpdatedDateTime"></a>
The date and time that the bot was last updated\.  
Type: Timestamp  
Required: No

 **latestBotVersion**   <a name="lexv2-Type-BotSummary-latestBotVersion"></a>
The latest numerical version in use for the bot\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 5\.  
Pattern: `^[0-9]+$`   
Required: No

## See Also<a name="API_BotSummary_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/models.lex.v2-2020-08-07/BotSummary) 
+  [AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/models.lex.v2-2020-08-07/BotSummary) 
+  [AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/models.lex.v2-2020-08-07/BotSummary) 
+  [AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/models.lex.v2-2020-08-07/BotSummary) 