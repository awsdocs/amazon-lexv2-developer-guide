# ListSlots<a name="API_ListSlots"></a>

Gets a list of slots that match the specified criteria\.

## Request Syntax<a name="API_ListSlots_RequestSyntax"></a>

```
POST /bots/botId/botversions/botVersion/botlocales/localeId/intents/intentId/slots/ HTTP/1.1
Content-type: application/json

{
   "filters": [ 
      { 
         "name": "string",
         "operator": "string",
         "values": [ "string" ]
      }
   ],
   "maxResults": number,
   "nextToken": "string",
   "sortBy": { 
      "attribute": "string",
      "order": "string"
   }
}
```

## URI Request Parameters<a name="API_ListSlots_RequestParameters"></a>

The request uses the following URI parameters\.

 ** [botId](#API_ListSlots_RequestSyntax) **   <a name="lexv2-ListSlots-request-botId"></a>
The identifier of the bot that contains the slot\.  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$`   
Required: Yes

 ** [botVersion](#API_ListSlots_RequestSyntax) **   <a name="lexv2-ListSlots-request-botVersion"></a>
The version of the bot that contains the slot\.  
Length Constraints: Minimum length of 1\. Maximum length of 5\.  
Pattern: `^(DRAFT|[0-9]+)$`   
Required: Yes

 ** [intentId](#API_ListSlots_RequestSyntax) **   <a name="lexv2-ListSlots-request-intentId"></a>
The unique identifier of the intent that contains the slot\.  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$`   
Required: Yes

 ** [localeId](#API_ListSlots_RequestSyntax) **   <a name="lexv2-ListSlots-request-localeId"></a>
The identifier of the language and locale of the slots to list\. The string must match one of the supported locales\. For more information, see [Supported languages](https://docs.aws.amazon.com/lexv2/latest/dg/how-languages.html)\.  
Required: Yes

## Request Body<a name="API_ListSlots_RequestBody"></a>

The request accepts the following data in JSON format\.

 ** [filters](#API_ListSlots_RequestSyntax) **   <a name="lexv2-ListSlots-request-filters"></a>
Provides the specification of a filter used to limit the slots in the response to only those that match the filter specification\. You can only specify one filter and only one string to filter on\.  
Type: Array of [SlotFilter](API_SlotFilter.md) objects  
Array Members: Fixed number of 1 item\.  
Required: No

 ** [maxResults](#API_ListSlots_RequestSyntax) **   <a name="lexv2-ListSlots-request-maxResults"></a>
The maximum number of slots to return in each page of results\. If there are fewer results than the max page size, only the actual number of results are returned\.  
Type: Integer  
Valid Range: Minimum value of 1\. Maximum value of 1000\.  
Required: No

 ** [nextToken](#API_ListSlots_RequestSyntax) **   <a name="lexv2-ListSlots-request-nextToken"></a>
If the response from the `ListSlots` operation contains more results than specified in the `maxResults` parameter, a token is returned in the response\. Use that token in the `nextToken` parameter to return the next page of results\.  
Type: String  
Required: No

 ** [sortBy](#API_ListSlots_RequestSyntax) **   <a name="lexv2-ListSlots-request-sortBy"></a>
Determines the sort order for the response from the `ListSlots` operation\. You can choose to sort by the slot name or last updated date in either ascending or descending order\.  
Type: [SlotSortBy](API_SlotSortBy.md) object  
Required: No

## Response Syntax<a name="API_ListSlots_ResponseSyntax"></a>

```
HTTP/1.1 200
Content-type: application/json

{
   "botId": "string",
   "botVersion": "string",
   "intentId": "string",
   "localeId": "string",
   "nextToken": "string",
   "slotSummaries": [ 
      { 
         "description": "string",
         "lastUpdatedDateTime": number,
         "slotConstraint": "string",
         "slotId": "string",
         "slotName": "string",
         "slotTypeId": "string",
         "valueElicitationPromptSpecification": { 
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
      }
   ]
}
```

## Response Elements<a name="API_ListSlots_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 200 response\.

The following data is returned in JSON format by the service\.

 ** [botId](#API_ListSlots_ResponseSyntax) **   <a name="lexv2-ListSlots-response-botId"></a>
The identifier of the bot that contains the slots\.  
Type: String  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$` 

 ** [botVersion](#API_ListSlots_ResponseSyntax) **   <a name="lexv2-ListSlots-response-botVersion"></a>
The version of the bot that contains the slots\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 5\.  
Pattern: `^(DRAFT|[0-9]+)$` 

 ** [intentId](#API_ListSlots_ResponseSyntax) **   <a name="lexv2-ListSlots-response-intentId"></a>
The identifier of the intent that contains the slots\.  
Type: String  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$` 

 ** [localeId](#API_ListSlots_ResponseSyntax) **   <a name="lexv2-ListSlots-response-localeId"></a>
The language and locale of the slots in the list\.  
Type: String

 ** [nextToken](#API_ListSlots_ResponseSyntax) **   <a name="lexv2-ListSlots-response-nextToken"></a>
A token that indicates whether there are more results to return in a response to the `ListSlots` operation\. If the `nextToken` field is present, you send the contents as the `nextToken` parameter of a `ListSlots` operation request to get the next page of results\.  
Type: String

 ** [slotSummaries](#API_ListSlots_ResponseSyntax) **   <a name="lexv2-ListSlots-response-slotSummaries"></a>
Summary information for the slots that meet the filter criteria specified in the request\. The length of the list is specified in the `maxResults` parameter of the request\. If there are more slots available, the `nextToken` field contains a token to get the next page of results\.  
Type: Array of [SlotSummary](API_SlotSummary.md) objects

## Errors<a name="API_ListSlots_Errors"></a>

For information about the errors that are common to all actions, see [Common Errors](CommonErrors.md)\.

 **InternalServerException**   
  
HTTP Status Code: 500

 **ServiceQuotaExceededException**   
  
HTTP Status Code: 402

 **ThrottlingException**   
  
HTTP Status Code: 429

 **ValidationException**   
  
HTTP Status Code: 400

## See Also<a name="API_ListSlots_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [ AWS Command Line Interface](https://docs.aws.amazon.com/goto/aws-cli/models.lex.v2-2020-08-07/ListSlots) 
+  [ AWS SDK for \.NET](https://docs.aws.amazon.com/goto/DotNetSDKV3/models.lex.v2-2020-08-07/ListSlots) 
+  [ AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/models.lex.v2-2020-08-07/ListSlots) 
+  [ AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/models.lex.v2-2020-08-07/ListSlots) 
+  [ AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/models.lex.v2-2020-08-07/ListSlots) 
+  [ AWS SDK for JavaScript](https://docs.aws.amazon.com/goto/AWSJavaScriptSDK/models.lex.v2-2020-08-07/ListSlots) 
+  [ AWS SDK for PHP V3](https://docs.aws.amazon.com/goto/SdkForPHPV3/models.lex.v2-2020-08-07/ListSlots) 
+  [ AWS SDK for Python](https://docs.aws.amazon.com/goto/boto3/models.lex.v2-2020-08-07/ListSlots) 
+  [ AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/models.lex.v2-2020-08-07/ListSlots) 