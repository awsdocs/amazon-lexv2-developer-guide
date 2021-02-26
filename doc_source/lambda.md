# Using a AWS Lambda function<a name="lambda"></a>

This section describes the structure of the event data that Amazon Lex provides to a Lambda function\. Use this information to parse the input to your Lambda code\. It also explains the format of the response that Amazon Lex expects your Lambda function to return\.

**Topics**
+ [Input event format](#lambda-input-format)
+ [Response format](#lambda-response-format)

## Input event format<a name="lambda-input-format"></a>

The following is the general format of an Amazon Lex event that is passed to a Lambda function\. Use this information when you're writing you Lambda function\.

**Note**  
The input format may change without a corresponding change to the `messageVersion`\. Your code shouldn't throw an error if new fields are present\.

```
{
    "messageVersion": "2.0",
    "invocationSource": "DialogCodeHook | FulfillmentCodeHook",
    "inputMode": "DTMF | Speech | Text",
    "responseContentType": "CustomPayload | ImageResponseCard | PlainText | SSML",
    "sessionId": "string",
    "inputTranscript": "string",
    "bot": {
        "id": "string",
        "name": "string",
        "aliasId": "string",
        "localeId": "string",
        "version": "string"
    },
    "interpretations": [
        {
            "intent": {
                "confirmationState": "Confirmed | Denied | None",
                "name":"string",
                "slots": {
                    "value": {
                        "interpretedValue": "string",
                        "originalValue": "string",
                        "resovledValues": "string"
                    }
                },
                "state": "Failed | Fulfilled | InProgress | ReadyForFulfillment",
                "kendraResponse": {
                    // Only present when intent is KendraSearchIntent. For details, see 
                    // https://docs.aws.amazon.com/kendra/latest/dg/API_Query.html#API_Query_ResponseSyntax
                }
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
        "string": "string"
    },
    "sessionState": {
        "activeContexts": [ 
            { 
               "name": "string",
               "contextAttributes": { 
                  "string" : "string" 
               },
               "timeToLive": { 
                  "timeToLiveInSeconds": number,
                  "turnsToLive": number
               }
            }
         ],
         "sessionAttributes": { 
            "string" : "string" 
         },
         "dialogAction": { 
            "slotToElicit": "string",
            "type": "Close | ConfirmIntent | Delegate | ElicitIntent | ElicitSlot"
         },
         "intent": { 
            "confirmationState": "Confirmed | Denied | None",
            "name": "string",
            "slots": { 
               "string" : { 
                  "value": { 
                     "interpretedValue": "string",
                     "originalValue": "string",
                     "resolvedValues": [ "string" ]
                  }
               }
            },
            "state": "Failed | Fulfilled | InProgress | ReadyForFulfillment",
            "kendraResponse": {
                // Only present when intent is KendraSearchIntent. For details, see
                // https://docs.aws.amazon.com/kendra/latest/dg/API_Query.html#API_Query_ResponseSyntax                     }
            },
         "originatingRequestId": "string"
       }
    }
}
```

Note the following additional information about the event fields:
+ **invocationSource** – Indicates the action that called the Lambda function\. When the source is `DialogCodeHook`, the Lambda function was called after input from the user\. When the source is `FulfillmentCodeHook` the Lambda function was called after all required slots have been filled and the intent is ready for fulfillment\.
+ **inputTranscript** – The text that was used to process the input from the user\. For text or DTMF input, this is the text that the user typed\. For speech input, this is the text that was recognized from the speech\.
+ **interpretations** – One or more intents that Amazon Lex considers possible matches to the user's utterance\. For more information, see [Interpretation](API_runtime_Interpretation.md)\.
+ **requestAttributes** – Request\-specific attributes that the client sends in the request\. Use request attributes to pass information that doesn't need to persist for the entire session\.
+ **sessionState** – The current state of the conversation between the user and your Amazon Lex bot\. For more information about the session state, see [SessionState](API_runtime_SessionState.md)\.

## Response format<a name="lambda-response-format"></a>

Amazon Lex expects a response from you Lambda function in the following format:

```
{
    "sessionState": {
        "activeContexts": [
            {
                "name": "string",
                "contextAttributes": {
                    "key": "value"
                },
                "timeToLive": {
                    "timeToLiveInSeconds": number,
                    "turnsToLive": number
                }
            }
        ],
        "sessionAttributes": {
            "string": "string"
        },
        "dialogAction": { 
            "slotToElicit": "string",
            "type": "Close | ConfirmIntent | Delegate | ElicitIntent | ElicitSlot"
         },
         "intent": { 
            "confirmationState": "Confirmed | Denied | None",
            "name": "string",
            "slots": { 
               "string" : { 
                  "value": { 
                     "interpretedValue": "string",
                     "originalValue": "string",
                     "resolvedValues": [ "string" ]
                  }
               }
            },
            "state": "Failed | Fulfilled | InProgress | ReadyForFulfillment"
        }
    },
    "messages": [
        {
            "contentType": "CustomPayload | ImageResponseCard | PlainText | SSML",
            "content": "string",
            "imageResponseCard": {
                "title": "string",
                "subtitle": "string",
                "imageUrl": "string",
                "buttonsList": [
                    {
                        "text": "string",
                        "value": "string"
                    }
                ]
            }
        }
    ],
    "requestAttributes": {
        "string": "string"
    }
}
```

Note the following additional information about the response fields:
+ **sessionState** – Required\. The current state of the conversation with the user\. The actual contents of the structure depends on the type of dialog action\.
  + **dialogAction** – Determines the type of action that Amazon Lex should take in response to the Lambda function\. The `type` field is always required, the `slotToElicit` field is only required when `dialogAction.type` is `ElicitSlot`\.
  + **intent** – The name of the intent that Amazon Lex should use\. Required when `dialogAction.type` is `Delegate` or `ElicitIntent`\.
  + **state** – Required\. The state can only be `ReadyForFulfillment` if `delegateAction.type` isn't `Delegate`\.
+ **messages** – Required if `dialogAction.type` is `ElicitIntent`\. One or more messages that Amazon Lex shows to the customer to perform the next turn of the conversation\. If you don't supply messages, Amazon Lex uses the appropriate message defined when the bot was created\. For more information, see the [Message](API_runtime_Message.md) data type\.
  + **contentType** – The type of message to use\.
  + **content** – If the message type is `PlainText`, `CustomPayload`, or `SSML`, the `content` field contains the message to send to the user\.
  + **imageResponseCard** – If the message type is `ImageResponseCard`, contains the definition of the response card to show to the user\. For more information, see the [ImageResponseCard](API_runtime_ImageResponseCard.md) data type\.