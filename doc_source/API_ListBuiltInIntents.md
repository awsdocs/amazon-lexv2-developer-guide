# ListBuiltInIntents<a name="API_ListBuiltInIntents"></a>

Gets a list of built\-in intents provided by Amazon Lex that you can use in your bot\. 

To use a built\-in intent as a the base for your own intent, include the built\-in intent signature in the `parentIntentSignature` parameter when you call the `CreateIntent` operation\. For more information, see [CreateIntent](API_CreateIntent.md)\.

## Request Syntax<a name="API_ListBuiltInIntents_RequestSyntax"></a>

```
POST /builtins/locales/localeId/intents/ HTTP/1.1
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

## URI Request Parameters<a name="API_ListBuiltInIntents_RequestParameters"></a>

The request uses the following URI parameters\.

 ** [localeId](#API_ListBuiltInIntents_RequestSyntax) **   <a name="lexv2-ListBuiltInIntents-request-localeId"></a>
The identifier of the language and locale of the intents to list\. The string must match one of the supported locales\. For more information, see [Supported languages](https://docs.aws.amazon.com/lexv2/latest/dg/how-languages.html)\.  
Required: Yes

## Request Body<a name="API_ListBuiltInIntents_RequestBody"></a>

The request accepts the following data in JSON format\.

 ** [maxResults](#API_ListBuiltInIntents_RequestSyntax) **   <a name="lexv2-ListBuiltInIntents-request-maxResults"></a>
The maximum number of built\-in intents to return in each page of results\. If there are fewer results than the max page size, only the actual number of results are returned\.  
Type: Integer  
Valid Range: Fixed value of 20\.  
Required: No

 ** [nextToken](#API_ListBuiltInIntents_RequestSyntax) **   <a name="lexv2-ListBuiltInIntents-request-nextToken"></a>
If the response from the `ListBuiltInIntents` operation contains more results than specified in the `maxResults` parameter, a token is returned in the response\. Use that token in the `nextToken` parameter to return the next page of results\.  
Type: String  
Required: No

 ** [sortBy](#API_ListBuiltInIntents_RequestSyntax) **   <a name="lexv2-ListBuiltInIntents-request-sortBy"></a>
Specifies sorting parameters for the list of built\-in intents\. You can specify that the list be sorted by the built\-in intent signature in either ascending or descending order\.  
Type: [BuiltInIntentSortBy](API_BuiltInIntentSortBy.md) object  
Required: No

## Response Syntax<a name="API_ListBuiltInIntents_ResponseSyntax"></a>

```
HTTP/1.1 200
Content-type: application/json

{
   "builtInIntentSummaries": [ 
      { 
         "description": "string",
         "intentSignature": "string"
      }
   ],
   "localeId": "string",
   "nextToken": "string"
}
```

## Response Elements<a name="API_ListBuiltInIntents_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 200 response\.

The following data is returned in JSON format by the service\.

 ** [builtInIntentSummaries](#API_ListBuiltInIntents_ResponseSyntax) **   <a name="lexv2-ListBuiltInIntents-response-builtInIntentSummaries"></a>
Summary information for the built\-in intents that meet the filter criteria specified in the request\. The length of the list is specified in the `maxResults` parameter of the request\. If there are more intents available, the `nextToken` field contains a token to get the next page of results\.  
Type: Array of [BuiltInIntentSummary](API_BuiltInIntentSummary.md) objects

 ** [localeId](#API_ListBuiltInIntents_ResponseSyntax) **   <a name="lexv2-ListBuiltInIntents-response-localeId"></a>
The language and locale of the intents in the list\.  
Type: String

 ** [nextToken](#API_ListBuiltInIntents_ResponseSyntax) **   <a name="lexv2-ListBuiltInIntents-response-nextToken"></a>
A token that indicates whether there are more results to return in a response to the `ListBuiltInIntents` operation\. If the `nextToken` field is present, you send the contents as the `nextToken` parameter of a `ListBotAliases` operation request to get the next page of results\.  
Type: String

## Errors<a name="API_ListBuiltInIntents_Errors"></a>

For information about the errors that are common to all actions, see [Common Errors](CommonErrors.md)\.

 **InternalServerException**   
  
HTTP Status Code: 500

 **ServiceQuotaExceededException**   
  
HTTP Status Code: 402

 **ThrottlingException**   
  
HTTP Status Code: 429

 **ValidationException**   
  
HTTP Status Code: 400

## See Also<a name="API_ListBuiltInIntents_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [ AWS Command Line Interface](https://docs.aws.amazon.com/goto/aws-cli/models.lex.v2-2020-08-07/ListBuiltInIntents) 
+  [ AWS SDK for \.NET](https://docs.aws.amazon.com/goto/DotNetSDKV3/models.lex.v2-2020-08-07/ListBuiltInIntents) 
+  [ AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/models.lex.v2-2020-08-07/ListBuiltInIntents) 
+  [ AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/models.lex.v2-2020-08-07/ListBuiltInIntents) 
+  [ AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/models.lex.v2-2020-08-07/ListBuiltInIntents) 
+  [ AWS SDK for JavaScript](https://docs.aws.amazon.com/goto/AWSJavaScriptSDK/models.lex.v2-2020-08-07/ListBuiltInIntents) 
+  [ AWS SDK for PHP V3](https://docs.aws.amazon.com/goto/SdkForPHPV3/models.lex.v2-2020-08-07/ListBuiltInIntents) 
+  [ AWS SDK for Python](https://docs.aws.amazon.com/goto/boto3/models.lex.v2-2020-08-07/ListBuiltInIntents) 
+  [ AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/models.lex.v2-2020-08-07/ListBuiltInIntents) 