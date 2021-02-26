# CreateSlotType<a name="API_CreateSlotType"></a>

Creates a custom slot type

 To create a custom slot type, specify a name for the slot type and a set of enumeration values, the values that a slot of this type can assume\. 

## Request Syntax<a name="API_CreateSlotType_RequestSyntax"></a>

```
PUT /bots/botId/botversions/botVersion/botlocales/localeId/slottypes/ HTTP/1.1
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

## URI Request Parameters<a name="API_CreateSlotType_RequestParameters"></a>

The request uses the following URI parameters\.

 ** [botId](#API_CreateSlotType_RequestSyntax) **   <a name="lexv2-CreateSlotType-request-botId"></a>
The identifier of the bot associated with this slot type\.  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$`   
Required: Yes

 ** [botVersion](#API_CreateSlotType_RequestSyntax) **   <a name="lexv2-CreateSlotType-request-botVersion"></a>
The identifier of the bot version associated with this slot type\.  
Length Constraints: Fixed length of 5\.  
Pattern: `^DRAFT$`   
Required: Yes

 ** [localeId](#API_CreateSlotType_RequestSyntax) **   <a name="lexv2-CreateSlotType-request-localeId"></a>
The identifier of the language and locale that the slot type will be used in\. The string must match one of the supported locales\. All of the bots, intents, and slots used by the slot type must have the same locale\. For more information, see [https://docs.aws.amazon.com/lex/latest/dg/supported-locales.html](https://docs.aws.amazon.com/lex/latest/dg/supported-locales.html)\.  
Required: Yes

## Request Body<a name="API_CreateSlotType_RequestBody"></a>

The request accepts the following data in JSON format\.

 ** [description](#API_CreateSlotType_RequestSyntax) **   <a name="lexv2-CreateSlotType-request-description"></a>
A description of the slot type\. Use the description to help identify the slot type in lists\.  
Type: String  
Length Constraints: Minimum length of 0\. Maximum length of 200\.  
Required: No

 ** [parentSlotTypeSignature](#API_CreateSlotType_RequestSyntax) **   <a name="lexv2-CreateSlotType-request-parentSlotTypeSignature"></a>
The built\-in slot type used as a parent of this slot type\. When you define a parent slot type, the new slot type has the configuration of the parent slot type\.  
Only `AMAZON.AlphaNumeric` is supported\.  
Type: String  
Required: No

 ** [slotTypeName](#API_CreateSlotType_RequestSyntax) **   <a name="lexv2-CreateSlotType-request-slotTypeName"></a>
The name for the slot\. A slot type name must be unique within the account\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 100\.  
Pattern: `^([0-9a-zA-Z][_-]?)+$`   
Required: Yes

 ** [slotTypeValues](#API_CreateSlotType_RequestSyntax) **   <a name="lexv2-CreateSlotType-request-slotTypeValues"></a>
A list of `SlotTypeValue` objects that defines the values that the slot type can take\. Each value can have a list of synonyms, additional values that help train the machine learning model about the values that it resolves for a slot\.  
Type: Array of [SlotTypeValue](API_SlotTypeValue.md) objects  
Array Members: Minimum number of 1 item\. Maximum number of 10000 items\.  
Required: No

 ** [valueSelectionSetting](#API_CreateSlotType_RequestSyntax) **   <a name="lexv2-CreateSlotType-request-valueSelectionSetting"></a>
Determines the strategy that Amazon Lex uses to select a value from the list of possible values\. The field can be set to one of the following values:  
+  `OriginalValue` \- Returns the value entered by the user, if the user value is similar to the slot value\.
+  `TopResolution` \- If there is a resolution list for the slot, return the first value in the resolution list\. If there is no resolution list, return null\.
If you don't specify the `valueSelectionSetting` parameter, the default is `OriginalValue`\.  
Type: [SlotValueSelectionSetting](API_SlotValueSelectionSetting.md) object  
Required: Yes

## Response Syntax<a name="API_CreateSlotType_ResponseSyntax"></a>

```
HTTP/1.1 200
Content-type: application/json

{
   "botId": "string",
   "botVersion": "string",
   "creationDateTime": number,
   "description": "string",
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

## Response Elements<a name="API_CreateSlotType_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 200 response\.

The following data is returned in JSON format by the service\.

 ** [botId](#API_CreateSlotType_ResponseSyntax) **   <a name="lexv2-CreateSlotType-response-botId"></a>
The identifier for the bot associated with the slot type\.  
Type: String  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$` 

 ** [botVersion](#API_CreateSlotType_ResponseSyntax) **   <a name="lexv2-CreateSlotType-response-botVersion"></a>
The version of the bot associated with the slot type\.  
Type: String  
Length Constraints: Fixed length of 5\.  
Pattern: `^DRAFT$` 

 ** [creationDateTime](#API_CreateSlotType_ResponseSyntax) **   <a name="lexv2-CreateSlotType-response-creationDateTime"></a>
A timestamp of the date and time that the slot type was created\.  
Type: Timestamp

 ** [description](#API_CreateSlotType_ResponseSyntax) **   <a name="lexv2-CreateSlotType-response-description"></a>
The description specified for the slot type\.  
Type: String  
Length Constraints: Minimum length of 0\. Maximum length of 200\.

 ** [localeId](#API_CreateSlotType_ResponseSyntax) **   <a name="lexv2-CreateSlotType-response-localeId"></a>
The specified language and local specified for the slot type\.  
Type: String

 ** [parentSlotTypeSignature](#API_CreateSlotType_ResponseSyntax) **   <a name="lexv2-CreateSlotType-response-parentSlotTypeSignature"></a>
The signature of the base slot type specified for the slot type\.  
Type: String

 ** [slotTypeId](#API_CreateSlotType_ResponseSyntax) **   <a name="lexv2-CreateSlotType-response-slotTypeId"></a>
The unique identifier assigned to the slot type\. Use this to identify the slot type in the `UpdateSlotType` and `DeleteSlotType` operations\.  
Type: String  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$` 

 ** [slotTypeName](#API_CreateSlotType_ResponseSyntax) **   <a name="lexv2-CreateSlotType-response-slotTypeName"></a>
The name specified for the slot type\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 100\.  
Pattern: `^([0-9a-zA-Z][_-]?)+$` 

 ** [slotTypeValues](#API_CreateSlotType_ResponseSyntax) **   <a name="lexv2-CreateSlotType-response-slotTypeValues"></a>
The list of values that the slot type can assume\.  
Type: Array of [SlotTypeValue](API_SlotTypeValue.md) objects  
Array Members: Minimum number of 1 item\. Maximum number of 10000 items\.

 ** [valueSelectionSetting](#API_CreateSlotType_ResponseSyntax) **   <a name="lexv2-CreateSlotType-response-valueSelectionSetting"></a>
The strategy that Amazon Lex uses to select a value from the list of possible values\.  
Type: [SlotValueSelectionSetting](API_SlotValueSelectionSetting.md) object

## Errors<a name="API_CreateSlotType_Errors"></a>

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

## See Also<a name="API_CreateSlotType_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [AWS Command Line Interface](https://docs.aws.amazon.com/goto/aws-cli/models.lex.v2-2020-08-07/CreateSlotType) 
+  [AWS SDK for \.NET](https://docs.aws.amazon.com/goto/DotNetSDKV3/models.lex.v2-2020-08-07/CreateSlotType) 
+  [AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/models.lex.v2-2020-08-07/CreateSlotType) 
+  [AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/models.lex.v2-2020-08-07/CreateSlotType) 
+  [AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/models.lex.v2-2020-08-07/CreateSlotType) 
+  [AWS SDK for JavaScript](https://docs.aws.amazon.com/goto/AWSJavaScriptSDK/models.lex.v2-2020-08-07/CreateSlotType) 
+  [AWS SDK for PHP V3](https://docs.aws.amazon.com/goto/SdkForPHPV3/models.lex.v2-2020-08-07/CreateSlotType) 
+  [AWS SDK for Python](https://docs.aws.amazon.com/goto/boto3/models.lex.v2-2020-08-07/CreateSlotType) 
+  [AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/models.lex.v2-2020-08-07/CreateSlotType) 