# ListIntents<a name="API_ListIntents"></a>

Get a list of intents that meet the specified criteria\.

## Request Syntax<a name="API_ListIntents_RequestSyntax"></a>

```
POST /bots/botId/botversions/botVersion/botlocales/localeId/intents/ HTTP/1.1
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

## URI Request Parameters<a name="API_ListIntents_RequestParameters"></a>

The request uses the following URI parameters\.

 ** [botId](#API_ListIntents_RequestSyntax) **   <a name="lexv2-ListIntents-request-botId"></a>
The unique identifier of the bot that contains the intent\.  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$`   
Required: Yes

 ** [botVersion](#API_ListIntents_RequestSyntax) **   <a name="lexv2-ListIntents-request-botVersion"></a>
The version of the bot that contains the intent\.  
Length Constraints: Minimum length of 1\. Maximum length of 5\.  
Pattern: `^(DRAFT|[0-9]+)$`   
Required: Yes

 ** [localeId](#API_ListIntents_RequestSyntax) **   <a name="lexv2-ListIntents-request-localeId"></a>
The identifier of the language and locale of the intents to list\. The string must match one of the supported locales\. For more information, see [Supported languages](https://docs.aws.amazon.com/lexv2/latest/dg/how-languages.html)\.  
Required: Yes

## Request Body<a name="API_ListIntents_RequestBody"></a>

The request accepts the following data in JSON format\.

 ** [filters](#API_ListIntents_RequestSyntax) **   <a name="lexv2-ListIntents-request-filters"></a>
Provides the specification of a filter used to limit the intents in the response to only those that match the filter specification\. You can only specify one filter and only one string to filter on\.  
Type: Array of [IntentFilter](API_IntentFilter.md) objects  
Array Members: Fixed number of 1 item\.  
Required: No

 ** [maxResults](#API_ListIntents_RequestSyntax) **   <a name="lexv2-ListIntents-request-maxResults"></a>
The maximum number of intents to return in each page of results\. If there are fewer results than the max page size, only the actual number of results are returned\.  
Type: Integer  
Valid Range: Minimum value of 1\. Maximum value of 1000\.  
Required: No

 ** [nextToken](#API_ListIntents_RequestSyntax) **   <a name="lexv2-ListIntents-request-nextToken"></a>
If the response from the `ListIntents` operation contains more results than specified in the `maxResults` parameter, a token is returned in the response\. Use that token in the `nextToken` parameter to return the next page of results\.  
Type: String  
Required: No

 ** [sortBy](#API_ListIntents_RequestSyntax) **   <a name="lexv2-ListIntents-request-sortBy"></a>
Determines the sort order for the response from the `ListIntents` operation\. You can choose to sort by the intent name or last updated date in either ascending or descending order\.  
Type: [IntentSortBy](API_IntentSortBy.md) object  
Required: No

## Response Syntax<a name="API_ListIntents_ResponseSyntax"></a>

```
HTTP/1.1 200
Content-type: application/json

{
   "botId": "string",
   "botVersion": "string",
   "intentSummaries": [ 
      { 
         "description": "string",
         "inputContexts": [ 
            { 
               "name": "string"
            }
         ],
         "intentId": "string",
         "intentName": "string",
         "lastUpdatedDateTime": number,
         "outputContexts": [ 
            { 
               "name": "string",
               "timeToLiveInSeconds": number,
               "turnsToLive": number
            }
         ],
         "parentIntentSignature": "string"
      }
   ],
   "localeId": "string",
   "nextToken": "string"
}
```

## Response Elements<a name="API_ListIntents_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 200 response\.

The following data is returned in JSON format by the service\.

 ** [botId](#API_ListIntents_ResponseSyntax) **   <a name="lexv2-ListIntents-response-botId"></a>
The identifier of the bot that contains the intent\.  
Type: String  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$` 

 ** [botVersion](#API_ListIntents_ResponseSyntax) **   <a name="lexv2-ListIntents-response-botVersion"></a>
The version of the bot that contains the intent\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 5\.  
Pattern: `^(DRAFT|[0-9]+)$` 

 ** [intentSummaries](#API_ListIntents_ResponseSyntax) **   <a name="lexv2-ListIntents-response-intentSummaries"></a>
Summary information for the intents that meet the filter criteria specified in the request\. The length of the list is specified in the `maxResults` parameter of the request\. If there are more intents available, the `nextToken` field contains a token to get the next page of results\.  
Type: Array of [IntentSummary](API_IntentSummary.md) objects

 ** [localeId](#API_ListIntents_ResponseSyntax) **   <a name="lexv2-ListIntents-response-localeId"></a>
The language and locale of the intents in the list\.  
Type: String

 ** [nextToken](#API_ListIntents_ResponseSyntax) **   <a name="lexv2-ListIntents-response-nextToken"></a>
A token that indicates whether there are more results to return in a response to the `ListIntents` operation\. If the `nextToken` field is present, you send the contents as the `nextToken` parameter of a `ListIntents` operation request to get the next page of results\.  
Type: String

## Errors<a name="API_ListIntents_Errors"></a>

For information about the errors that are common to all actions, see [Common Errors](CommonErrors.md)\.

 **InternalServerException**   
  
HTTP Status Code: 500

 **ServiceQuotaExceededException**   
  
HTTP Status Code: 402

 **ThrottlingException**   
  
HTTP Status Code: 429

 **ValidationException**   
  
HTTP Status Code: 400

## See Also<a name="API_ListIntents_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [ AWS Command Line Interface](https://docs.aws.amazon.com/goto/aws-cli/models.lex.v2-2020-08-07/ListIntents) 
+  [ AWS SDK for \.NET](https://docs.aws.amazon.com/goto/DotNetSDKV3/models.lex.v2-2020-08-07/ListIntents) 
+  [ AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/models.lex.v2-2020-08-07/ListIntents) 
+  [ AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/models.lex.v2-2020-08-07/ListIntents) 
+  [ AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/models.lex.v2-2020-08-07/ListIntents) 
+  [ AWS SDK for JavaScript](https://docs.aws.amazon.com/goto/AWSJavaScriptSDK/models.lex.v2-2020-08-07/ListIntents) 
+  [ AWS SDK for PHP V3](https://docs.aws.amazon.com/goto/SdkForPHPV3/models.lex.v2-2020-08-07/ListIntents) 
+  [ AWS SDK for Python](https://docs.aws.amazon.com/goto/boto3/models.lex.v2-2020-08-07/ListIntents) 
+  [ AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/models.lex.v2-2020-08-07/ListIntents) 