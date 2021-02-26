# UpdateIntent<a name="API_UpdateIntent"></a>

Updates the settings for an intent\.

## Request Syntax<a name="API_UpdateIntent_RequestSyntax"></a>

```
PUT /bots/botId/botversions/botVersion/botlocales/localeId/intents/intentId/ HTTP/1.1
Content-type: application/json

{
   "description": "string",
   "dialogCodeHook": { 
      "enabled": boolean
   },
   "fulfillmentCodeHook": { 
      "enabled": boolean
   },
   "inputContexts": [ 
      { 
         "name": "string"
      }
   ],
   "intentClosingSetting": { 
      "closingResponse": { 
         "allowInterrupt": boolean,
         "messageGroups": [ 
            { 
               "message": { 
                  "customPayload": { 
                     "value": "string"
                  },
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
                  },
                  "plainTextMessage": { 
                     "value": "string"
                  },
                  "ssmlMessage": { 
                     "value": "string"
                  }
               },
               "variations": [ 
                  { 
                     "customPayload": { 
                        "value": "string"
                     },
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
                     },
                     "plainTextMessage": { 
                        "value": "string"
                     },
                     "ssmlMessage": { 
                        "value": "string"
                     }
                  }
               ]
            }
         ]
      }
   },
   "intentConfirmationSetting": { 
      "declinationResponse": { 
         "allowInterrupt": boolean,
         "messageGroups": [ 
            { 
               "message": { 
                  "customPayload": { 
                     "value": "string"
                  },
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
                  },
                  "plainTextMessage": { 
                     "value": "string"
                  },
                  "ssmlMessage": { 
                     "value": "string"
                  }
               },
               "variations": [ 
                  { 
                     "customPayload": { 
                        "value": "string"
                     },
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
                     },
                     "plainTextMessage": { 
                        "value": "string"
                     },
                     "ssmlMessage": { 
                        "value": "string"
                     }
                  }
               ]
            }
         ]
      },
      "promptSpecification": { 
         "allowInterrupt": boolean,
         "maxRetries": number,
         "messageGroups": [ 
            { 
               "message": { 
                  "customPayload": { 
                     "value": "string"
                  },
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
                  },
                  "plainTextMessage": { 
                     "value": "string"
                  },
                  "ssmlMessage": { 
                     "value": "string"
                  }
               },
               "variations": [ 
                  { 
                     "customPayload": { 
                        "value": "string"
                     },
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
                     },
                     "plainTextMessage": { 
                        "value": "string"
                     },
                     "ssmlMessage": { 
                        "value": "string"
                     }
                  }
               ]
            }
         ]
      }
   },
   "intentName": "string",
   "kendraConfiguration": { 
      "kendraIndex": "string",
      "queryFilterString": "string",
      "queryFilterStringEnabled": boolean
   },
   "outputContexts": [ 
      { 
         "name": "string",
         "timeToLiveInSeconds": number,
         "turnsToLive": number
      }
   ],
   "parentIntentSignature": "string",
   "sampleUtterances": [ 
      { 
         "utterance": "string"
      }
   ],
   "slotPriorities": [ 
      { 
         "priority": number,
         "slotId": "string"
      }
   ]
}
```

## URI Request Parameters<a name="API_UpdateIntent_RequestParameters"></a>

