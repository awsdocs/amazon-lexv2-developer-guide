# ListBuiltInSlotTypes<a name="API_ListBuiltInSlotTypes"></a>

Gets a list of built\-in slot types that meet the specified criteria\.

## Request Syntax<a name="API_ListBuiltInSlotTypes_RequestSyntax"></a>

```
POST /builtins/locales/localeId/slottypes/ HTTP/1.1
Content-type: application/json

{
   "maxResults": number,
   "nextToken": "string",
   "sortBy": { 
      "attribute": "string",
      "order": "string"
   }
}
```

## URI Request Parameters<a name="API_ListBuiltInSlotTypes_RequestParameters"></a>

The request uses the following URI parameters\.

 ** [localeId](#API_ListBuiltInSlotTypes_RequestSyntax) **   <a name="lexv2-ListBuiltInSlotTypes-request-localeId"></a>
The identifier of the language and locale of the slot types to list\. The string must match one of the supported locales\. For more information, see [Supported languages](https://docs.aws.amazon.com/lexv2/latest/dg/how-languages.html)\.  
Required: Yes

## Request Body<a name="API_ListBuiltInSlotTypes_RequestBody"></a>

The request accepts the following data in JSON format\.

 ** [maxResults](#API_ListBuiltInSlotTypes_RequestSyntax) **   <a name="lexv2-ListBuiltInSlotTypes-request-maxResults"></a>
The maximum number of built\-in slot types to return in each page of results\. If there are fewer results than the max page size, only the actual number of results are returned\.  
Type: Integer  
Valid Range: Fixed value of 20\.  
Required: No

 ** [nextToken](#API_ListBuiltInSlotTypes_RequestSyntax) **   <a name="lexv2-ListBuiltInSlotTypes-request-nextToken"></a>
If the response from the `ListBuiltInSlotTypes` operation contains more results than specified in the `maxResults` parameter, a token is returned in the response\. Use that token in the `nextToken` parameter to return the next page of results\.  
Type: String  
Required: No

 ** [sortBy](#API_ListBuiltInSlotTypes_RequestSyntax) **   <a name="lexv2-ListBuiltInSlotTypes-request-sortBy"></a>
Determines the sort order for the response from the `ListBuiltInSlotTypes` operation\. You can choose to sort by the slot type signature in either ascending or descending order\.  
Type: [BuiltInSlotTypeSortBy](API_BuiltInSlotTypeSortBy.md) object  
Required: No

## Response Syntax<a name="API_ListBuiltInSlotTypes_ResponseSyntax"></a>

```
HTTP/1.1 200
Content-type: application/json

{
   "builtInSlotTypeSummaries": [ 
      { 
         "description": "string",
         "slotTypeSignature": "string"
      }
   ],
   "localeId": "string",
   "nextToken": "string"
}
```

## Response Elements<a name="API_ListBuiltInSlotTypes_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 200 response\.

The following data is returned in JSON format by the service\.

 ** [builtInSlotTypeSummaries](#API_ListBuiltInSlotTypes_ResponseSyntax) **   <a name="lexv2-ListBuiltInSlotTypes-response-builtInSlotTypeSummaries"></a>
Summary information for the built\-in slot types that meet the filter criteria specified in the request\. The length of the list is specified in the `maxResults` parameter of the request\. If there are more slot types available, the `nextToken` field contains a token to get the next page of results\.  
Type: Array of [BuiltInSlotTypeSummary](API_BuiltInSlotTypeSummary.md) objects

 ** [localeId](#API_ListBuiltInSlotTypes_ResponseSyntax) **   <a name="lexv2-ListBuiltInSlotTypes-response-localeId"></a>
The language and locale of the slot types in the list\.  
Type: String

 ** [nextToken](#API_ListBuiltInSlotTypes_ResponseSyntax) **   <a name="lexv2-ListBuiltInSlotTypes-response-nextToken"></a>
A token that indicates whether there are more results to return in a response to the `ListBuiltInSlotTypes` operation\. If the `nextToken` field is present, you send the contents as the `nextToken` parameter of a `LIstBuiltInSlotTypes` operation request to get the next page of results\.  
Type: String

## Errors<a name="API_ListBuiltInSlotTypes_Errors"></a>

For information about the errors that are common to all actions, see [Common Errors](CommonErrors.md)\.

 **InternalServerException**   
  
HTTP Status Code: 500

 **ServiceQuotaExceededException**   
  
HTTP Status Code: 402

 **ThrottlingException**   
  
HTTP Status Code: 429

 **ValidationException**   
  
HTTP Status Code: 400

## See Also<a name="API_ListBuiltInSlotTypes_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [ AWS Command Line Interface](https://docs.aws.amazon.com/goto/aws-cli/models.lex.v2-2020-08-07/ListBuiltInSlotTypes) 
+  [ AWS SDK for \.NET](https://docs.aws.amazon.com/goto/DotNetSDKV3/models.lex.v2-2020-08-07/ListBuiltInSlotTypes) 
+  [ AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/models.lex.v2-2020-08-07/ListBuiltInSlotTypes) 
+  [ AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/models.lex.v2-2020-08-07/ListBuiltInSlotTypes) 
+  [ AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/models.lex.v2-2020-08-07/ListBuiltInSlotTypes) 
+  [ AWS SDK for JavaScript](https://docs.aws.amazon.com/goto/AWSJavaScriptSDK/models.lex.v2-2020-08-07/ListBuiltInSlotTypes) 
+  [ AWS SDK for PHP V3](https://docs.aws.amazon.com/goto/SdkForPHPV3/models.lex.v2-2020-08-07/ListBuiltInSlotTypes) 
+  [ AWS SDK for Python](https://docs.aws.amazon.com/goto/boto3/models.lex.v2-2020-08-07/ListBuiltInSlotTypes) 
+  [ AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/models.lex.v2-2020-08-07/ListBuiltInSlotTypes) 