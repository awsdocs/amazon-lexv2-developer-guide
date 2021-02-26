# UpdateSlotType<a name="API_UpdateSlotType"></a>

Updates the configuration of an existing slot type\.

## Request Syntax<a name="API_UpdateSlotType_RequestSyntax"></a>

```
PUT /bots/botId/botversions/botVersion/botlocales/localeId/slottypes/slotTypeId/ HTTP/1.1
Content-type: application/json

{
   "description": "string",
   "parentSlotTypeSignature": "string",
   "slotTypeName": "string",
   "slotTypeValues": [ 
      { 
         "sampleValue": { 
            "value": "string"
         },
         "synonyms": [ 
            { 
               "value": "string"
            }
         ]
      }
   ],
   "valueSelectionSetting": { 
      "regexFilter": { 
         "pattern": "string"
      },
      "resolutionStrategy": "string"
   }
}
```

## URI Request Parameters<a name="API_UpdateSlotType_RequestParameters"></a>

The request uses the following URI parameters\.

 ** [botId](#API_UpdateSlotType_RequestSyntax) **   <a name="lexv2-UpdateSlotType-request-botId"></a>
The identifier of the bot that contains the slot type\.  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$`   
Required: Yes

 ** [botVersion](#API_UpdateSlotType_RequestSyntax) **   <a name="lexv2-UpdateSlotType-request-botVersion"></a>
The version of the bot that contains the slot type\. Must be `DRAFT`\.  
Length Constraints: Fixed length of 5\.  
Pattern: `^DRAFT$`   
Required: Yes

 ** [localeId](#API_UpdateSlotType_RequestSyntax) **   <a name="lexv2-UpdateSlotType-request-localeId"></a>
The identifier of the language and locale that contains the slot type\. The string must match one of the supported locales\. For more information, see [https://docs.aws.amazon.com/lex/latest/dg/supported-locales.html](https://docs.aws.amazon.com/lex/latest/dg/supported-locales.html)\.  
Required: Yes

 ** [slotTypeId](#API_UpdateSlotType_RequestSyntax) **   <a name="lexv2-UpdateSlotType-request-slotTypeId"></a>
The unique identifier of the slot type to update\.  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$`   
Required: Yes

## Request Body<a name="API_UpdateSlotType_RequestBody"></a>

The request accepts the following data in JSON format\.

 ** [description](#API_UpdateSlotType_RequestSyntax) **   <a name="lexv2-UpdateSlotType-request-description"></a>
The new description of the slot type\.  
Type: String  
Length Constraints: Minimum length of 0\. Maximum length of 200\.  
Required: No

 ** [parentSlotTypeSignature](#API_UpdateSlotType_RequestSyntax) **   <a name="lexv2-UpdateSlotType-request-parentSlotTypeSignature"></a>
The new built\-in slot type that should be used as the parent of this slot type\.  
Type: String  
Required: No

 ** [slotTypeName](#API_UpdateSlotType_RequestSyntax) **   <a name="lexv2-UpdateSlotType-request-slotTypeName"></a>
The new name of the slot type\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 100\.  
Pattern: `^([0-9a-zA-Z][_-]?)+$`   
Required: Yes

 ** [slotTypeValues](#API_UpdateSlotType_RequestSyntax) **   <a name="lexv2-UpdateSlotType-request-slotTypeValues"></a>
A new list of values and their optional synonyms that define the values that the slot type can take\.  
Type: Array of [SlotTypeValue](API_SlotTypeValue.md) objects  
Array Members: Minimum number of 1 item\. Maximum number of 10000 items\.  
Required: No

 ** [valueSelectionSetting](#API_UpdateSlotType_RequestSyntax) **   <a name="lexv2-UpdateSlotType-request-valueSelectionSetting"></a>
The strategy that Amazon Lex should use when deciding on a value from the list of slot type values\.  
Type: [SlotValueSelectionSetting](API_SlotValueSelectionSetting.md) object  
Required: Yes

## Response Syntax<a name="API_UpdateSlotType_ResponseSyntax"></a>

```
HTTP/1.1 202
Content-type: application/json

{
   "botId": "string",
   "botVersion": "string",
   "creationDateTime": number,
   "description": "string",
   "lastUpdatedDateTime": number,
   "localeId": "string",
   "parentSlotTypeSignature": "string",
   "slotTypeId": "string",
   "slotTypeName": "string",
   "slotTypeValues": [ 
      { 
         "sampleValue": { 
            "value": "string"
         },
         "synonyms": [ 
            { 
               "value": "string"
            }
         ]
      }
   ],
   "valueSelectionSetting": { 
      "regexFilter": { 
         "pattern": "string"
      },
      "resolutionStrategy": "string"
   }
}
```

## Response Elements<a name="API_UpdateSlotType_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 202 response\.

The following data is returned in JSON format by the service\.

 ** [botId](#API_UpdateSlotType_ResponseSyntax) **   <a name="lexv2-UpdateSlotType-response-botId"></a>
The identifier of the bot that contains the slot type\.  
Type: String  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$` 

 ** [botVersion](#API_UpdateSlotType_ResponseSyntax) **   <a name="lexv2-UpdateSlotType-response-botVersion"></a>
The version of the bot that contains the slot type\. This is always `DRAFT`\.  
Type: String  
Length Constraints: Fixed length of 5\.  
Pattern: `^DRAFT$` 

 ** [creationDateTime](#API_UpdateSlotType_ResponseSyntax) **   <a name="lexv2-UpdateSlotType-response-creationDateTime"></a>
The timestamp of the date and time that the slot type was created\.  
Type: Timestamp

 ** [description](#API_UpdateSlotType_ResponseSyntax) **   <a name="lexv2-UpdateSlotType-response-description"></a>
The updated description of the slot type\.  
Type: String  
Length Constraints: Minimum length of 0\. Maximum length of 200\.

 ** [lastUpdatedDateTime](#API_UpdateSlotType_ResponseSyntax) **   <a name="lexv2-UpdateSlotType-response-lastUpdatedDateTime"></a>
A timestamp of the date and time that the slot type was last updated\.  
Type: Timestamp

 ** [localeId](#API_UpdateSlotType_ResponseSyntax) **   <a name="lexv2-UpdateSlotType-response-localeId"></a>
The language and locale of the updated slot type\.  
Type: String

 ** [parentSlotTypeSignature](#API_UpdateSlotType_ResponseSyntax) **   <a name="lexv2-UpdateSlotType-response-parentSlotTypeSignature"></a>
The updated signature of the built\-in slot type that is the parent of this slot type\.  
Type: String

 ** [slotTypeId](#API_UpdateSlotType_ResponseSyntax) **   <a name="lexv2-UpdateSlotType-response-slotTypeId"></a>
The unique identifier of the updated slot type\.  
Type: String  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$` 

 ** [slotTypeName](#API_UpdateSlotType_ResponseSyntax) **   <a name="lexv2-UpdateSlotType-response-slotTypeName"></a>
The updated name of the slot type\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 100\.  
Pattern: `^([0-9a-zA-Z][_-]?)+$` 

 ** [slotTypeValues](#API_UpdateSlotType_ResponseSyntax) **   <a name="lexv2-UpdateSlotType-response-slotTypeValues"></a>
The updated values that the slot type provides\.  
Type: Array of [SlotTypeValue](API_SlotTypeValue.md) objects  
Array Members: Minimum number of 1 item\. Maximum number of 10000 items\.

 ** [valueSelectionSetting](#API_UpdateSlotType_ResponseSyntax) **   <a name="lexv2-UpdateSlotType-response-valueSelectionSetting"></a>
The updated strategy that Amazon Lex uses to determine which value to select from the slot type\.  
Type: [SlotValueSelectionSetting](API_SlotValueSelectionSetting.md) object

## Errors<a name="API_UpdateSlotType_Errors"></a>

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

## See Also<a name="API_UpdateSlotType_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [AWS Command Line Interface](https://docs.aws.amazon.com/goto/aws-cli/models.lex.v2-2020-08-07/UpdateSlotType) 
+  [AWS SDK for \.NET](https://docs.aws.amazon.com/goto/DotNetSDKV3/models.lex.v2-2020-08-07/UpdateSlotType) 
+  [AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/models.lex.v2-2020-08-07/UpdateSlotType) 
+  [AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/models.lex.v2-2020-08-07/UpdateSlotType) 
+  [AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/models.lex.v2-2020-08-07/UpdateSlotType) 
+  [AWS SDK for JavaScript](https://docs.aws.amazon.com/goto/AWSJavaScriptSDK/models.lex.v2-2020-08-07/UpdateSlotType) 
+  [AWS SDK for PHP V3](https://docs.aws.amazon.com/goto/SdkForPHPV3/models.lex.v2-2020-08-07/UpdateSlotType) 
+  [AWS SDK for Python](https://docs.aws.amazon.com/goto/boto3/models.lex.v2-2020-08-07/UpdateSlotType) 
+  [AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/models.lex.v2-2020-08-07/UpdateSlotType) 