The request uses the following URI parameters\.

 ** [botId](#API_UpdateIntent_RequestSyntax) **   <a name="lexv2-UpdateIntent-request-botId"></a>
The identifier of the bot that contains the intent\.  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$`   
Required: Yes

 ** [botVersion](#API_UpdateIntent_RequestSyntax) **   <a name="lexv2-UpdateIntent-request-botVersion"></a>
The version of the bot that contains the intent\. Must be `DRAFT`\.  
Length Constraints: Fixed length of 5\.  
Pattern: `^DRAFT$`   
Required: Yes

 ** [intentId](#API_UpdateIntent_RequestSyntax) **   <a name="lexv2-UpdateIntent-request-intentId"></a>
The unique identifier of the intent to update\.  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$`   
Required: Yes

 ** [localeId](#API_UpdateIntent_RequestSyntax) **   <a name="lexv2-UpdateIntent-request-localeId"></a>
The identifier of the language and locale where this intent is used\. The string must match one of the supported locales\. For more information, see [https://docs.aws.amazon.com/lex/latest/dg/supported-locales.html](https://docs.aws.amazon.com/lex/latest/dg/supported-locales.html)\.  
Required: Yes

## Request Body<a name="API_UpdateIntent_RequestBody"></a>

The request accepts the following data in JSON format\.

 ** [description](#API_UpdateIntent_RequestSyntax) **   <a name="lexv2-UpdateIntent-request-description"></a>
The new description of the intent\.  
Type: String  
Length Constraints: Minimum length of 0\. Maximum length of 200\.  
Required: No

 ** [dialogCodeHook](#API_UpdateIntent_RequestSyntax) **   <a name="lexv2-UpdateIntent-request-dialogCodeHook"></a>
The new Lambda function to use between each turn of the conversation with the bot\.  
Type: [DialogCodeHookSettings](API_DialogCodeHookSettings.md) object  
Required: No

 ** [fulfillmentCodeHook](#API_UpdateIntent_RequestSyntax) **   <a name="lexv2-UpdateIntent-request-fulfillmentCodeHook"></a>
The new Lambda function to call when all of the intents required slots are provided and the intent is ready for fulfillment\.  
Type: [FulfillmentCodeHookSettings](API_FulfillmentCodeHookSettings.md) object  
Required: No

 ** [inputContexts](#API_UpdateIntent_RequestSyntax) **   <a name="lexv2-UpdateIntent-request-inputContexts"></a>
A new list of contexts that must be active in order for Amazon Lex to consider the intent\.  
Type: Array of [InputContext](API_InputContext.md) objects  
Array Members: Minimum number of 0 items\. Maximum number of 5 items\.  
Required: No

 ** [intentClosingSetting](#API_UpdateIntent_RequestSyntax) **   <a name="lexv2-UpdateIntent-request-intentClosingSetting"></a>
The new response that Amazon Lex sends the user when the intent is closed\.  
Type: [IntentClosingSetting](API_IntentClosingSetting.md) object  
Required: No

 ** [intentConfirmationSetting](#API_UpdateIntent_RequestSyntax) **   <a name="lexv2-UpdateIntent-request-intentConfirmationSetting"></a>
New prompts that Amazon Lex sends to the user to confirm the completion of an intent\.  
Type: [IntentConfirmationSetting](API_IntentConfirmationSetting.md) object  
Required: No

 ** [intentName](#API_UpdateIntent_RequestSyntax) **   <a name="lexv2-UpdateIntent-request-intentName"></a>
The new name for the intent\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 100\.  
Pattern: `^([0-9a-zA-Z][_-]?)+$`   
Required: Yes

 ** [kendraConfiguration](#API_UpdateIntent_RequestSyntax) **   <a name="lexv2-UpdateIntent-request-kendraConfiguration"></a>
New configuration settings for connecting to an Amazon Kendra index\.  
Type: [KendraConfiguration](API_KendraConfiguration.md) object  
Required: No

 ** [outputContexts](#API_UpdateIntent_RequestSyntax) **   <a name="lexv2-UpdateIntent-request-outputContexts"></a>
A new list of contexts that Amazon Lex activates when the intent is fulfilled\.  
Type: Array of [OutputContext](API_OutputContext.md) objects  
Array Members: Minimum number of 0 items\. Maximum number of 10 items\.  
Required: No

 ** [parentIntentSignature](#API_UpdateIntent_RequestSyntax) **   <a name="lexv2-UpdateIntent-request-parentIntentSignature"></a>
The signature of the new built\-in intent to use as the parent of this intent\.  
Type: String  
Required: No

 ** [sampleUtterances](#API_UpdateIntent_RequestSyntax) **   <a name="lexv2-UpdateIntent-request-sampleUtterances"></a>
New utterances used to invoke the intent\.  
Type: Array of [SampleUtterance](API_SampleUtterance.md) objects  
Required: No

 ** [slotPriorities](#API_UpdateIntent_RequestSyntax) **   <a name="lexv2-UpdateIntent-request-slotPriorities"></a>
A new list of slots and their priorities that are contained by the intent\.  
Type: Array of [SlotPriority](API_SlotPriority.md) objects  
Required: No

## Response Syntax<a name="API_UpdateIntent_ResponseSyntax"></a>

```
HTTP/1.1 200
Content-type: application/json

{
   "botId": "string",
   "botVersion": "string",
   "creationDateTime": number,
   "description": "string",
   "dialogCodeHook": { 
      "enabled": boolean
   },
   "fulfillmentCodeHook": { 
      "enabled": boolean
   },
   "inputContexts": [ 
      { 
         "name": "string"
      }
   ],
   "intentClosingSetting": { 
      "closingResponse": { 
         "allowInterrupt": boolean,
         "messageGroups": [ 
            { 
               "message": { 
                  "customPayload": { 
                     "value": "string"
                  },
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
                  },
                  "plainTextMessage": { 
                     "value": "string"
                  },
                  "ssmlMessage": { 
                     "value": "string"
                  }
               },
               "variations": [ 
                  { 
                     "customPayload": { 
                        "value": "string"
                     },
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
                     },
                     "plainTextMessage": { 
                        "value": "string"
                     },
                     "ssmlMessage": { 
                        "value": "string"
                     }
                  }
               ]
            }
         ]
      }
   },
   "intentConfirmationSetting": { 
      "declinationResponse": { 
         "allowInterrupt": boolean,
         "messageGroups": [ 
            { 
               "message": { 
                  "customPayload": { 
                     "value": "string"
                  },
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
                  },
                  "plainTextMessage": { 
                     "value": "string"
                  },
                  "ssmlMessage": { 
                     "value": "string"
                  }
               },
               "variations": [ 
                  { 
                     "customPayload": { 
                        "value": "string"
                     },
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
                     },
                     "plainTextMessage": { 
                        "value": "string"
                     },
                     "ssmlMessage": { 
                        "value": "string"
                     }
                  }
               ]
            }
         ]
      },
      "promptSpecification": { 
         "allowInterrupt": boolean,
         "maxRetries": number,
         "messageGroups": [ 
            { 
               "message": { 
                  "customPayload": { 
                     "value": "string"
                  },
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
                  },
                  "plainTextMessage": { 
                     "value": "string"
                  },
                  "ssmlMessage": { 
                     "value": "string"
                  }
               },
               "variations": [ 
                  { 
                     "customPayload": { 
                        "value": "string"
                     },
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
                     },
                     "plainTextMessage": { 
                        "value": "string"
                     },
                     "ssmlMessage": { 
                        "value": "string"
                     }
                  }
               ]
            }
         ]
      }
   },
   "intentId": "string",
   "intentName": "string",
   "kendraConfiguration": { 
      "kendraIndex": "string",
      "queryFilterString": "string",
      "queryFilterStringEnabled": boolean
   },
   "lastUpdatedDateTime": number,
   "localeId": "string",
   "outputContexts": [ 
      { 
         "name": "string",
         "timeToLiveInSeconds": number,
         "turnsToLive": number
      }
   ],
   "parentIntentSignature": "string",
   "sampleUtterances": [ 
      { 
         "utterance": "string"
      }
   ],
   "slotPriorities": [ 
      { 
         "priority": number,
         "slotId": "string"
      }
   ]
}
```

## Response Elements<a name="API_UpdateIntent_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 200 response\.

The following data is returned in JSON format by the service\.

 ** [botId](#API_UpdateIntent_ResponseSyntax) **   <a name="lexv2-UpdateIntent-response-botId"></a>
The identifier of the bot that contains the intent\.  
Type: String  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$` 

 ** [botVersion](#API_UpdateIntent_ResponseSyntax) **   <a name="lexv2-UpdateIntent-response-botVersion"></a>
The version of the bot that contains the intent\. Will always be `DRAFT`\.  
Type: String  
Length Constraints: Fixed length of 5\.  
Pattern: `^DRAFT$` 

 ** [creationDateTime](#API_UpdateIntent_ResponseSyntax) **   <a name="lexv2-UpdateIntent-response-creationDateTime"></a>
A timestamp of when the intent was created\.  
Type: Timestamp

 ** [description](#API_UpdateIntent_ResponseSyntax) **   <a name="lexv2-UpdateIntent-response-description"></a>
The updated description of the intent\.  
Type: String  
Length Constraints: Minimum length of 0\. Maximum length of 200\.

 ** [dialogCodeHook](#API_UpdateIntent_ResponseSyntax) **   <a name="lexv2-UpdateIntent-response-dialogCodeHook"></a>
The updated Lambda function called during each turn of the conversation with the user\.  
Type: [DialogCodeHookSettings](API_DialogCodeHookSettings.md) object

 ** [fulfillmentCodeHook](#API_UpdateIntent_ResponseSyntax) **   <a name="lexv2-UpdateIntent-response-fulfillmentCodeHook"></a>
The updated Lambda function called when the intent is ready for fulfillment\.  
Type: [FulfillmentCodeHookSettings](API_FulfillmentCodeHookSettings.md) object

 ** [inputContexts](#API_UpdateIntent_ResponseSyntax) **   <a name="lexv2-UpdateIntent-response-inputContexts"></a>
The updated list of contexts that must be active for the intent to be considered by Amazon Lex\.  
Type: Array of [InputContext](API_InputContext.md) objects  
Array Members: Minimum number of 0 items\. Maximum number of 5 items\.

 ** [intentClosingSetting](#API_UpdateIntent_ResponseSyntax) **   <a name="lexv2-UpdateIntent-response-intentClosingSetting"></a>
The updated response that Amazon Lex sends the user when the intent is closed\.  
Type: [IntentClosingSetting](API_IntentClosingSetting.md) object

 ** [intentConfirmationSetting](#API_UpdateIntent_ResponseSyntax) **   <a name="lexv2-UpdateIntent-response-intentConfirmationSetting"></a>
The updated prompts that Amazon Lex sends to the user to confirm the completion of an intent\.  
Type: [IntentConfirmationSetting](API_IntentConfirmationSetting.md) object

 ** [intentId](#API_UpdateIntent_ResponseSyntax) **   <a name="lexv2-UpdateIntent-response-intentId"></a>
The identifier of the intent that was updated\.  
Type: String  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$` 

 ** [intentName](#API_UpdateIntent_ResponseSyntax) **   <a name="lexv2-UpdateIntent-response-intentName"></a>
The updated name of the intent\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 100\.  
Pattern: `^([0-9a-zA-Z][_-]?)+$` 

 ** [kendraConfiguration](#API_UpdateIntent_ResponseSyntax) **   <a name="lexv2-UpdateIntent-response-kendraConfiguration"></a>
The updated configuration for connecting to an Amazon Kendra index with the `AMAZON.KendraSearchIntent` intent\.  
Type: [KendraConfiguration](API_KendraConfiguration.md) object

 ** [lastUpdatedDateTime](#API_UpdateIntent_ResponseSyntax) **   <a name="lexv2-UpdateIntent-response-lastUpdatedDateTime"></a>
A timestamp of the last time that the intent was modified\.  
Type: Timestamp

 ** [localeId](#API_UpdateIntent_ResponseSyntax) **   <a name="lexv2-UpdateIntent-response-localeId"></a>
The updated language and locale of the intent\.  
Type: String

 ** [outputContexts](#API_UpdateIntent_ResponseSyntax) **   <a name="lexv2-UpdateIntent-response-outputContexts"></a>
The updated list of contexts that Amazon Lex activates when the intent is fulfilled\.  
Type: Array of [OutputContext](API_OutputContext.md) objects  
Array Members: Minimum number of 0 items\. Maximum number of 10 items\.

 ** [parentIntentSignature](#API_UpdateIntent_ResponseSyntax) **   <a name="lexv2-UpdateIntent-response-parentIntentSignature"></a>
The updated built\-in intent that is the parent of this intent\.  
Type: String

 ** [sampleUtterances](#API_UpdateIntent_ResponseSyntax) **   <a name="lexv2-UpdateIntent-response-sampleUtterances"></a>
The updated list of sample utterances for the intent\.  
Type: Array of [SampleUtterance](API_SampleUtterance.md) objects

 ** [slotPriorities](#API_UpdateIntent_ResponseSyntax) **   <a name="lexv2-UpdateIntent-response-slotPriorities"></a>
The updated list of slots and their priorities that are elicited from the user for the intent\.  
Type: Array of [SlotPriority](API_SlotPriority.md) objects

## Errors<a name="API_UpdateIntent_Errors"></a>

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

## See Also<a name="API_UpdateIntent_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [AWS Command Line Interface](https://docs.aws.amazon.com/goto/aws-cli/models.lex.v2-2020-08-07/UpdateIntent) 
+  [AWS SDK for \.NET](https://docs.aws.amazon.com/goto/DotNetSDKV3/models.lex.v2-2020-08-07/UpdateIntent) 
+  [AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/models.lex.v2-2020-08-07/UpdateIntent) 
+  [AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/models.lex.v2-2020-08-07/UpdateIntent) 
+  [AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/models.lex.v2-2020-08-07/UpdateIntent) 
+  [AWS SDK for JavaScript](https://docs.aws.amazon.com/goto/AWSJavaScriptSDK/models.lex.v2-2020-08-07/UpdateIntent) 
+  [AWS SDK for PHP V3](https://docs.aws.amazon.com/goto/SdkForPHPV3/models.lex.v2-2020-08-07/UpdateIntent) 
+  [AWS SDK for Python](https://docs.aws.amazon.com/goto/boto3/models.lex.v2-2020-08-07/UpdateIntent) 
+  [AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/models.lex.v2-2020-08-07/UpdateIntent) 