# BotAliasHistoryEvent<a name="API_BotAliasHistoryEvent"></a>

Provides a record of an event that affects a bot alias\. For example, when the version of a bot that the alias points to changes\.

## Contents<a name="API_BotAliasHistoryEvent_Contents"></a>

 **botVersion**   <a name="lexv2-Type-BotAliasHistoryEvent-botVersion"></a>
The version of the bot that was used in the event\.   
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 5\.  
Pattern: `^(DRAFT|[0-9]+)$`   
Required: No

 **endDate**   <a name="lexv2-Type-BotAliasHistoryEvent-endDate"></a>
The date and time that the event ended\.  
Type: Timestamp  
Required: No

 **startDate**   <a name="lexv2-Type-BotAliasHistoryEvent-startDate"></a>
The date and time that the event started\.  
Type: Timestamp  
Required: No

## See Also<a name="API_BotAliasHistoryEvent_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [ AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/models.lex.v2-2020-08-07/BotAliasHistoryEvent) 
+  [ AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/models.lex.v2-2020-08-07/BotAliasHistoryEvent) 
+  [ AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/models.lex.v2-2020-08-07/BotAliasHistoryEvent) 
+  [ AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/models.lex.v2-2020-08-07/BotAliasHistoryEvent) 