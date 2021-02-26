# ListBotVersions<a name="API_ListBotVersions"></a>

Gets information about all of the versions of a bot\.

The `ListBotVersions` operation returns a summary of each version of a bot\. For example, if a bot has three numbered versions, the `ListBotVersions` operation returns for summaries, one for each numbered version and one for the `DRAFT` version\.

The `ListBotVersions` operation always returns at least one version, the `DRAFT` version\.

## Request Syntax<a name="API_ListBotVersions_RequestSyntax"></a>

```
POST /bots/botId/botversions/ HTTP/1.1
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

## URI Request Parameters<a name="API_ListBotVersions_RequestParameters"></a>

The request uses the following URI parameters\.

 ** [botId](#API_ListBotVersions_RequestSyntax) **   <a name="lexv2-ListBotVersions-request-botId"></a>
The identifier of the bot to list versions for\.  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$`   
Required: Yes

## Request Body<a name="API_ListBotVersions_RequestBody"></a>

The request accepts the following data in JSON format\.

 ** [maxResults](#API_ListBotVersions_RequestSyntax) **   <a name="lexv2-ListBotVersions-request-maxResults"></a>
The maximum number of versions to return in each page of results\. If there are fewer results than the max page size, only the actual number of results are returned\.  
Type: Integer  
Valid Range: Minimum value of 1\. Maximum value of 1000\.  
Required: No

 ** [nextToken](#API_ListBotVersions_RequestSyntax) **   <a name="lexv2-ListBotVersions-request-nextToken"></a>
If the response to the `ListBotVersion` operation contains more results than specified in the `maxResults` parameter, a token is returned in the response\. Use that token in the `nextToken` parameter to return the next page of results\.  
Type: String  
Required: No

 ** [sortBy](#API_ListBotVersions_RequestSyntax) **   <a name="lexv2-ListBotVersions-request-sortBy"></a>
Specifies sorting parameters for the list of versions\. You can specify that the list be sorted by version name in either ascending or descending order\.  
Type: [BotVersionSortBy](API_BotVersionSortBy.md) object  
Required: No

## Response Syntax<a name="API_ListBotVersions_ResponseSyntax"></a>

```
HTTP/1.1 200
Content-type: application/json

{
   "botId": "string",
   "botVersionSummaries": [ 
      { 
         "botName": "string",
         "botStatus": "string",
         "botVersion": "string",
         "creationDateTime": number,
         "description": "string"
      }
   ],
   "nextToken": "string"
}
```

## Response Elements<a name="API_ListBotVersions_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 200 response\.

The following data is returned in JSON format by the service\.

 ** [botId](#API_ListBotVersions_ResponseSyntax) **   <a name="lexv2-ListBotVersions-response-botId"></a>
The identifier of the bot to list versions for\.  
Type: String  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$` 

 ** [botVersionSummaries](#API_ListBotVersions_ResponseSyntax) **   <a name="lexv2-ListBotVersions-response-botVersionSummaries"></a>
Summary information for the bot versions that meet the filter criteria specified in the request\. The length of the list is specified in the `maxResults` parameter of the request\. If there are more versions available, the `nextToken` field contains a token to get the next page of results\.  
Type: Array of [BotVersionSummary](API_BotVersionSummary.md) objects

 ** [nextToken](#API_ListBotVersions_ResponseSyntax) **   <a name="lexv2-ListBotVersions-response-nextToken"></a>
A token that indicates whether there are more results to return in a response to the `ListBotVersions` operation\. If the `nextToken` field is present, you send the contents as the `nextToken` parameter of a `ListBotAliases` operation request to get the next page of results\.  
Type: String

## Errors<a name="API_ListBotVersions_Errors"></a>

For information about the errors that are common to all actions, see [Common Errors](CommonErrors.md)\.

 **InternalServerException**   
  
HTTP Status Code: 500

 **ServiceQuotaExceededException**   
  
HTTP Status Code: 402

 **ThrottlingException**   
  
HTTP Status Code: 429

 **ValidationException**   
  
HTTP Status Code: 400

## See Also<a name="API_ListBotVersions_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [AWS Command Line Interface](https://docs.aws.amazon.com/goto/aws-cli/models.lex.v2-2020-08-07/ListBotVersions) 
+  [AWS SDK for \.NET](https://docs.aws.amazon.com/goto/DotNetSDKV3/models.lex.v2-2020-08-07/ListBotVersions) 
+  [AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/models.lex.v2-2020-08-07/ListBotVersions) 
+  [AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/models.lex.v2-2020-08-07/ListBotVersions) 
+  [AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/models.lex.v2-2020-08-07/ListBotVersions) 
+  [AWS SDK for JavaScript](https://docs.aws.amazon.com/goto/AWSJavaScriptSDK/models.lex.v2-2020-08-07/ListBotVersions) 
+  [AWS SDK for PHP V3](https://docs.aws.amazon.com/goto/SdkForPHPV3/models.lex.v2-2020-08-07/ListBotVersions) 
+  [AWS SDK for Python](https://docs.aws.amazon.com/goto/boto3/models.lex.v2-2020-08-07/ListBotVersions) 
+  [AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/models.lex.v2-2020-08-07/ListBotVersions) 