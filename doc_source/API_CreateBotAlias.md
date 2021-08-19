# CreateBotAlias<a name="API_CreateBotAlias"></a>

Creates an alias for the specified version of a bot\. Use an alias to enable you to change the version of a bot without updating applications that use the bot\.

For example, you can create an alias called "PROD" that your applications use to call the Amazon Lex bot\. 

## Request Syntax<a name="API_CreateBotAlias_RequestSyntax"></a>

```
PUT /bots/botId/botaliases/ HTTP/1.1
Content-type: application/json

{
   "botAliasLocaleSettings": { 
      "string" : { 
         "codeHookSpecification": { 
            "lambdaCodeHook": { 
               "codeHookInterfaceVersion": "string",
               "lambdaARN": "string"
            }
         },
         "enabled": boolean
      }
   },
   "botAliasName": "string",
   "botVersion": "string",
   "conversationLogSettings": { 
      "audioLogSettings": [ 
         { 
            "destination": { 
               "s3Bucket": { 
                  "kmsKeyArn": "string",
                  "logPrefix": "string",
                  "s3BucketArn": "string"
               }
            },
            "enabled": boolean
         }
      ],
      "textLogSettings": [ 
         { 
            "destination": { 
               "cloudWatch": { 
                  "cloudWatchLogGroupArn": "string",
                  "logPrefix": "string"
               }
            },
            "enabled": boolean
         }
      ]
   },
   "description": "string",
   "sentimentAnalysisSettings": { 
      "detectSentiment": boolean
   },
   "tags": { 
      "string" : "string" 
   }
}
```

## URI Request Parameters<a name="API_CreateBotAlias_RequestParameters"></a>

