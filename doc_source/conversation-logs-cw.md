# Viewing text logs in Amazon CloudWatch Logs<a name="conversation-logs-cw"></a>

Amazon Lex V2 stores text logs for your conversations in Amazon CloudWatch Logs\. To view the logs, you can use the CloudWatch Logs console or API\. For more information, see [ Search Log Data Using Filter Patterns ](https://docs.aws.amazon.com/AmazonCloudWatch/latest/logs/SearchDataFilterPattern.html) and [CloudWatch Logs Insights Query Syntax](https://docs.aws.amazon.com/AmazonCloudWatch/latest/logs/CWL_QuerySyntax.html) in the *Amazon CloudWatch Logs User Guide*\.

**To view logs using the Amazon Lex V2 console**

1. Open the Amazon Lex V2 console [https://console\.aws\.amazon\.com/lexv2](https://console.aws.amazon.com/lexv2)\.

1. From the list, choose a bot\.

1. From the left menu, choose **Analytics** and then choose **CloudWatch metrics**\.

1. View metrics for your bot on the **CloudWatch metrics** page\.

You can also use the CloudWatch console or API to view your log entries\. To find the log entries, navigate to the log group that you configured for the alias\. You find the log stream prefix for your logs in the Amazon Lex V2 console or by using the [DescribeBotAlias](API_DescribeBotAlias.md) operation\. 

Log entries for a user utterance is in multiple log streams\. An utterance in the conversation has an entry in one of the log streams with the specified prefix\. An entry in the log stream contains the following information\.

```
{
    "message-version": "2.0",
    "bot": {
        "id": "string",
        "name": "string",
        "aliasId": "string",
        "aliasName": "string",
        "localeId": "string",
        "version": "string"
    },
    "messages": [
        {
            "contentType": "PlainText | SSML | CustomPayload | ImageResponseCard",
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
    "sessionState": {
        "dialogAction": {
            "type": "Close | ConfirmIntent | Delegate | ElicitIntent | ElicitSlot",
            "slotToElicit": "string"
        },
        "intent": {
            "name": "string",
            "slots": {
                "string" : { 
                    "value": { 
                       "interpretedValue": "string",
                       "originalValue": "string",
                       "resolvedValues": [ "string" ]
                    }
                 },  
                "string": {
                    "shape": "List",
                    "value": {
                        "originalValue":"string",
                        "interpretedValue":"string",
                        "resolvedValues":[ "string" ]
                    },
                    "values": [
                        {
                            "shape": "Scalar",
                            "value": {
                                "originalValue": "string",
                                "interpretedValue": "string",
                                "resolvedValues": [ "string" ]
                            }
                        },
                        {
                            "shape": "Scalar",
                            "value": {
                                "originalValue": "string",
                                "interpretedValue": "string",
                                "resolvedValues": [ "string" ]
                            }
                        }
                    ]
                }
            },
            "kendraResponse": {
                // Only present when intent is KendraSearchIntent. For details, see 
                // https://docs.aws.amazon.com/kendra/latest/dg/API_Query.html#API_Query_ResponseSyntax
                },
            "state": "InProgress | ReadyForFulfillment | Fulfilled | Failed",
            "confirmationState": "Confirmed | Denied | None"
        },
        "originatingRequestId": "string",
        "sessionAttributes": {
            "string": "string"
        }
    },
    "interpretations": [
        {
            "nluConfidence": "string",
            "intent": {
                "name": "string",
                "slots": {
                    "string": {
                        "value": {
                            "originalValue": "string",
                            "interpretedValue": "string",
                            "resolvedValues": [ "string" ]
                        }
                    },
                    "string": {
                        "shape": "List",
                        "value": {
                            "interpretedValue": "string",
                            "originalValue": "string",
                            "resolvedValues": [ "string" ]
                        },
                        "values": [
                            {
                                "shape": "Scalar",
                                "value": {
                                    "interpretedValue": "string",
                                    "originalValue": "string",
                                    "resolvedValues": [ "string" ]
                                }
                            },
                            {
                                "shape": "Scalar",
                                "value": {
                                    "interpretedValue": "string",
                                    "originalValue":"string",
                                    "resolvedValues": [ "string" ]
                                }

                            }
                        ]
                    }
                },
                "kendraResponse": {
                    // Only present when intent is KendraSearchIntent. For details, see 
                    // https://docs.aws.amazon.com/kendra/latest/dg/API_Query.html#API_Query_ResponseSyntax
                    },
                "state": "InProgress | ReadyForFulfillment | Fulfilled | Failed",
                "confirmationState": "Confirmed | Denied | None"
                },
            "sentimentResponse": {
                "sentiment": "string",
                "sentimentScore": {
                    "positive": "string",
                    "negative": "string",
                    "neutral": "string",
                    "mixed": "string"
                }
            }
        }
    ],
    "sessionId": "string",
    "inputTranscript": "string",
    "missedUtterance": "bool",
    "requestId": "string",
    "timestamp": "string",
    "developerOverride": "bool",
    "inputMode": "DTMF | Speech | Text",
    "requestAttributes": {
        "string": "string"
    },
    "audioProperties": {
        "contentType": "string",
        "s3Path": "string",
        "duration": {
            "total": "integer",
            "voice": "integer",
            "silence": "integer"
        }
    },
    "bargeIn": "string",
    "responseReason": "string",
    "operationName": "string"
}
```

The contents of the log entry depends on the result of a transaction and the configuration of the bot and request\.
+ The `intent`, `slots`, and `slotToElicit` fields don't appear in an entry if the `missedUtterance` field is `true`\.
+ The `s3PathForAudio` field doesn't appear if audio logs are disabled or if the `inputDialogMode`field is `Text`\.
+ The `responseCard` field only appears when you have defined a response card for the bot\.
+ The `requestAttributes` map only appears if you have specified request attributes in the request\.
+ The `kendraResponse` field is only present when the `AMAZON.KendraSearchIntent` makes a request to search an Amazon Kendra index\.
+ The `developerOverride` field is true when an alternative intent was specified in the bot's Lambda function\.
+ The `sessionAttributes` map only appears if you have specified session attributes in the request\.
+ The `sentimentResponse` map only appears if you configure the bot to return sentiment values\.

**Note**  
The input format may change without a corresponding change in the `messageVersion`\. Your code should not throw an error if new fields are present\.