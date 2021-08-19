# ListBotLocales<a name="API_ListBotLocales"></a>

Gets a list of locales for the specified bot\.

## Request Syntax<a name="API_ListBotLocales_RequestSyntax"></a>

```
POST /bots/botId/botversions/botVersion/botlocales/ HTTP/1.1
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

## URI Request Parameters<a name="API_ListBotLocales_RequestParameters"></a>

The request uses the following URI parameters\.

 ** [botId](#API_ListBotLocales_RequestSyntax) **   <a name="lexv2-ListBotLocales-request-botId"></a>
The identifier of the bot to list locales for\.  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$`   
Required: Yes

 ** [botVersion](#API_ListBotLocales_RequestSyntax) **   <a name="lexv2-ListBotLocales-request-botVersion"></a>
The version of the bot to list locales for\.  
Length Constraints: Minimum length of 1\. Maximum length of 5\.  
Pattern: `^(DRAFT|[0-9]+)$`   
Required: Yes

## Request Body<a name="API_ListBotLocales_RequestBody"></a>

The request accepts the following data in JSON format\.

 ** [filters](#API_ListBotLocales_RequestSyntax) **   <a name="lexv2-ListBotLocales-request-filters"></a>
Provides the specification for a filter used to limit the response to only those locales that match the filter specification\. You can only specify one filter and one value to filter on\.  
Type: Array of [BotLocaleFilter](API_BotLocaleFilter.md) objects  
Array Members: Fixed number of 1 item\.  
Required: No

 ** [maxResults](#API_ListBotLocales_RequestSyntax) **   <a name="lexv2-ListBotLocales-request-maxResults"></a>
The maximum number of aliases to return in each page of results\. If there are fewer results than the max page size, only the actual number of results are returned\.  
Type: Integer  
Valid Range: Minimum value of 1\. Maximum value of 1000\.  
Required: No

 ** [nextToken](#API_ListBotLocales_RequestSyntax) **   <a name="lexv2-ListBotLocales-request-nextToken"></a>
If the response from the `ListBotLocales` operation contains more results than specified in the `maxResults` parameter, a token is returned in the response\. Use that token as the `nextToken` parameter to return the next page of results\.   
Type: String  
Required: No

 ** [sortBy](#API_ListBotLocales_RequestSyntax) **   <a name="lexv2-ListBotLocales-request-sortBy"></a>
Specifies sorting parameters for the list of locales\. You can sort by locale name in ascending or descending order\.  
Type: [BotLocaleSortBy](API_BotLocaleSortBy.md) object  
Required: No

## Response Syntax<a name="API_ListBotLocales_ResponseSyntax"></a>

```
HTTP/1.1 200
Content-type: application/json

{
   "botId": "string",
   "botLocaleSummaries": [ 
      { 
         "botLocaleStatus": "string",
         "description": "string",
         "lastBuildSubmittedDateTime": number,
         "lastUpdatedDateTime": number,
         "localeId": "string",
         "localeName": "string"
      }
   ],
   "botVersion": "string",
   "nextToken": "string"
}
```

## Response Elements<a name="API_ListBotLocales_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 200 response\.

The following data is returned in JSON format by the service\.

 ** [botId](#API_ListBotLocales_ResponseSyntax) **   <a name="lexv2-ListBotLocales-response-botId"></a>
The identifier of the bot to list locales for\.  
Type: String  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$` 

 ** [botLocaleSummaries](#API_ListBotLocales_ResponseSyntax) **   <a name="lexv2-ListBotLocales-response-botLocaleSummaries"></a>
Summary information for the locales that meet the filter criteria specified in the request\. The length of the list is specified in the `maxResults` parameter of the request\. If there are more locales available, the `nextToken` field contains a token to get the next page of results\.  
Type: Array of [BotLocaleSummary](API_BotLocaleSummary.md) objects

 ** [botVersion](#API_ListBotLocales_ResponseSyntax) **   <a name="lexv2-ListBotLocales-response-botVersion"></a>
The version of the bot\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 5\.  
Pattern: `^(DRAFT|[0-9]+)$` 

 ** [nextToken](#API_ListBotLocales_ResponseSyntax) **   <a name="lexv2-ListBotLocales-response-nextToken"></a>
A token that indicates whether there are more results to return in a response to the `ListBotLocales` operation\. If the `nextToken` field is present, you send the contents as the `nextToken` parameter of a `ListBotLocales` operation request to get the next page of results\.  
Type: String

## Errors<a name="API_ListBotLocales_Errors"></a>

For information about the errors that are common to all actions, see [Common Errors](CommonErrors.md)\.

 **InternalServerException**   
  
HTTP Status Code: 500

 **ServiceQuotaExceededException**   
  
HTTP Status Code: 402

 **ThrottlingException**   
  
HTTP Status Code: 429

 **ValidationException**   
  
HTTP Status Code: 400

## See Also<a name="API_ListBotLocales_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [ AWS Command Line Interface](https://docs.aws.amazon.com/goto/aws-cli/models.lex.v2-2020-08-07/ListBotLocales) 
+  [ AWS SDK for \.NET](https://docs.aws.amazon.com/goto/DotNetSDKV3/models.lex.v2-2020-08-07/ListBotLocales) 
+  [ AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/models.lex.v2-2020-08-07/ListBotLocales) 
+  [ AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/models.lex.v2-2020-08-07/ListBotLocales) 
+  [ AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/models.lex.v2-2020-08-07/ListBotLocales) 
+  [ AWS SDK for JavaScript](https://docs.aws.amazon.com/goto/AWSJavaScriptSDK/models.lex.v2-2020-08-07/ListBotLocales) 
+  [ AWS SDK for PHP V3](https://docs.aws.amazon.com/goto/SdkForPHPV3/models.lex.v2-2020-08-07/ListBotLocales) 
+  [ AWS SDK for Python](https://docs.aws.amazon.com/goto/boto3/models.lex.v2-2020-08-07/ListBotLocales) 
+  [ AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/models.lex.v2-2020-08-07/ListBotLocales) 