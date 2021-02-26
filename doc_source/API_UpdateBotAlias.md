# UpdateBotAlias<a name="API_UpdateBotAlias"></a>

Updates the configuration of an existing bot alias\.

## Request Syntax<a name="API_UpdateBotAlias_RequestSyntax"></a>

```
PUT /bots/botId/botaliases/botAliasId/ HTTP/1.1
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
   }
}
```

## URI Request Parameters<a name="API_UpdateBotAlias_RequestParameters"></a>

The request uses the following URI parameters\.

 ** [botAliasId](#API_UpdateBotAlias_RequestSyntax) **   <a name="lexv2-UpdateBotAlias-request-botAliasId"></a>
The unique identifier of the bot alias\.  
Length Constraints: Fixed length of 10\.  
Pattern: `^(\bTSTALIASID\b|[0-9a-zA-Z]+)$`   
Required: Yes

 ** [botId](#API_UpdateBotAlias_RequestSyntax) **   <a name="lexv2-UpdateBotAlias-request-botId"></a>
The identifier of the bot with the updated alias\.  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$`   
Required: Yes

## Request Body<a name="API_UpdateBotAlias_RequestBody"></a>

The request accepts the following data in JSON format\.

 ** [botAliasLocaleSettings](#API_UpdateBotAlias_RequestSyntax) **   <a name="lexv2-UpdateBotAlias-request-botAliasLocaleSettings"></a>
The new Lambda functions to use in each locale for the bot alias\.  
Type: String to [BotAliasLocaleSettings](API_BotAliasLocaleSettings.md) object map  
Map Entries: Maximum number of items\.  
Required: No

 ** [botAliasName](#API_UpdateBotAlias_RequestSyntax) **   <a name="lexv2-UpdateBotAlias-request-botAliasName"></a>
The new name to assign to the bot alias\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 100\.  
Pattern: `^([0-9a-zA-Z][_-]?)+$`   
Required: Yes

 ** [botVersion](#API_UpdateBotAlias_RequestSyntax) **   <a name="lexv2-UpdateBotAlias-request-botVersion"></a>
The new bot version to assign to the bot alias\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 5\.  
Pattern: `^(DRAFT|[0-9]+)$`   
Required: No

 ** [conversationLogSettings](#API_UpdateBotAlias_RequestSyntax) **   <a name="lexv2-UpdateBotAlias-request-conversationLogSettings"></a>
The new settings for storing conversation logs in Amazon CloudWatch Logs and Amazon S3 buckets\.  
Type: [ConversationLogSettings](API_ConversationLogSettings.md) object  
Required: No

 ** [description](#API_UpdateBotAlias_RequestSyntax) **   <a name="lexv2-UpdateBotAlias-request-description"></a>
The new description to assign to the bot alias\.  
Type: String  
Length Constraints: Minimum length of 0\. Maximum length of 200\.  
Required: No

 ** [sentimentAnalysisSettings](#API_UpdateBotAlias_RequestSyntax) **   <a name="lexv2-UpdateBotAlias-request-sentimentAnalysisSettings"></a>
Determines whether Amazon Lex will use Amazon Comprehend to detect the sentiment of user utterances\.  
Type: [SentimentAnalysisSettings](API_SentimentAnalysisSettings.md) object  
Required: No

## Response Syntax<a name="API_UpdateBotAlias_ResponseSyntax"></a>

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
   "lastUpdatedDateTime": number,
   "sentimentAnalysisSettings": { 
      "detectSentiment": boolean
   }
}
```

## Response Elements<a name="API_UpdateBotAlias_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 202 response\.

The following data is returned in JSON format by the service\.

 ** [botAliasId](#API_UpdateBotAlias_ResponseSyntax) **   <a name="lexv2-UpdateBotAlias-response-botAliasId"></a>
The identifier of the updated bot alias\.  
Type: String  
Length Constraints: Fixed length of 10\.  
Pattern: `^(\bTSTALIASID\b|[0-9a-zA-Z]+)$` 

 ** [botAliasLocaleSettings](#API_UpdateBotAlias_ResponseSyntax) **   <a name="lexv2-UpdateBotAlias-response-botAliasLocaleSettings"></a>
The updated Lambda functions to use in each locale for the bot alias\.  
Type: String to [BotAliasLocaleSettings](API_BotAliasLocaleSettings.md) object map  
Map Entries: Maximum number of items\.

 ** [botAliasName](#API_UpdateBotAlias_ResponseSyntax) **   <a name="lexv2-UpdateBotAlias-response-botAliasName"></a>
The updated name of the bot alias\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 100\.  
Pattern: `^([0-9a-zA-Z][_-]?)+$` 

 ** [botAliasStatus](#API_UpdateBotAlias_ResponseSyntax) **   <a name="lexv2-UpdateBotAlias-response-botAliasStatus"></a>
The current status of the bot alias\. When the status is `Available` the alias is ready for use\.  
Type: String  
Valid Values:` Creating | Available | Deleting | Failed` 

 ** [botId](#API_UpdateBotAlias_ResponseSyntax) **   <a name="lexv2-UpdateBotAlias-response-botId"></a>
The identifier of the bot with the updated alias\.  
Type: String  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$` 

 ** [botVersion](#API_UpdateBotAlias_ResponseSyntax) **   <a name="lexv2-UpdateBotAlias-response-botVersion"></a>
The updated version of the bot that the alias points to\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 5\.  
Pattern: `^(DRAFT|[0-9]+)$` 

 ** [conversationLogSettings](#API_UpdateBotAlias_ResponseSyntax) **   <a name="lexv2-UpdateBotAlias-response-conversationLogSettings"></a>
The updated settings for storing conversation logs in Amazon CloudWatch Logs and Amazon S3 buckets\.  
Type: [ConversationLogSettings](API_ConversationLogSettings.md) object

 ** [creationDateTime](#API_UpdateBotAlias_ResponseSyntax) **   <a name="lexv2-UpdateBotAlias-response-creationDateTime"></a>
A timestamp of the date and time that the bot was created\.  
Type: Timestamp

 ** [description](#API_UpdateBotAlias_ResponseSyntax) **   <a name="lexv2-UpdateBotAlias-response-description"></a>
The updated description of the bot alias\.  
Type: String  
Length Constraints: Minimum length of 0\. Maximum length of 200\.

 ** [lastUpdatedDateTime](#API_UpdateBotAlias_ResponseSyntax) **   <a name="lexv2-UpdateBotAlias-response-lastUpdatedDateTime"></a>
A timestamp of the date and time that the bot was last updated\.  
Type: Timestamp

 ** [sentimentAnalysisSettings](#API_UpdateBotAlias_ResponseSyntax) **   <a name="lexv2-UpdateBotAlias-response-sentimentAnalysisSettings"></a>
Determines whether Amazon Lex will use Amazon Comprehend to detect the sentiment of user utterances\.  
Type: [SentimentAnalysisSettings](API_SentimentAnalysisSettings.md) object

## Errors<a name="API_UpdateBotAlias_Errors"></a>

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

## See Also<a name="API_UpdateBotAlias_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [AWS Command Line Interface](https://docs.aws.amazon.com/goto/aws-cli/models.lex.v2-2020-08-07/UpdateBotAlias) 
+  [AWS SDK for \.NET](https://docs.aws.amazon.com/goto/DotNetSDKV3/models.lex.v2-2020-08-07/UpdateBotAlias) 
+  [AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/models.lex.v2-2020-08-07/UpdateBotAlias) 
+  [AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/models.lex.v2-2020-08-07/UpdateBotAlias) 
+  [AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/models.lex.v2-2020-08-07/UpdateBotAlias) 
+  [AWS SDK for JavaScript](https://docs.aws.amazon.com/goto/AWSJavaScriptSDK/models.lex.v2-2020-08-07/UpdateBotAlias) 
+  [AWS SDK for PHP V3](https://docs.aws.amazon.com/goto/SdkForPHPV3/models.lex.v2-2020-08-07/UpdateBotAlias) 
+  [AWS SDK for Python](https://docs.aws.amazon.com/goto/boto3/models.lex.v2-2020-08-07/UpdateBotAlias) 
+  [AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/models.lex.v2-2020-08-07/UpdateBotAlias) 