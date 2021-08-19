# GetSession<a name="API_runtime_GetSession"></a>

Returns session information for a specified bot, alias, and user\.

For example, you can use this operation to retrieve session information for a user that has left a long\-running session in use\.

If the bot, alias, or session identifier doesn't exist, Amazon Lex V2 returns a `BadRequestException`\. If the locale doesn't exist or is not enabled for the alias, you receive a `BadRequestException`\.

## Request Syntax<a name="API_runtime_GetSession_RequestSyntax"></a>

```
GET /bots/botId/botAliases/botAliasId/botLocales/localeId/sessions/sessionId HTTP/1.1
```

## URI Request Parameters<a name="API_runtime_GetSession_RequestParameters"></a>

The request uses the following URI parameters\.

 ** [botAliasId](#API_runtime_GetSession_RequestSyntax) **   <a name="lexv2-runtime_GetSession-request-botAliasId"></a>
The alias identifier in use for the bot that contains the session data\.  
Required: Yes

 ** [botId](#API_runtime_GetSession_RequestSyntax) **   <a name="lexv2-runtime_GetSession-request-botId"></a>
The identifier of the bot that contains the session data\.  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$`   
Required: Yes

 ** [localeId](#API_runtime_GetSession_RequestSyntax) **   <a name="lexv2-runtime_GetSession-request-localeId"></a>
The locale where the session is in use\.  
Length Constraints: Minimum length of 1\.  
Required: Yes

 ** [sessionId](#API_runtime_GetSession_RequestSyntax) **   <a name="lexv2-runtime_GetSession-request-sessionId"></a>
The identifier of the session to return\.  
Length Constraints: Minimum length of 2\. Maximum length of 100\.  
Pattern: `[0-9a-zA-Z._:-]+`   
Required: Yes

## Request Body<a name="API_runtime_GetSession_RequestBody"></a>

The request does not have a request body\.

## Response Syntax<a name="API_runtime_GetSession_ResponseSyntax"></a>

```
HTTP/1.1 200
Content-type: application/json

{
   "interpretations": [ 
      { 
         "intent": { 
            "confirmationState": "string",
            "name": "string",
            "slots": { 
               "string" : { 
                  "shape": "string",
                  "value": { 
                     "interpretedValue": "string",
                     "originalValue": "string",
                     "resolvedValues": [ "string" ]
                  },
                  "values": [ 
                     "Slot"
                  ]
               }
            },
            "state": "string"
         },
         "nluConfidence": { 
            "score": number
         },
         "sentimentResponse": { 
            "sentiment": "string",
            "sentimentScore": { 
               "mixed": number,
               "negative": number,
               "neutral": number,
               "positive": number
            }
         }
      }
   ],
   "messages": [ 
      { 
         "content": "string",
         "contentType": "string",
         "imageResponseCard": { 
            "buttons": [ 
               { 
                  "text": "string",
                  "value": "string"
               }
            ],
            "imageUrl": "string",
            "subtitle": "string",
            "title": "string"
         }
      }
   ],
   "sessionId": "string",
   "sessionState": { 
      "activeContexts": [ 
         { 
            "contextAttributes": { 
               "string" : "string" 
            },
            "name": "string",
            "timeToLive": { 
               "timeToLiveInSeconds": number,
               "turnsToLive": number
            }
         }
      ],
      "dialogAction": { 
         "slotToElicit": "string",
         "type": "string"
      },
      "intent": { 
         "confirmationState": "string",
         "name": "string",
         "slots": { 
            "string" : { 
               "shape": "string",
               "value": { 
                  "interpretedValue": "string",
                  "originalValue": "string",
                  "resolvedValues": [ "string" ]
               },
               "values": [ 
                  "Slot"
               ]
            }
         },
         "state": "string"
      },
      "originatingRequestId": "string",
      "sessionAttributes": { 
         "string" : "string" 
      }
   }
}
```

## Response Elements<a name="API_runtime_GetSession_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 200 response\.

The following data is returned in JSON format by the service\.

 ** [interpretations](#API_runtime_GetSession_ResponseSyntax) **   <a name="lexv2-runtime_GetSession-response-interpretations"></a>
A list of intents that Amazon Lex V2 determined might satisfy the user's utterance\.   
Each interpretation includes the intent, a score that indicates how confident Amazon Lex V2 is that the interpretation is the correct one, and an optional sentiment response that indicates the sentiment expressed in the utterance\.  
Type: Array of [Interpretation](API_runtime_Interpretation.md) objects  
Array Members: Maximum number of 5 items\.

 ** [messages](#API_runtime_GetSession_ResponseSyntax) **   <a name="lexv2-runtime_GetSession-response-messages"></a>
A list of messages that were last sent to the user\. The messages are ordered based on the order that your returned the messages from your Lambda function or the order that messages are defined in the bot\.   
Type: Array of [Message](API_runtime_Message.md) objects  
Array Members: Maximum number of 10 items\.

 ** [sessionId](#API_runtime_GetSession_ResponseSyntax) **   <a name="lexv2-runtime_GetSession-response-sessionId"></a>
The identifier of the returned session\.  
Type: String  
Length Constraints: Minimum length of 1\.

 ** [sessionState](#API_runtime_GetSession_ResponseSyntax) **   <a name="lexv2-runtime_GetSession-response-sessionState"></a>
Represents the current state of the dialog between the user and the bot\.  
You can use this to determine the progress of the conversation and what the next action might be\.  
Type: [SessionState](API_runtime_SessionState.md) object

## Errors<a name="API_runtime_GetSession_Errors"></a>

For information about the errors that are common to all actions, see [Common Errors](CommonErrors.md)\.

 **AccessDeniedException**   
  
HTTP Status Code: 403

 **InternalServerException**   
  
HTTP Status Code: 500

 **ResourceNotFoundException**   
  
HTTP Status Code: 404

 **ThrottlingException**   
  
HTTP Status Code: 429

 **ValidationException**   
  
HTTP Status Code: 400

## See Also<a name="API_runtime_GetSession_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [ AWS Command Line Interface](https://docs.aws.amazon.com/goto/aws-cli/runtime.lex.v2-2020-08-07/GetSession) 
+  [ AWS SDK for \.NET](https://docs.aws.amazon.com/goto/DotNetSDKV3/runtime.lex.v2-2020-08-07/GetSession) 
+  [ AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/runtime.lex.v2-2020-08-07/GetSession) 
+  [ AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/runtime.lex.v2-2020-08-07/GetSession) 
+  [ AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/runtime.lex.v2-2020-08-07/GetSession) 
+  [ AWS SDK for JavaScript](https://docs.aws.amazon.com/goto/AWSJavaScriptSDK/runtime.lex.v2-2020-08-07/GetSession) 
+  [ AWS SDK for PHP V3](https://docs.aws.amazon.com/goto/SdkForPHPV3/runtime.lex.v2-2020-08-07/GetSession) 
+  [ AWS SDK for Python](https://docs.aws.amazon.com/goto/boto3/runtime.lex.v2-2020-08-07/GetSession) 
+  [ AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/runtime.lex.v2-2020-08-07/GetSession) 