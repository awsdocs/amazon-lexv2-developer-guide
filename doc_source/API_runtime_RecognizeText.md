# RecognizeText<a name="API_runtime_RecognizeText"></a>

Sends user input to Amazon Lex V2\. Client applications use this API to send requests to Amazon Lex V2 at runtime\. Amazon Lex V2 then interprets the user input using the machine learning model that it build for the bot\.

In response, Amazon Lex V2 returns the next message to convey to the user and an optional response card to display\.

## Request Syntax<a name="API_runtime_RecognizeText_RequestSyntax"></a>

```
POST /bots/botId/botAliases/botAliasId/botLocales/localeId/sessions/sessionId/text HTTP/1.1
Content-type: application/json

{
   "requestAttributes": { 
      "string" : "string" 
   },
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
   },
   "text": "string"
}
```

## URI Request Parameters<a name="API_runtime_RecognizeText_RequestParameters"></a>

The request uses the following URI parameters\.

 ** [botAliasId](#API_runtime_RecognizeText_RequestSyntax) **   <a name="lexv2-runtime_RecognizeText-request-botAliasId"></a>
The alias identifier in use for the bot that processes the request\.  
Required: Yes

 ** [botId](#API_runtime_RecognizeText_RequestSyntax) **   <a name="lexv2-runtime_RecognizeText-request-botId"></a>
The identifier of the bot that processes the request\.  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$`   
Required: Yes

 ** [localeId](#API_runtime_RecognizeText_RequestSyntax) **   <a name="lexv2-runtime_RecognizeText-request-localeId"></a>
The locale where the session is in use\.  
Length Constraints: Minimum length of 1\.  
Required: Yes

 ** [sessionId](#API_runtime_RecognizeText_RequestSyntax) **   <a name="lexv2-runtime_RecognizeText-request-sessionId"></a>
The identifier of the user session that is having the conversation\.  
Length Constraints: Minimum length of 2\. Maximum length of 100\.  
Pattern: `[0-9a-zA-Z._:-]+`   
Required: Yes

## Request Body<a name="API_runtime_RecognizeText_RequestBody"></a>

The request accepts the following data in JSON format\.

 ** [requestAttributes](#API_runtime_RecognizeText_RequestSyntax) **   <a name="lexv2-runtime_RecognizeText-request-requestAttributes"></a>
Request\-specific information passed between the client application and Amazon Lex V2   
The namespace `x-amz-lex:` is reserved for special attributes\. Don't create any request attributes with the prefix `x-amz-lex:`\.  
Type: String to string map  
Key Length Constraints: Minimum length of 1\.  
Required: No

 ** [sessionState](#API_runtime_RecognizeText_RequestSyntax) **   <a name="lexv2-runtime_RecognizeText-request-sessionState"></a>
The current state of the dialog between the user and the bot\.  
Type: [SessionState](API_runtime_SessionState.md) object  
Required: No

 ** [text](#API_runtime_RecognizeText_RequestSyntax) **   <a name="lexv2-runtime_RecognizeText-request-text"></a>
The text that the user entered\. Amazon Lex V2 interprets this text\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 1024\.  
Required: Yes

## Response Syntax<a name="API_runtime_RecognizeText_ResponseSyntax"></a>

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
   "requestAttributes": { 
      "string" : "string" 
   },
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

## Response Elements<a name="API_runtime_RecognizeText_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 200 response\.

The following data is returned in JSON format by the service\.

 ** [interpretations](#API_runtime_RecognizeText_ResponseSyntax) **   <a name="lexv2-runtime_RecognizeText-response-interpretations"></a>
A list of intents that Amazon Lex V2 determined might satisfy the user's utterance\.   
Each interpretation includes the intent, a score that indicates now confident Amazon Lex V2 is that the interpretation is the correct one, and an optional sentiment response that indicates the sentiment expressed in the utterance\.  
Type: Array of [Interpretation](API_runtime_Interpretation.md) objects  
Array Members: Maximum number of 5 items\.

 ** [messages](#API_runtime_RecognizeText_ResponseSyntax) **   <a name="lexv2-runtime_RecognizeText-response-messages"></a>
A list of messages last sent to the user\. The messages are ordered based on the order that you returned the messages from your Lambda function or the order that the messages are defined in the bot\.  
Type: Array of [Message](API_runtime_Message.md) objects  
Array Members: Maximum number of 10 items\.

 ** [requestAttributes](#API_runtime_RecognizeText_ResponseSyntax) **   <a name="lexv2-runtime_RecognizeText-response-requestAttributes"></a>
The attributes sent in the request\.  
Type: String to string map  
Key Length Constraints: Minimum length of 1\.

 ** [sessionId](#API_runtime_RecognizeText_ResponseSyntax) **   <a name="lexv2-runtime_RecognizeText-response-sessionId"></a>
The identifier of the session in use\.  
Type: String  
Length Constraints: Minimum length of 2\. Maximum length of 100\.  
Pattern: `[0-9a-zA-Z._:-]+` 

 ** [sessionState](#API_runtime_RecognizeText_ResponseSyntax) **   <a name="lexv2-runtime_RecognizeText-response-sessionState"></a>
Represents the current state of the dialog between the user and the bot\.   
Use this to determine the progress of the conversation and what the next action may be\.  
Type: [SessionState](API_runtime_SessionState.md) object

## Errors<a name="API_runtime_RecognizeText_Errors"></a>

For information about the errors that are common to all actions, see [Common Errors](CommonErrors.md)\.

 **AccessDeniedException**   
  
HTTP Status Code: 403

 **BadGatewayException**   
  
HTTP Status Code: 502

 **ConflictException**   
  
HTTP Status Code: 409

 **DependencyFailedException**   
  
HTTP Status Code: 424

 **InternalServerException**   
  
HTTP Status Code: 500

 **ResourceNotFoundException**   
  
HTTP Status Code: 404

 **ThrottlingException**   
  
HTTP Status Code: 429

 **ValidationException**   
  
HTTP Status Code: 400

## See Also<a name="API_runtime_RecognizeText_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [ AWS Command Line Interface](https://docs.aws.amazon.com/goto/aws-cli/runtime.lex.v2-2020-08-07/RecognizeText) 
+  [ AWS SDK for \.NET](https://docs.aws.amazon.com/goto/DotNetSDKV3/runtime.lex.v2-2020-08-07/RecognizeText) 
+  [ AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/runtime.lex.v2-2020-08-07/RecognizeText) 
+  [ AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/runtime.lex.v2-2020-08-07/RecognizeText) 
+  [ AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/runtime.lex.v2-2020-08-07/RecognizeText) 
+  [ AWS SDK for JavaScript](https://docs.aws.amazon.com/goto/AWSJavaScriptSDK/runtime.lex.v2-2020-08-07/RecognizeText) 
+  [ AWS SDK for PHP V3](https://docs.aws.amazon.com/goto/SdkForPHPV3/runtime.lex.v2-2020-08-07/RecognizeText) 
+  [ AWS SDK for Python](https://docs.aws.amazon.com/goto/boto3/runtime.lex.v2-2020-08-07/RecognizeText) 
+  [ AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/runtime.lex.v2-2020-08-07/RecognizeText) 