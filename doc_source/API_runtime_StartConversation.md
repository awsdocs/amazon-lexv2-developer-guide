# StartConversation<a name="API_runtime_StartConversation"></a>

Starts an HTTP/2 bidirectional event stream that enables you to send audio, text, or DTMF input in real time\. After your application starts a conversation, users send input to Amazon Lex V2 as a stream of events\. Amazon Lex V2 processes the incoming events and responds with streaming text or audio events\. 

Audio input must be in the following format: `audio/lpcm sample-rate=8000 sample-size-bits=16 channel-count=1; is-big-endian=false`\.

The `StartConversation` operation is supported only in the following SDKs: 
+  [AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/runtime.lex.v2-2020-08-07/StartConversation) 
+  [AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/runtime.lex.v2-2020-08-07/StartConversation) 
+  [AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/runtime.lex.v2-2020-08-07/StartConversation) 

## Request Syntax<a name="API_runtime_StartConversation_RequestSyntax"></a>

```
POST /bots/botId/botAliases/botAliasId/botLocales/localeId/sessions/sessionId/conversation HTTP/2
x-amz-lex-conversation-mode: conversationMode
Content-type: application/json

{
   "requestEventStream": { 
      "AudioInputEvent": { 
         "audioChunk": blob,
         "clientTimestampMillis": number,
         "contentType": "string",
         "eventId": "string"
      },
      "ConfigurationEvent": { 
         "clientTimestampMillis": number,
         "disablePlayback": boolean,
         "eventId": "string",
         "requestAttributes": { 
            "string" : "string" 
         },
         "responseContentType": "string",
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
         "welcomeMessages": [ 
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
         ]
      },
      "DisconnectionEvent": { 
         "clientTimestampMillis": number,
         "eventId": "string"
      },
      "DTMFInputEvent": { 
         "clientTimestampMillis": number,
         "eventId": "string",
         "inputCharacter": "string"
      },
      "PlaybackCompletionEvent": { 
         "clientTimestampMillis": number,
         "eventId": "string"
      },
      "TextInputEvent": { 
         "clientTimestampMillis": number,
         "eventId": "string",
         "text": "string"
      }
   }
}
```

## URI Request Parameters<a name="API_runtime_StartConversation_RequestParameters"></a>

The request uses the following URI parameters\.

 ** [botAliasId](#API_runtime_StartConversation_RequestSyntax) **   <a name="lexv2-runtime_StartConversation-request-botAliasId"></a>
The alias identifier in use for the bot that processes the request\.  
Required: Yes

 ** [botId](#API_runtime_StartConversation_RequestSyntax) **   <a name="lexv2-runtime_StartConversation-request-botId"></a>
The identifier of the bot to process the request\.  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$`   
Required: Yes

 ** [conversationMode](#API_runtime_StartConversation_RequestSyntax) **   <a name="lexv2-runtime_StartConversation-request-conversationMode"></a>
The conversation type that you are using the Amazon Lex V2\. If the conversation mode is `AUDIO` you can send both audio and DTMF information\. If the mode is `TEXT` you can only send text\.  
Valid Values:` AUDIO | TEXT` 

 ** [localeId](#API_runtime_StartConversation_RequestSyntax) **   <a name="lexv2-runtime_StartConversation-request-localeId"></a>
The locale where the session is in use\.  
Length Constraints: Minimum length of 1\.  
Required: Yes

 ** [sessionId](#API_runtime_StartConversation_RequestSyntax) **   <a name="lexv2-runtime_StartConversation-request-sessionId"></a>
The identifier of the user session that is having the conversation\.  
Length Constraints: Minimum length of 2\. Maximum length of 100\.  
Pattern: `[0-9a-zA-Z._:-]+`   
Required: Yes

## Request Body<a name="API_runtime_StartConversation_RequestBody"></a>

The request accepts the following data in JSON format\.

 ** [requestEventStream](#API_runtime_StartConversation_RequestSyntax) **   <a name="lexv2-runtime_StartConversation-request-requestEventStream"></a>
Represents the stream of events to Amazon Lex V2 from your application\. The events are encoded as HTTP/2 data frames\.  
Type: [StartConversationRequestEventStream](API_runtime_StartConversationRequestEventStream.md) object  
Required: Yes

## Response Syntax<a name="API_runtime_StartConversation_ResponseSyntax"></a>

```
HTTP/2 200
Content-type: application/json

{
   "responseEventStream": { 
      "AccessDeniedException": { 
      },
      "AudioResponseEvent": { 
         "audioChunk": blob,
         "contentType": "string",
         "eventId": "string"
      },
      "BadGatewayException": { 
      },
      "ConflictException": { 
      },
      "DependencyFailedException": { 
      },
      "HeartbeatEvent": { 
         "eventId": "string"
      },
      "IntentResultEvent": { 
         "eventId": "string",
         "inputMode": "string",
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
      },
      "InternalServerException": { 
      },
      "PlaybackInterruptionEvent": { 
         "causedByEventId": "string",
         "eventId": "string",
         "eventReason": "string"
      },
      "ResourceNotFoundException": { 
      },
      "TextResponseEvent": { 
         "eventId": "string",
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
         ]
      },
      "ThrottlingException": { 
      },
      "TranscriptEvent": { 
         "eventId": "string",
         "transcript": "string"
      },
      "ValidationException": { 
      }
   }
}
```

## Response Elements<a name="API_runtime_StartConversation_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 200 response\.

The following data is returned in JSON format by the service\.

 ** [responseEventStream](#API_runtime_StartConversation_ResponseSyntax) **   <a name="lexv2-runtime_StartConversation-response-responseEventStream"></a>
Represents the stream of events from Amazon Lex V2 to your application\. The events are encoded as HTTP/2 data frames\.  
Type: [StartConversationResponseEventStream](API_runtime_StartConversationResponseEventStream.md) object

## Errors<a name="API_runtime_StartConversation_Errors"></a>

For information about the errors that are common to all actions, see [Common Errors](CommonErrors.md)\.

 **AccessDeniedException**   
  
HTTP Status Code: 403

 **InternalServerException**   
  
HTTP Status Code: 500

 **ThrottlingException**   
  
HTTP Status Code: 429

 **ValidationException**   
  
HTTP Status Code: 400

## See Also<a name="API_runtime_StartConversation_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [ AWS Command Line Interface](https://docs.aws.amazon.com/goto/aws-cli/runtime.lex.v2-2020-08-07/StartConversation) 
+  [ AWS SDK for \.NET](https://docs.aws.amazon.com/goto/DotNetSDKV3/runtime.lex.v2-2020-08-07/StartConversation) 
+  [ AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/runtime.lex.v2-2020-08-07/StartConversation) 
+  [ AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/runtime.lex.v2-2020-08-07/StartConversation) 
+  [ AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/runtime.lex.v2-2020-08-07/StartConversation) 
+  [ AWS SDK for JavaScript](https://docs.aws.amazon.com/goto/AWSJavaScriptSDK/runtime.lex.v2-2020-08-07/StartConversation) 
+  [ AWS SDK for PHP V3](https://docs.aws.amazon.com/goto/SdkForPHPV3/runtime.lex.v2-2020-08-07/StartConversation) 
+  [ AWS SDK for Python](https://docs.aws.amazon.com/goto/boto3/runtime.lex.v2-2020-08-07/StartConversation) 
+  [ AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/runtime.lex.v2-2020-08-07/StartConversation) 