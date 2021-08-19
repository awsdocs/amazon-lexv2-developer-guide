# ListBots<a name="API_ListBots"></a>

Gets a list of available bots\.

## Request Syntax<a name="API_ListBots_RequestSyntax"></a>

```
POST /bots/ HTTP/1.1
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

## URI Request Parameters<a name="API_ListBots_RequestParameters"></a>

The request does not use any URI parameters\.

## Request Body<a name="API_ListBots_RequestBody"></a>

The request accepts the following data in JSON format\.

 ** [filters](#API_ListBots_RequestSyntax) **   <a name="lexv2-ListBots-request-filters"></a>
Provides the specification of a filter used to limit the bots in the response to only those that match the filter specification\. You can only specify one filter and one string to filter on\.  
Type: Array of [BotFilter](API_BotFilter.md) objects  
Array Members: Fixed number of 1 item\.  
Required: No

 ** [maxResults](#API_ListBots_RequestSyntax) **   <a name="lexv2-ListBots-request-maxResults"></a>
The maximum number of bots to return in each page of results\. If there are fewer results than the maximum page size, only the actual number of results are returned\.  
Type: Integer  
Valid Range: Minimum value of 1\. Maximum value of 1000\.  
Required: No

 ** [nextToken](#API_ListBots_RequestSyntax) **   <a name="lexv2-ListBots-request-nextToken"></a>
If the response from the `ListBots` operation contains more results than specified in the `maxResults` parameter, a token is returned in the response\. Use that token in the `nextToken` parameter to return the next page of results\.  
Type: String  
Required: No

 ** [sortBy](#API_ListBots_RequestSyntax) **   <a name="lexv2-ListBots-request-sortBy"></a>
Specifies sorting parameters for the list of bots\. You can specify that the list be sorted by bot name in ascending or descending order\.  
Type: [BotSortBy](API_BotSortBy.md) object  
Required: No

## Response Syntax<a name="API_ListBots_ResponseSyntax"></a>

```
HTTP/1.1 200
Content-type: application/json

{
   "botSummaries": [ 
      { 
         "botId": "string",
         "botName": "string",
         "botStatus": "string",
         "description": "string",
         "lastUpdatedDateTime": number,
         "latestBotVersion": "string"
      }
   ],
   "nextToken": "string"
}
```

## Response Elements<a name="API_ListBots_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 200 response\.

The following data is returned in JSON format by the service\.

 ** [botSummaries](#API_ListBots_ResponseSyntax) **   <a name="lexv2-ListBots-response-botSummaries"></a>
Summary information for the bots that meet the filter criteria specified in the request\. The length of the list is specified in the `maxResults` parameter of the request\. If there are more bots available, the `nextToken` field contains a token to the next page of results\.  
Type: Array of [BotSummary](API_BotSummary.md) objects

 ** [nextToken](#API_ListBots_ResponseSyntax) **   <a name="lexv2-ListBots-response-nextToken"></a>
A token that indicates whether there are more results to return in a response to the `ListBots` operation\. If the `nextToken` field is present, you send the contents as the `nextToken` parameter of a `ListBots` operation request to get the next page of results\.  
Type: String

## Errors<a name="API_ListBots_Errors"></a>

For information about the errors that are common to all actions, see [Common Errors](CommonErrors.md)\.

 **InternalServerException**   
  
HTTP Status Code: 500

 **ServiceQuotaExceededException**   
  
HTTP Status Code: 402

 **ThrottlingException**   
  
HTTP Status Code: 429

 **ValidationException**   
  
HTTP Status Code: 400

## See Also<a name="API_ListBots_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [ AWS Command Line Interface](https://docs.aws.amazon.com/goto/aws-cli/models.lex.v2-2020-08-07/ListBots) 
+  [ AWS SDK for \.NET](https://docs.aws.amazon.com/goto/DotNetSDKV3/models.lex.v2-2020-08-07/ListBots) 
+  [ AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/models.lex.v2-2020-08-07/ListBots) 
+  [ AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/models.lex.v2-2020-08-07/ListBots) 
+  [ AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/models.lex.v2-2020-08-07/ListBots) 
+  [ AWS SDK for JavaScript](https://docs.aws.amazon.com/goto/AWSJavaScriptSDK/models.lex.v2-2020-08-07/ListBots) 
+  [ AWS SDK for PHP V3](https://docs.aws.amazon.com/goto/SdkForPHPV3/models.lex.v2-2020-08-07/ListBots) 
+  [ AWS SDK for Python](https://docs.aws.amazon.com/goto/boto3/models.lex.v2-2020-08-07/ListBots) 
+  [ AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/models.lex.v2-2020-08-07/ListBots) 