The request uses the following URI parameters\.

 ** [botId](#API_CreateBotAlias_RequestSyntax) **   <a name="lexv2-CreateBotAlias-request-botId"></a>
The unique identifier of the bot that the alias applies to\.  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$`   
Required: Yes

## Request Body<a name="API_CreateBotAlias_RequestBody"></a>

The request accepts the following data in JSON format\.

 ** [botAliasLocaleSettings](#API_CreateBotAlias_RequestSyntax) **   <a name="lexv2-CreateBotAlias-request-botAliasLocaleSettings"></a>
Maps configuration information to a specific locale\. You can use this parameter to specify a specific Lambda function to run different functions in different locales\.  
Type: String to [BotAliasLocaleSettings](API_BotAliasLocaleSettings.md) object map  
Map Entries: Maximum number of items\.  
Required: No

 ** [botAliasName](#API_CreateBotAlias_RequestSyntax) **   <a name="lexv2-CreateBotAlias-request-botAliasName"></a>
The alias to create\. The name must be unique for the bot\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 100\.  
Pattern: `^([0-9a-zA-Z][_-]?)+$`   
Required: Yes

 ** [botVersion](#API_CreateBotAlias_RequestSyntax) **   <a name="lexv2-CreateBotAlias-request-botVersion"></a>
The version of the bot that this alias points to\. You can use the [UpdateBotAlias](API_UpdateBotAlias.md) operation to change the bot version associated with the alias\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 5\.  
Pattern: `^[0-9]+$`   
Required: No

 ** [conversationLogSettings](#API_CreateBotAlias_RequestSyntax) **   <a name="lexv2-CreateBotAlias-request-conversationLogSettings"></a>
Specifies whether Amazon Lex logs text and audio for a conversation with the bot\. When you enable conversation logs, text logs store text input, transcripts of audio input, and associated metadata in Amazon CloudWatch Logs\. Audio logs store audio input in Amazon S3\.  
Type: [ConversationLogSettings](API_ConversationLogSettings.md) object  
Required: No

 ** [description](#API_CreateBotAlias_RequestSyntax) **   <a name="lexv2-CreateBotAlias-request-description"></a>
A description of the alias\. Use this description to help identify the alias\.  
Type: String  
Length Constraints: Minimum length of 0\. Maximum length of 200\.  
Required: No

 ** [sentimentAnalysisSettings](#API_CreateBotAlias_RequestSyntax) **   <a name="lexv2-CreateBotAlias-request-sentimentAnalysisSettings"></a>
Determines whether Amazon Lex will use Amazon Comprehend to detect the sentiment of user utterances\.  
Type: [SentimentAnalysisSettings](API_SentimentAnalysisSettings.md) object  
Required: No

 ** [tags](#API_CreateBotAlias_RequestSyntax) **   <a name="lexv2-CreateBotAlias-request-tags"></a>
A list of tags to add to the bot alias\. You can only add tags when you create an alias, you can't use the `UpdateBotAlias` operation to update the tags on a bot alias\. To update tags, use the `TagResource` operation\.  
Type: String to string map  
Map Entries: Minimum number of 0 items\. Maximum number of 200 items\.  
Key Length Constraints: Minimum length of 1\. Maximum length of 128\.  
Value Length Constraints: Minimum length of 0\. Maximum length of 256\.  
Required: No

## Response Syntax<a name="API_CreateBotAlias_ResponseSyntax"></a>

```
HTTP/1.1 202
Content-type: application/json

{
   "botAliasId": "string",
   "botAliasLocaleSettings": { 
      "string" : { 
         "codeHookSpecification": { 
            "lambdaCodeHook": { 
               "codeHookInterfaceVersion": "string",
               "lambdaARN": "string"
            }
         },
         "enabled": boolean
      }
   },
   "botAliasName": "string",
   "botAliasStatus": "string",
   "botId": "string",
   "botVersion": "string",
   "conversationLogSettings": { 
      "audioLogSettings": [ 
         { 
            "destination": { 
               "s3Bucket": { 
                  "kmsKeyArn": "string",
                  "logPrefix": "string",
                  "s3BucketArn": "string"
               }
            },
            "enabled": boolean
         }
      ],
      "textLogSettings": [ 
         { 
            "destination": { 
               "cloudWatch": { 
                  "cloudWatchLogGroupArn": "string",
                  "logPrefix": "string"
               }
            },
            "enabled": boolean
         }
      ]
   },
   "creationDateTime": number,
   "description": "string",
   "sentimentAnalysisSettings": { 
      "detectSentiment": boolean
   },
   "tags": { 
      "string" : "string" 
   }
}
```

## Response Elements<a name="API_CreateBotAlias_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 202 response\.

The following data is returned in JSON format by the service\.

 ** [botAliasId](#API_CreateBotAlias_ResponseSyntax) **   <a name="lexv2-CreateBotAlias-response-botAliasId"></a>
The unique identifier of the bot alias\.  
Type: String  
Length Constraints: Fixed length of 10\.  
Pattern: `^(\bTSTALIASID\b|[0-9a-zA-Z]+)$` 

 ** [botAliasLocaleSettings](#API_CreateBotAlias_ResponseSyntax) **   <a name="lexv2-CreateBotAlias-response-botAliasLocaleSettings"></a>
Configuration information for a specific locale\.  
Type: String to [BotAliasLocaleSettings](API_BotAliasLocaleSettings.md) object map  
Map Entries: Maximum number of items\.

 ** [botAliasName](#API_CreateBotAlias_ResponseSyntax) **   <a name="lexv2-CreateBotAlias-response-botAliasName"></a>
The name specified for the bot alias\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 100\.  
Pattern: `^([0-9a-zA-Z][_-]?)+$` 

 ** [botAliasStatus](#API_CreateBotAlias_ResponseSyntax) **   <a name="lexv2-CreateBotAlias-response-botAliasStatus"></a>
The current status of the alias\. The alias is first put into the `Creating` state\. When the alias is ready to be used, it is put into the `Available` state\. You can use the `DescribeBotAlias` operation to get the current state of an alias\.  
Type: String  
Valid Values:` Creating | Available | Deleting | Failed` 

 ** [botId](#API_CreateBotAlias_ResponseSyntax) **   <a name="lexv2-CreateBotAlias-response-botId"></a>
The unique identifier of the bot that this alias applies to\.  
Type: String  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$` 

 ** [botVersion](#API_CreateBotAlias_ResponseSyntax) **   <a name="lexv2-CreateBotAlias-response-botVersion"></a>
The version of the bot associated with this alias\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 5\.  
Pattern: `^[0-9]+$` 

 ** [conversationLogSettings](#API_CreateBotAlias_ResponseSyntax) **   <a name="lexv2-CreateBotAlias-response-conversationLogSettings"></a>
The conversation log settings specified for the alias\.  
Type: [ConversationLogSettings](API_ConversationLogSettings.md) object

 ** [creationDateTime](#API_CreateBotAlias_ResponseSyntax) **   <a name="lexv2-CreateBotAlias-response-creationDateTime"></a>
A Unix timestamp indicating the date and time that the bot alias was created\.  
Type: Timestamp

 ** [description](#API_CreateBotAlias_ResponseSyntax) **   <a name="lexv2-CreateBotAlias-response-description"></a>
The description specified for the bot alias\.  
Type: String  
Length Constraints: Minimum length of 0\. Maximum length of 200\.

 ** [sentimentAnalysisSettings](#API_CreateBotAlias_ResponseSyntax) **   <a name="lexv2-CreateBotAlias-response-sentimentAnalysisSettings"></a>
Determines whether Amazon Lex will use Amazon Comprehend to detect the sentiment of user utterances\.  
Type: [SentimentAnalysisSettings](API_SentimentAnalysisSettings.md) object

 ** [tags](#API_CreateBotAlias_ResponseSyntax) **   <a name="lexv2-CreateBotAlias-response-tags"></a>
A list of tags associated with the bot alias\.  
Type: String to string map  
Map Entries: Minimum number of 0 items\. Maximum number of 200 items\.  
Key Length Constraints: Minimum length of 1\. Maximum length of 128\.  
Value Length Constraints: Minimum length of 0\. Maximum length of 256\.

## Errors<a name="API_CreateBotAlias_Errors"></a>

For information about the errors that are common to all actions, see [Common Errors](CommonErrors.md)\.

 **ConflictException**   
  
HTTP Status Code: 409

 **InternalServerException**   
  
HTTP Status Code: 500

 **PreconditionFailedException**   
  
HTTP Status Code: 412

 **ServiceQuotaExceededException**   
  
HTTP Status Code: 402

 **ThrottlingException**   
  
HTTP Status Code: 429

 **ValidationException**   
  
HTTP Status Code: 400

## See Also<a name="API_CreateBotAlias_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [ AWS Command Line Interface](https://docs.aws.amazon.com/goto/aws-cli/models.lex.v2-2020-08-07/CreateBotAlias) 
+  [ AWS SDK for \.NET](https://docs.aws.amazon.com/goto/DotNetSDKV3/models.lex.v2-2020-08-07/CreateBotAlias) 
+  [ AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/models.lex.v2-2020-08-07/CreateBotAlias) 
+  [ AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/models.lex.v2-2020-08-07/CreateBotAlias) 
+  [ AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/models.lex.v2-2020-08-07/CreateBotAlias) 
+  [ AWS SDK for JavaScript](https://docs.aws.amazon.com/goto/AWSJavaScriptSDK/models.lex.v2-2020-08-07/CreateBotAlias) 
+  [ AWS SDK for PHP V3](https://docs.aws.amazon.com/goto/SdkForPHPV3/models.lex.v2-2020-08-07/CreateBotAlias) 
+  [ AWS SDK for Python](https://docs.aws.amazon.com/goto/boto3/models.lex.v2-2020-08-07/CreateBotAlias) 
+  [ AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/models.lex.v2-2020-08-07/CreateBotAlias) 