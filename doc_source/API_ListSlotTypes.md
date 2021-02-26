# ListSlotTypes<a name="API_ListSlotTypes"></a>

Gets a list of slot types that match the specified criteria\.

## Request Syntax<a name="API_ListSlotTypes_RequestSyntax"></a>

```
POST /bots/botId/botversions/botVersion/botlocales/localeId/slottypes/ HTTP/1.1
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

## URI Request Parameters<a name="API_ListSlotTypes_RequestParameters"></a>

The request uses the following URI parameters\.

 ** [botId](#API_ListSlotTypes_RequestSyntax) **   <a name="lexv2-ListSlotTypes-request-botId"></a>
The unique identifier of the bot that contains the slot types\.  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$`   
Required: Yes

 ** [botVersion](#API_ListSlotTypes_RequestSyntax) **   <a name="lexv2-ListSlotTypes-request-botVersion"></a>
The version of the bot that contains the slot type\.  
Length Constraints: Minimum length of 1\. Maximum length of 5\.  
Pattern: `^(DRAFT|[0-9]+)$`   
Required: Yes

 ** [localeId](#API_ListSlotTypes_RequestSyntax) **   <a name="lexv2-ListSlotTypes-request-localeId"></a>
The identifier of the language and locale of the slot types to list\. The string must match one of the supported locales\. For more information, see [https://docs.aws.amazon.com/lex/latest/dg/supported-locales.html](https://docs.aws.amazon.com/lex/latest/dg/supported-locales.html)\.  
Required: Yes

## Request Body<a name="API_ListSlotTypes_RequestBody"></a>

The request accepts the following data in JSON format\.

 ** [filters](#API_ListSlotTypes_RequestSyntax) **   <a name="lexv2-ListSlotTypes-request-filters"></a>
Provides the specification of a filter used to limit the slot types in the response to only those that match the filter specification\. You can only specify one filter and only one string to filter on\.  
Type: Array of [SlotTypeFilter](API_SlotTypeFilter.md) objects  
Array Members: Fixed number of 1 item\.  
Required: No

 ** [maxResults](#API_ListSlotTypes_RequestSyntax) **   <a name="lexv2-ListSlotTypes-request-maxResults"></a>
The maximum number of slot types to return in each page of results\. If there are fewer results than the max page size, only the actual number of results are returned\.  
Type: Integer  
Valid Range: Minimum value of 1\. Maximum value of 1000\.  
Required: No

 ** [nextToken](#API_ListSlotTypes_RequestSyntax) **   <a name="lexv2-ListSlotTypes-request-nextToken"></a>
If the response from the `ListSlotTypes` operation contains more results than specified in the `maxResults` parameter, a token is returned in the response\. Use that token in the `nextToken` parameter to return the next page of results\.  
Type: String  
Required: No

 ** [sortBy](#API_ListSlotTypes_RequestSyntax) **   <a name="lexv2-ListSlotTypes-request-sortBy"></a>
Determines the sort order for the response from the `ListSlotTypes` operation\. You can choose to sort by the slot type name or last updated date in either ascending or descending order\.  
Type: [SlotTypeSortBy](API_SlotTypeSortBy.md) object  
Required: No

## Response Syntax<a name="API_ListSlotTypes_ResponseSyntax"></a>

```
HTTP/1.1 200
Content-type: application/json

{
   "botId": "string",
   "botVersion": "string",
   "localeId": "string",
   "nextToken": "string",
   "slotTypeSummaries": [ 
      { 
         "description": "string",
         "lastUpdatedDateTime": number,
         "parentSlotTypeSignature": "string",
         "slotTypeId": "string",
         "slotTypeName": "string"
      }
   ]
}
```

## Response Elements<a name="API_ListSlotTypes_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 200 response\.

The following data is returned in JSON format by the service\.

 ** [botId](#API_ListSlotTypes_ResponseSyntax) **   <a name="lexv2-ListSlotTypes-response-botId"></a>
The identifier of the bot that contains the slot types\.  
Type: String  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$` 

 ** [botVersion](#API_ListSlotTypes_ResponseSyntax) **   <a name="lexv2-ListSlotTypes-response-botVersion"></a>
The version of the bot that contains the slot types\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 5\.  
Pattern: `^(DRAFT|[0-9]+)$` 

 ** [localeId](#API_ListSlotTypes_ResponseSyntax) **   <a name="lexv2-ListSlotTypes-response-localeId"></a>
The language and local of the slot types in the list\.  
Type: String

 ** [nextToken](#API_ListSlotTypes_ResponseSyntax) **   <a name="lexv2-ListSlotTypes-response-nextToken"></a>
A token that indicates whether there are more results to return in a response to the `ListSlotTypes` operation\. If the `nextToken` field is present, you send the contents as the `nextToken` parameter of a `ListSlotTypes` operation request to get the next page of results\.  
Type: String

 ** [slotTypeSummaries](#API_ListSlotTypes_ResponseSyntax) **   <a name="lexv2-ListSlotTypes-response-slotTypeSummaries"></a>
Summary information for the slot types that meet the filter criteria specified in the request\. The length of the list is specified in the `maxResults` parameter of the request\. If there are more slot types available, the `nextToken` field contains a token to get the next page of results\.  
Type: Array of [SlotTypeSummary](API_SlotTypeSummary.md) objects

## Errors<a name="API_ListSlotTypes_Errors"></a>

For information about the errors that are common to all actions, see [Common Errors](CommonErrors.md)\.

 **InternalServerException**   
  
HTTP Status Code: 500

 **ServiceQuotaExceededException**   
  
HTTP Status Code: 402

 **ThrottlingException**   
  
HTTP Status Code: 429

 **ValidationException**   
  
HTTP Status Code: 400

## See Also<a name="API_ListSlotTypes_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [AWS Command Line Interface](https://docs.aws.amazon.com/goto/aws-cli/models.lex.v2-2020-08-07/ListSlotTypes) 
+  [AWS SDK for \.NET](https://docs.aws.amazon.com/goto/DotNetSDKV3/models.lex.v2-2020-08-07/ListSlotTypes) 
+  [AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/models.lex.v2-2020-08-07/ListSlotTypes) 
+  [AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/models.lex.v2-2020-08-07/ListSlotTypes) 
+  [AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/models.lex.v2-2020-08-07/ListSlotTypes) 
+  [AWS SDK for JavaScript](https://docs.aws.amazon.com/goto/AWSJavaScriptSDK/models.lex.v2-2020-08-07/ListSlotTypes) 
+  [AWS SDK for PHP V3](https://docs.aws.amazon.com/goto/SdkForPHPV3/models.lex.v2-2020-08-07/ListSlotTypes) 
+  [AWS SDK for Python](https://docs.aws.amazon.com/goto/boto3/models.lex.v2-2020-08-07/ListSlotTypes) 
+  [AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/models.lex.v2-2020-08-07/ListSlotTypes) 