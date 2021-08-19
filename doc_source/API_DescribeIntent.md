# DescribeIntent<a name="API_DescribeIntent"></a>

Returns metadata about an intent\.

## Request Syntax<a name="API_DescribeIntent_RequestSyntax"></a>

```
GET /bots/botId/botversions/botVersion/botlocales/localeId/intents/intentId/ HTTP/1.1
```

## URI Request Parameters<a name="API_DescribeIntent_RequestParameters"></a>

The request uses the following URI parameters\.

 ** [botId](#API_DescribeIntent_RequestSyntax) **   <a name="lexv2-DescribeIntent-request-botId"></a>
The identifier of the bot associated with the intent\.  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$`   
Required: Yes

 ** [botVersion](#API_DescribeIntent_RequestSyntax) **   <a name="lexv2-DescribeIntent-request-botVersion"></a>
The version of the bot associated with the intent\.  
Length Constraints: Minimum length of 1\. Maximum length of 5\.  
Pattern: `^(DRAFT|[0-9]+)$`   
Required: Yes

 ** [intentId](#API_DescribeIntent_RequestSyntax) **   <a name="lexv2-DescribeIntent-request-intentId"></a>
The identifier of the intent to describe\.  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$`   
Required: Yes

 ** [localeId](#API_DescribeIntent_RequestSyntax) **   <a name="lexv2-DescribeIntent-request-localeId"></a>
The identifier of the language and locale of the intent to describe\. The string must match one of the supported locales\. For more information, see [Supported languages](https://docs.aws.amazon.com/lexv2/latest/dg/how-languages.html)\.  
Required: Yes

## Request Body<a name="API_DescribeIntent_RequestBody"></a>

The request does not have a request body\.

## Response Syntax<a name="API_DescribeIntent_ResponseSyntax"></a>

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
      "active": boolean,
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
      "active": boolean,
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

## Response Elements<a name="API_DescribeIntent_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 200 response\.

The following data is returned in JSON format by the service\.

 ** [botId](#API_DescribeIntent_ResponseSyntax) **   <a name="lexv2-DescribeIntent-response-botId"></a>
The identifier of the bot associated with the intent\.  
Type: String  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$` 

 ** [botVersion](#API_DescribeIntent_ResponseSyntax) **   <a name="lexv2-DescribeIntent-response-botVersion"></a>
The version of the bot associated with the intent\.  
Type: String  
Length Constraints: Fixed length of 5\.  
Pattern: `^DRAFT$` 

 ** [creationDateTime](#API_DescribeIntent_ResponseSyntax) **   <a name="lexv2-DescribeIntent-response-creationDateTime"></a>
A timestamp of the date and time that the intent was created\.  
Type: Timestamp

 ** [description](#API_DescribeIntent_ResponseSyntax) **   <a name="lexv2-DescribeIntent-response-description"></a>
The description of the intent\.  
Type: String  
Length Constraints: Minimum length of 0\. Maximum length of 200\.

 ** [dialogCodeHook](#API_DescribeIntent_ResponseSyntax) **   <a name="lexv2-DescribeIntent-response-dialogCodeHook"></a>
The Lambda function called during each turn of a conversation with the intent\.  
Type: [DialogCodeHookSettings](API_DialogCodeHookSettings.md) object

 ** [fulfillmentCodeHook](#API_DescribeIntent_ResponseSyntax) **   <a name="lexv2-DescribeIntent-response-fulfillmentCodeHook"></a>
The Lambda function called when the intent is complete and ready for fulfillment\.  
Type: [FulfillmentCodeHookSettings](API_FulfillmentCodeHookSettings.md) object

 ** [inputContexts](#API_DescribeIntent_ResponseSyntax) **   <a name="lexv2-DescribeIntent-response-inputContexts"></a>
A list of contexts that must be active for the intent to be considered for sending to the user\.  
Type: Array of [InputContext](API_InputContext.md) objects  
Array Members: Minimum number of 0 items\. Maximum number of 5 items\.

 ** [intentClosingSetting](#API_DescribeIntent_ResponseSyntax) **   <a name="lexv2-DescribeIntent-response-intentClosingSetting"></a>
The response that Amazon Lex sends to when the intent is closed\.  
Type: [IntentClosingSetting](API_IntentClosingSetting.md) object

 ** [intentConfirmationSetting](#API_DescribeIntent_ResponseSyntax) **   <a name="lexv2-DescribeIntent-response-intentConfirmationSetting"></a>
Prompts that Amazon Lex sends to the user to confirm completion of an intent\.  
Type: [IntentConfirmationSetting](API_IntentConfirmationSetting.md) object

 ** [intentId](#API_DescribeIntent_ResponseSyntax) **   <a name="lexv2-DescribeIntent-response-intentId"></a>
The unique identifier assigned to the intent when it was created\.  
Type: String  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$` 

 ** [intentName](#API_DescribeIntent_ResponseSyntax) **   <a name="lexv2-DescribeIntent-response-intentName"></a>
The name specified for the intent\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 100\.  
Pattern: `^([0-9a-zA-Z][_-]?)+$` 

 ** [kendraConfiguration](#API_DescribeIntent_ResponseSyntax) **   <a name="lexv2-DescribeIntent-response-kendraConfiguration"></a>
Configuration information required to use the `AMAZON.KendraSearchIntent` intent\.  
Type: [KendraConfiguration](API_KendraConfiguration.md) object

 ** [lastUpdatedDateTime](#API_DescribeIntent_ResponseSyntax) **   <a name="lexv2-DescribeIntent-response-lastUpdatedDateTime"></a>
A timestamp of the date and time that the intent was last updated\.  
Type: Timestamp

 ** [localeId](#API_DescribeIntent_ResponseSyntax) **   <a name="lexv2-DescribeIntent-response-localeId"></a>
The language and locale specified for the intent\.  
Type: String

 ** [outputContexts](#API_DescribeIntent_ResponseSyntax) **   <a name="lexv2-DescribeIntent-response-outputContexts"></a>
A list of contexts that are activated when the intent is fulfilled\.  
Type: Array of [OutputContext](API_OutputContext.md) objects  
Array Members: Minimum number of 0 items\. Maximum number of 10 items\.

 ** [parentIntentSignature](#API_DescribeIntent_ResponseSyntax) **   <a name="lexv2-DescribeIntent-response-parentIntentSignature"></a>
The identifier of the built\-in intent that this intent is derived from, if any\.  
Type: String

 ** [sampleUtterances](#API_DescribeIntent_ResponseSyntax) **   <a name="lexv2-DescribeIntent-response-sampleUtterances"></a>
User utterances that trigger this intent\.  
Type: Array of [SampleUtterance](API_SampleUtterance.md) objects

 ** [slotPriorities](#API_DescribeIntent_ResponseSyntax) **   <a name="lexv2-DescribeIntent-response-slotPriorities"></a>
The list that determines the priority that slots should be elicited from the user\.  
Type: Array of [SlotPriority](API_SlotPriority.md) objects

## Errors<a name="API_DescribeIntent_Errors"></a>

For information about the errors that are common to all actions, see [Common Errors](CommonErrors.md)\.

 **InternalServerException**   
  
HTTP Status Code: 500

 **ResourceNotFoundException**   
  
HTTP Status Code: 404

 **ServiceQuotaExceededException**   
  
HTTP Status Code: 402

 **ThrottlingException**   
  
HTTP Status Code: 429

 **ValidationException**   
  
HTTP Status Code: 400

## See Also<a name="API_DescribeIntent_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [ AWS Command Line Interface](https://docs.aws.amazon.com/goto/aws-cli/models.lex.v2-2020-08-07/DescribeIntent) 
+  [ AWS SDK for \.NET](https://docs.aws.amazon.com/goto/DotNetSDKV3/models.lex.v2-2020-08-07/DescribeIntent) 
+  [ AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/models.lex.v2-2020-08-07/DescribeIntent) 
+  [ AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/models.lex.v2-2020-08-07/DescribeIntent) 
+  [ AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/models.lex.v2-2020-08-07/DescribeIntent) 
+  [ AWS SDK for JavaScript](https://docs.aws.amazon.com/goto/AWSJavaScriptSDK/models.lex.v2-2020-08-07/DescribeIntent) 
+  [ AWS SDK for PHP V3](https://docs.aws.amazon.com/goto/SdkForPHPV3/models.lex.v2-2020-08-07/DescribeIntent) 
+  [ AWS SDK for Python](https://docs.aws.amazon.com/goto/boto3/models.lex.v2-2020-08-07/DescribeIntent) 
+  [ AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/models.lex.v2-2020-08-07/DescribeIntent) 