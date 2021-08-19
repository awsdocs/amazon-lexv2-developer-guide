# BotImportSpecification<a name="API_BotImportSpecification"></a>

Provides the bot parameters required for importing a bot\.

## Contents<a name="API_BotImportSpecification_Contents"></a>

 **botName**   <a name="lexv2-Type-BotImportSpecification-botName"></a>
The name that Amazon Lex should use for the bot\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 100\.  
Pattern: `^([0-9a-zA-Z][_-]?)+$`   
Required: Yes

 **botTags**   <a name="lexv2-Type-BotImportSpecification-botTags"></a>
A list of tags to add to the bot\. You can only add tags when you import a bot\. You can't use the `UpdateBot` operation to update tags\. To update tags, use the `TagResource` operation\.  
Type: String to string map  
Map Entries: Minimum number of 0 items\. Maximum number of 200 items\.  
Key Length Constraints: Minimum length of 1\. Maximum length of 128\.  
Value Length Constraints: Minimum length of 0\. Maximum length of 256\.  
Required: No

 **dataPrivacy**   <a name="lexv2-Type-BotImportSpecification-dataPrivacy"></a>
By default, data stored by Amazon Lex is encrypted\. The `DataPrivacy` structure provides settings that determine how Amazon Lex handles special cases of securing the data for your bot\.   
Type: [DataPrivacy](API_DataPrivacy.md) object  
Required: Yes

 **idleSessionTTLInSeconds**   <a name="lexv2-Type-BotImportSpecification-idleSessionTTLInSeconds"></a>
The time, in seconds, that Amazon Lex should keep information about a user's conversation with the bot\.   
A user interaction remains active for the amount of time specified\. If no conversation occurs during this time, the session expires and Amazon Lex deletes any data provided before the timeout\.  
You can specify between 60 \(1 minute\) and 86,400 \(24 hours\) seconds\.  
Type: Integer  
Valid Range: Minimum value of 60\. Maximum value of 86400\.  
Required: No

 **roleArn**   <a name="lexv2-Type-BotImportSpecification-roleArn"></a>
The Amazon Resource Name \(ARN\) of the IAM role used to build and run the bot\.  
Type: String  
Length Constraints: Minimum length of 32\. Maximum length of 2048\.  
Pattern: `^arn:aws:iam::[0-9]{12}:role/.*$`   
Required: Yes

 **testBotAliasTags**   <a name="lexv2-Type-BotImportSpecification-testBotAliasTags"></a>
A list of tags to add to the test alias for a bot\. You can only add tags when you import a bot\. You can't use the `UpdateAlias` operation to update tags\. To update tags on the test alias, use the `TagResource` operation\.  
Type: String to string map  
Map Entries: Minimum number of 0 items\. Maximum number of 200 items\.  
Key Length Constraints: Minimum length of 1\. Maximum length of 128\.  
Value Length Constraints: Minimum length of 0\. Maximum length of 256\.  
Required: No

## See Also<a name="API_BotImportSpecification_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [ AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/models.lex.v2-2020-08-07/BotImportSpecification) 
+  [ AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/models.lex.v2-2020-08-07/BotImportSpecification) 
+  [ AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/models.lex.v2-2020-08-07/BotImportSpecification) 
+  [ AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/models.lex.v2-2020-08-07/BotImportSpecification) 