# UpdateSlot<a name="API_UpdateSlot"></a>

Updates the settings for a slot\.

## Request Syntax<a name="API_UpdateSlot_RequestSyntax"></a>

```
PUT /bots/botId/botversions/botVersion/botlocales/localeId/intents/intentId/slots/slotId/ HTTP/1.1
Content-type: application/json

{
   "description": "string",
   "multipleValuesSetting": { 
      "allowMultipleValues": boolean
   },
   "obfuscationSetting": { 
      "obfuscationSettingType": "string"
   },
   "slotName": "string",
   "slotTypeId": "string",
   "valueElicitationSetting": { 
      "defaultValueSpecification": { 
         "defaultValueList": [ 
            { 
               "defaultValue": "string"
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
      },
      "sampleUtterances": [ 
         { 
            "utterance": "string"
         }
      ],
      "slotConstraint": "string",
      "waitAndContinueSpecification": { 
         "active": boolean,
         "continueResponse": { 
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
         "stillWaitingResponse": { 
            "allowInterrupt": boolean,
            "frequencyInSeconds": number,
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
            ],
            "timeoutInSeconds": number
         },
         "waitingResponse": { 
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
      }
   }
}
```

## URI Request Parameters<a name="API_UpdateSlot_RequestParameters"></a>

The request uses the following URI parameters\.

 ** [botId](#API_UpdateSlot_RequestSyntax) **   <a name="lexv2-UpdateSlot-request-botId"></a>
The unique identifier of the bot that contains the slot\.  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$`   
Required: Yes

 ** [botVersion](#API_UpdateSlot_RequestSyntax) **   <a name="lexv2-UpdateSlot-request-botVersion"></a>
The version of the bot that contains the slot\. Must always be `DRAFT`\.  
Length Constraints: Fixed length of 5\.  
Pattern: `^DRAFT$`   
Required: Yes

 ** [intentId](#API_UpdateSlot_RequestSyntax) **   <a name="lexv2-UpdateSlot-request-intentId"></a>
The identifier of the intent that contains the slot\.  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$`   
Required: Yes

 ** [localeId](#API_UpdateSlot_RequestSyntax) **   <a name="lexv2-UpdateSlot-request-localeId"></a>
The identifier of the language and locale that contains the slot\. The string must match one of the supported locales\. For more information, see [Supported languages](https://docs.aws.amazon.com/lexv2/latest/dg/how-languages.html)\.  
Required: Yes

 ** [slotId](#API_UpdateSlot_RequestSyntax) **   <a name="lexv2-UpdateSlot-request-slotId"></a>
The unique identifier for the slot to update\.  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$`   
Required: Yes

## Request Body<a name="API_UpdateSlot_RequestBody"></a>

The request accepts the following data in JSON format\.

 ** [description](#API_UpdateSlot_RequestSyntax) **   <a name="lexv2-UpdateSlot-request-description"></a>
The new description for the slot\.  
Type: String  
Length Constraints: Minimum length of 0\. Maximum length of 200\.  
Required: No

 ** [multipleValuesSetting](#API_UpdateSlot_RequestSyntax) **   <a name="lexv2-UpdateSlot-request-multipleValuesSetting"></a>
Determines whether the slot accepts multiple values in one response\. Multiple value slots are only available in the en\-US locale\. If you set this value to `true` in any other locale, Amazon Lex throws a `ValidationException`\.  
If the `multipleValuesSetting` is not set, the default value is `false`\.  
Type: [MultipleValuesSetting](API_MultipleValuesSetting.md) object  
Required: No

 ** [obfuscationSetting](#API_UpdateSlot_RequestSyntax) **   <a name="lexv2-UpdateSlot-request-obfuscationSetting"></a>
New settings that determine how slot values are formatted in Amazon CloudWatch logs\.   
Type: [ObfuscationSetting](API_ObfuscationSetting.md) object  
Required: No

 ** [slotName](#API_UpdateSlot_RequestSyntax) **   <a name="lexv2-UpdateSlot-request-slotName"></a>
The new name for the slot\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 100\.  
Pattern: `^([0-9a-zA-Z][_-]?)+$`   
Required: Yes

 ** [slotTypeId](#API_UpdateSlot_RequestSyntax) **   <a name="lexv2-UpdateSlot-request-slotTypeId"></a>
The unique identifier of the new slot type to associate with this slot\.   
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 25\.  
Pattern: `^((AMAZON\.)[a-zA-Z_]+?|[0-9a-zA-Z]+)$`   
Required: Yes

 ** [valueElicitationSetting](#API_UpdateSlot_RequestSyntax) **   <a name="lexv2-UpdateSlot-request-valueElicitationSetting"></a>
A new set of prompts that Amazon Lex sends to the user to elicit a response the provides a value for the slot\.  
Type: [SlotValueElicitationSetting](API_SlotValueElicitationSetting.md) object  
Required: Yes

## Response Syntax<a name="API_UpdateSlot_ResponseSyntax"></a>

```
HTTP/1.1 200
Content-type: application/json

{
   "botId": "string",
   "botVersion": "string",
   "creationDateTime": number,
   "description": "string",
   "intentId": "string",
   "lastUpdatedDateTime": number,
   "localeId": "string",
   "multipleValuesSetting": { 
      "allowMultipleValues": boolean
   },
   "obfuscationSetting": { 
      "obfuscationSettingType": "string"
   },
   "slotId": "string",
   "slotName": "string",
   "slotTypeId": "string",
   "valueElicitationSetting": { 
      "defaultValueSpecification": { 
         "defaultValueList": [ 
            { 
               "defaultValue": "string"
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
      },
      "sampleUtterances": [ 
         { 
            "utterance": "string"
         }
      ],
      "slotConstraint": "string",
      "waitAndContinueSpecification": { 
         "active": boolean,
         "continueResponse": { 
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
         "stillWaitingResponse": { 
            "allowInterrupt": boolean,
            "frequencyInSeconds": number,
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
            ],
            "timeoutInSeconds": number
         },
         "waitingResponse": { 
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
      }
   }
}
```

## Response Elements<a name="API_UpdateSlot_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 200 response\.

The following data is returned in JSON format by the service\.

 ** [botId](#API_UpdateSlot_ResponseSyntax) **   <a name="lexv2-UpdateSlot-response-botId"></a>
The identifier of the bot that contains the slot\.  
Type: String  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$` 

 ** [botVersion](#API_UpdateSlot_ResponseSyntax) **   <a name="lexv2-UpdateSlot-response-botVersion"></a>
The identifier of the slot version that contains the slot\. Will always be `DRAFT`\.  
Type: String  
Length Constraints: Fixed length of 5\.  
Pattern: `^DRAFT$` 

 ** [creationDateTime](#API_UpdateSlot_ResponseSyntax) **   <a name="lexv2-UpdateSlot-response-creationDateTime"></a>
The timestamp of the date and time that the slot was created\.  
Type: Timestamp

 ** [description](#API_UpdateSlot_ResponseSyntax) **   <a name="lexv2-UpdateSlot-response-description"></a>
The updated description of the bot\.  
Type: String  
Length Constraints: Minimum length of 0\. Maximum length of 200\.

 ** [intentId](#API_UpdateSlot_ResponseSyntax) **   <a name="lexv2-UpdateSlot-response-intentId"></a>
The intent that contains the slot\.  
Type: String  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$` 

 ** [lastUpdatedDateTime](#API_UpdateSlot_ResponseSyntax) **   <a name="lexv2-UpdateSlot-response-lastUpdatedDateTime"></a>
The timestamp of the date and time that the slot was last updated\.  
Type: Timestamp

 ** [localeId](#API_UpdateSlot_ResponseSyntax) **   <a name="lexv2-UpdateSlot-response-localeId"></a>
The locale that contains the slot\.  
Type: String

 ** [multipleValuesSetting](#API_UpdateSlot_ResponseSyntax) **   <a name="lexv2-UpdateSlot-response-multipleValuesSetting"></a>
Indicates whether the slot accepts multiple values in one response\.  
Type: [MultipleValuesSetting](API_MultipleValuesSetting.md) object

 ** [obfuscationSetting](#API_UpdateSlot_ResponseSyntax) **   <a name="lexv2-UpdateSlot-response-obfuscationSetting"></a>
The updated setting that determines whether the slot value is obfuscated in the Amazon CloudWatch logs\.  
Type: [ObfuscationSetting](API_ObfuscationSetting.md) object

 ** [slotId](#API_UpdateSlot_ResponseSyntax) **   <a name="lexv2-UpdateSlot-response-slotId"></a>
The unique identifier of the slot that was updated\.  
Type: String  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$` 

 ** [slotName](#API_UpdateSlot_ResponseSyntax) **   <a name="lexv2-UpdateSlot-response-slotName"></a>
The updated name of the slot\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 100\.  
Pattern: `^([0-9a-zA-Z][_-]?)+$` 

 ** [slotTypeId](#API_UpdateSlot_ResponseSyntax) **   <a name="lexv2-UpdateSlot-response-slotTypeId"></a>
The updated identifier of the slot type that provides values for the slot\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 25\.  
Pattern: `^((AMAZON\.)[a-zA-Z_]+?|[0-9a-zA-Z]+)$` 

 ** [valueElicitationSetting](#API_UpdateSlot_ResponseSyntax) **   <a name="lexv2-UpdateSlot-response-valueElicitationSetting"></a>
The updated prompts that Amazon Lex sends to the user to elicit a response that provides a value for the slot\.  
Type: [SlotValueElicitationSetting](API_SlotValueElicitationSetting.md) object

## Errors<a name="API_UpdateSlot_Errors"></a>

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

## See Also<a name="API_UpdateSlot_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [ AWS Command Line Interface](https://docs.aws.amazon.com/goto/aws-cli/models.lex.v2-2020-08-07/UpdateSlot) 
+  [ AWS SDK for \.NET](https://docs.aws.amazon.com/goto/DotNetSDKV3/models.lex.v2-2020-08-07/UpdateSlot) 
+  [ AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/models.lex.v2-2020-08-07/UpdateSlot) 
+  [ AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/models.lex.v2-2020-08-07/UpdateSlot) 
+  [ AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/models.lex.v2-2020-08-07/UpdateSlot) 
+  [ AWS SDK for JavaScript](https://docs.aws.amazon.com/goto/AWSJavaScriptSDK/models.lex.v2-2020-08-07/UpdateSlot) 
+  [ AWS SDK for PHP V3](https://docs.aws.amazon.com/goto/SdkForPHPV3/models.lex.v2-2020-08-07/UpdateSlot) 
+  [ AWS SDK for Python](https://docs.aws.amazon.com/goto/boto3/models.lex.v2-2020-08-07/UpdateSlot) 
+  [ AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/models.lex.v2-2020-08-07/UpdateSlot) 