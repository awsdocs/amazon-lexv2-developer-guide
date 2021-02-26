# DescribeSlotType<a name="API_DescribeSlotType"></a>

Gets metadata information about a slot type\.

## Request Syntax<a name="API_DescribeSlotType_RequestSyntax"></a>

```
GET /bots/botId/botversions/botVersion/botlocales/localeId/slottypes/slotTypeId/ HTTP/1.1
```

## URI Request Parameters<a name="API_DescribeSlotType_RequestParameters"></a>

The request uses the following URI parameters\.

 ** [botId](#API_DescribeSlotType_RequestSyntax) **   <a name="lexv2-DescribeSlotType-request-botId"></a>
The identifier of the bot associated with the slot type\.  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$`   
Required: Yes

 ** [botVersion](#API_DescribeSlotType_RequestSyntax) **   <a name="lexv2-DescribeSlotType-request-botVersion"></a>
The version of the bot associated with the slot type\.  
Length Constraints: Minimum length of 1\. Maximum length of 5\.  
Pattern: `^(DRAFT|[0-9]+)$`   
Required: Yes

 ** [localeId](#API_DescribeSlotType_RequestSyntax) **   <a name="lexv2-DescribeSlotType-request-localeId"></a>
The identifier of the language and locale of the slot type to describe\. The string must match one of the supported locales\. For more information, see [https://docs.aws.amazon.com/lex/latest/dg/supported-locales.html](https://docs.aws.amazon.com/lex/latest/dg/supported-locales.html)\.  
Required: Yes

 ** [slotTypeId](#API_DescribeSlotType_RequestSyntax) **   <a name="lexv2-DescribeSlotType-request-slotTypeId"></a>
The identifier of the slot type\.  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$`   
Required: Yes

## Request Body<a name="API_DescribeSlotType_RequestBody"></a>

The request does not have a request body\.

## Response Syntax<a name="API_DescribeSlotType_ResponseSyntax"></a>

```
HTTP/1.1 200
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

## Response Elements<a name="API_DescribeSlotType_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 200 response\.

The following data is returned in JSON format by the service\.

 ** [botId](#API_DescribeSlotType_ResponseSyntax) **   <a name="lexv2-DescribeSlotType-response-botId"></a>
The identifier of the bot associated with the slot type\.  
Type: String  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$` 

 ** [botVersion](#API_DescribeSlotType_ResponseSyntax) **   <a name="lexv2-DescribeSlotType-response-botVersion"></a>
The version of the bot associated with the slot type\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 5\.  
Pattern: `^(DRAFT|[0-9]+)$` 

 ** [creationDateTime](#API_DescribeSlotType_ResponseSyntax) **   <a name="lexv2-DescribeSlotType-response-creationDateTime"></a>
A timestamp of the date and time that the slot type was created\.  
Type: Timestamp

 ** [description](#API_DescribeSlotType_ResponseSyntax) **   <a name="lexv2-DescribeSlotType-response-description"></a>
The description specified for the slot type\.  
Type: String  
Length Constraints: Minimum length of 0\. Maximum length of 200\.

 ** [lastUpdatedDateTime](#API_DescribeSlotType_ResponseSyntax) **   <a name="lexv2-DescribeSlotType-response-lastUpdatedDateTime"></a>
A timestamp of the date and time that the slot type was last updated\.  
Type: Timestamp

 ** [localeId](#API_DescribeSlotType_ResponseSyntax) **   <a name="lexv2-DescribeSlotType-response-localeId"></a>
The language and locale specified for the slot type\.  
Type: String

 ** [parentSlotTypeSignature](#API_DescribeSlotType_ResponseSyntax) **   <a name="lexv2-DescribeSlotType-response-parentSlotTypeSignature"></a>
The built in slot type used as a parent to this slot type\.  
Type: String

 ** [slotTypeId](#API_DescribeSlotType_ResponseSyntax) **   <a name="lexv2-DescribeSlotType-response-slotTypeId"></a>
The unique identifier for the slot type\.  
Type: String  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$` 

 ** [slotTypeName](#API_DescribeSlotType_ResponseSyntax) **   <a name="lexv2-DescribeSlotType-response-slotTypeName"></a>
The name specified for the slot type\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 100\.  
Pattern: `^([0-9a-zA-Z][_-]?)+$` 

 ** [slotTypeValues](#API_DescribeSlotType_ResponseSyntax) **   <a name="lexv2-DescribeSlotType-response-slotTypeValues"></a>
The values that the slot type can take\. Includes any synonyms for the slot type values\.  
Type: Array of [SlotTypeValue](API_SlotTypeValue.md) objects  
Array Members: Minimum number of 1 item\. Maximum number of 10000 items\.

 ** [valueSelectionSetting](#API_DescribeSlotType_ResponseSyntax) **   <a name="lexv2-DescribeSlotType-response-valueSelectionSetting"></a>
The strategy that Amazon Lex uses to choose a value from a list of possible values\.  
Type: [SlotValueSelectionSetting](API_SlotValueSelectionSetting.md) object

## Errors<a name="API_DescribeSlotType_Errors"></a>

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

## See Also<a name="API_DescribeSlotType_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [AWS Command Line Interface](https://docs.aws.amazon.com/goto/aws-cli/models.lex.v2-2020-08-07/DescribeSlotType) 
+  [AWS SDK for \.NET](https://docs.aws.amazon.com/goto/DotNetSDKV3/models.lex.v2-2020-08-07/DescribeSlotType) 
+  [AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/models.lex.v2-2020-08-07/DescribeSlotType) 
+  [AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/models.lex.v2-2020-08-07/DescribeSlotType) 
+  [AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/models.lex.v2-2020-08-07/DescribeSlotType) 
+  [AWS SDK for JavaScript](https://docs.aws.amazon.com/goto/AWSJavaScriptSDK/models.lex.v2-2020-08-07/DescribeSlotType) 
+  [AWS SDK for PHP V3](https://docs.aws.amazon.com/goto/SdkForPHPV3/models.lex.v2-2020-08-07/DescribeSlotType) 
+  [AWS SDK for Python](https://docs.aws.amazon.com/goto/boto3/models.lex.v2-2020-08-07/DescribeSlotType) 
+  [AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/models.lex.v2-2020-08-07/DescribeSlotType) 