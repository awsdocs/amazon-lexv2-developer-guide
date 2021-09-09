# Using an AWS Lambda function<a name="lambda"></a>

This section describes how to attach a Lambda function to a bot alias and the structure of the event data that Amazon Lex V2 provides to a Lambda function\. Use this information to parse the input to your Lambda code\. It also explains the format of the response that Amazon Lex V2 expects your Lambda function to return\.

**Topics**
+ [Attaching a Lambda function to a bot alias](#lambda-attach)
+ [Input event format](#lambda-input-format)
+ [Response format](#lambda-response-format)

## Attaching a Lambda function to a bot alias<a name="lambda-attach"></a>

With Amazon Lex V2 you indicate that an intent should use a Lambda function for each intent, but you assign the Lambda function that your intents use for each language supported by a bot alias\. That way you can create a Lambda function tailored to each language that your bot alias supports\.

You indicate that an intent should use a Lambda function using the console or the [CreateIntent](API_CreateIntent.md) or [UpdateIntent](API_UpdateIntent.md) operation\. In the intent editor, you turn on Lambda functions in the **Code hooks** section of the editor\.

![\[The code hooks section of the Amazon Lex V2 intent editor.\]](http://docs.aws.amazon.com/lexv2/latest/dg/images/lambda-code-hooks.png)

You define the Lambda function to use in each bot alias\. The same Lambda function is used for all intents in a language supported by the bot\.

**To choose a Lambda function to use with a bot alias**

1. Open the Amazon Lex console at [https://console\.aws\.amazon\.com/lexv2/](https://console.aws.amazon.com/lexv2/)\.

1. From the list of bots, choose the name of the bot that you want to use\.

1. From **Create versions and aliases for deployment**, choose **View aliases**\.

1. From the list of aliases, choose the name of the alias that you want to use\.

1. From the list of supported languages, choose the language that the Lambda function is used for\.

1. Choose the name of the Lambda function to use, then choose the version or alias of the function\.

1. Choose **Save** to save your changes\.

## Input event format<a name="lambda-input-format"></a>

The following is the general format of an Amazon Lex V2 event that is passed to a Lambda function\. Use this information when you're writing you Lambda function\.

**Note**  
The input format may change without a corresponding change to the `messageVersion`\. Your code shouldn't throw an error if new fields are present\.

```
{
    "messageVersion": "1.0",
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
                "name": "string",
                "slots": {
                    "string": {
                        "value": {
                            "interpretedValue": "string",
                            "originalValue": "string",
                            "resolvedValues": [
                                "string"
                            ]
                        }
                    },
                    "string": {
                        "shape": "List",
                        "value": {
                            "interpretedValue": "string",
                            "originalValue": "string",
                            "resolvedValues": [
                                "string"
                            ]
                        },
                        "values": [
                            {
                                "shape": "Scalar",
                                "value": {
                                    "originalValue": "string",
                                    "interpretedValue": "string",
                                    "resolvedValues": [
                                        "string"
                                    ]
                                }
                            },
                            {
                                "shape": "Scalar",
                                "value": {
                                    "originalValue": "string",
                                    "interpretedValue": "string",
                                    "resolvedValues": [
                                        "string"
                                    ]
                                }
                            }
                        ]
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
                    "string": "string"
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
            "state": "Failed | Fulfilled | InProgress | ReadyForFulfillment",
            "slots": {
                "string": {
                    "value": {
                        "interpretedValue": "string",
                        "originalValue": "string",
                        "resolvedValues": [
                            "string"
                        ]
                    }
                },
                "string": {
                    "shape": "List",
                    "value": {
                        "interpretedValue": "string",
                        "originalValue": "string",
                        "resolvedValues": [
                            "string"
                        ]
                    },
                    "values": [
                        {
                            "shape": "Scalar",
                            "value": {
                                "originalValue": "string",
                                "interpretedValue": "string",
                                "resolvedValues": [
                                    "string"
                                ]
                            }
                        },
                        {
                            "shape": "Scalar",
                            "value": {
                                "originalValue": "string",
                                "interpretedValue": "string",
                                "resolvedValues": [
                                    "string"
                                ]
                            }
                        }
                    ]
                }
            },
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
+ **interpretations** – One or more intents that Amazon Lex V2 considers possible matches to the user's utterance\. For more information, see [Interpretation](API_runtime_Interpretation.md)\.
+ **requestAttributes** – Request\-specific attributes that the client sends in the request\. Use request attributes to pass information that doesn't need to persist for the entire session\.
+ **sessionState** – The current state of the conversation between the user and your Amazon Lex V2 bot\. For more information about the session state, see [SessionState](API_runtime_SessionState.md)\.

## Response format<a name="lambda-response-format"></a>

Amazon Lex V2 expects a response from your Lambda function in the following format:

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
            "state": "Failed | Fulfilled | InProgress | ReadyForFulfillment",
            "slots": {
                "string": {
                    "value": {
                        "interpretedValue": "string",
                        "originalValue": "string",
                        "resolvedValues": [
                            "string"
                        ]
                    }
                },
                "string": {
                    "shape": "List",
                    "value": {
                        "originalValue": "string",
                        "interpretedValue": "string",
                        "resolvedValues": [
                            "string"
                        ]
                    },
                    "values": [
                        {
                            "shape": "Scalar",
                            "value": {
                                "originalValue": "string",
                                "interpretedValue": "string",
                                "resolvedValues": [
                                    "string"
                                ]
                            }
                        },
                        {
                            "shape": "Scalar",
                            "value": {
                                "originalValue": "string",
                                "interpretedValue": "string",
                                "resolvedValues": [
                                    "string"
                                ]
                            }
                        }
                    ]
                }
            }
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
                "buttons": [
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
  + **dialogAction** – Determines the type of action that Amazon Lex V2 should take in response to the Lambda function\. The `type` field is always required, the `slotToElicit` field is only required when `dialogAction.type` is `ElicitSlot`\.
  + **intent** – The name of the intent that Amazon Lex V2 should use\. Not required when `dialogAction.type` is `Delegate` or `ElicitIntent`\.
+ **messages** – Required if `dialogAction.type` is `ElicitIntent`\. One or more messages that Amazon Lex V2 shows to the customer to perform the next turn of the conversation\. If you don't supply messages, Amazon Lex V2 uses the appropriate message defined when the bot was created\. For more information, see the [Message](API_runtime_Message.md) data type\.
  + **contentType** – The type of message to use\.
  + **content** – If the message type is `PlainText`, `CustomPayload`, or `SSML`, the `content` field contains the message to send to the user\.
  + **imageResponseCard** – If the message type is `ImageResponseCard`, contains the definition of the response card to show to the user\. For more information, see the [ImageResponseCard](API_runtime_ImageResponseCard.md) data type\.
