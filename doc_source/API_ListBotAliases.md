# ListBotAliases<a name="API_ListBotAliases"></a>

Gets a list of aliases for the specified bot\.

## Request Syntax<a name="API_ListBotAliases_RequestSyntax"></a>

```
POST /bots/botId/botaliases/ HTTP/1.1
Content-type: application/json

{
   "maxResults": number,
   "nextToken": "string"
}
```

## URI Request Parameters<a name="API_ListBotAliases_RequestParameters"></a>

The request uses the following URI parameters\.

 ** [botId](#API_ListBotAliases_RequestSyntax) **   <a name="lexv2-ListBotAliases-request-botId"></a>
The identifier of the bot to list aliases for\.  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$`   
Required: Yes

## Request Body<a name="API_ListBotAliases_RequestBody"></a>

The request accepts the following data in JSON format\.

 ** [maxResults](#API_ListBotAliases_RequestSyntax) **   <a name="lexv2-ListBotAliases-request-maxResults"></a>
The maximum number of aliases to return in each page of results\. If there are fewer results than the max page size, only the actual number of results are returned\.  
Type: Integer  
Valid Range: Minimum value of 1\. Maximum value of 1000\.  
Required: No

 ** [nextToken](#API_ListBotAliases_RequestSyntax) **   <a name="lexv2-ListBotAliases-request-nextToken"></a>
If the response from the `ListBotAliases` operation contains more results than specified in the `maxResults` parameter, a token is returned in the response\. Use that token in the `nextToken` parameter to return the next page of results\.  
Type: String  
Required: No

## Response Syntax<a name="API_ListBotAliases_ResponseSyntax"></a>

```
HTTP/1.1 200
Content-type: application/json

{
   "botAliasSummaries": [ 
      { 
         "botAliasId": "string",
         "botAliasName": "string",
         "botAliasStatus": "string",
         "botVersion": "string",
         "creationDateTime": number,
         "description": "string",
         "lastUpdatedDateTime": number
      }
   ],
   "botId": "string",
   "nextToken": "string"
}
```

## Response Elements<a name="API_ListBotAliases_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 200 response\.

The following data is returned in JSON format by the service\.

 ** [botAliasSummaries](#API_ListBotAliases_ResponseSyntax) **   <a name="lexv2-ListBotAliases-response-botAliasSummaries"></a>
Summary information for the bot aliases that meet the filter criteria specified in the request\. The length of the list is specified in the `maxResults` parameter of the request\. If there are more aliases available, the `nextToken` field contains a token to get the next page of results\.  
Type: Array of [BotAliasSummary](API_BotAliasSummary.md) objects

 ** [botId](#API_ListBotAliases_ResponseSyntax) **   <a name="lexv2-ListBotAliases-response-botId"></a>
The identifier of the bot associated with the aliases\.  
Type: String  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$` 

 ** [nextToken](#API_ListBotAliases_ResponseSyntax) **   <a name="lexv2-ListBotAliases-response-nextToken"></a>
A token that indicates whether there are more results to return in a response to the `ListBotAliases` operation\. If the `nextToken` field is present, you send the contents as the `nextToken` parameter of a `ListBotAliases` operation request to get the next page of results\.  
Type: String

## Errors<a name="API_ListBotAliases_Errors"></a>

For information about the errors that are common to all actions, see [Common Errors](CommonErrors.md)\.

 **InternalServerException**   
  
HTTP Status Code: 500

 **ServiceQuotaExceededException**   
  
HTTP Status Code: 402

 **ThrottlingException**   
  
HTTP Status Code: 429

 **ValidationException**   
  
HTTP Status Code: 400

## See Also<a name="API_ListBotAliases_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [ AWS Command Line Interface](https://docs.aws.amazon.com/goto/aws-cli/models.lex.v2-2020-08-07/ListBotAliases) 
+  [ AWS SDK for \.NET](https://docs.aws.amazon.com/goto/DotNetSDKV3/models.lex.v2-2020-08-07/ListBotAliases) 
+  [ AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/models.lex.v2-2020-08-07/ListBotAliases) 
+  [ AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/models.lex.v2-2020-08-07/ListBotAliases) 
+  [ AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/models.lex.v2-2020-08-07/ListBotAliases) 
+  [ AWS SDK for JavaScript](https://docs.aws.amazon.com/goto/AWSJavaScriptSDK/models.lex.v2-2020-08-07/ListBotAliases) 
+  [ AWS SDK for PHP V3](https://docs.aws.amazon.com/goto/SdkForPHPV3/models.lex.v2-2020-08-07/ListBotAliases) 
+  [ AWS SDK for Python](https://docs.aws.amazon.com/goto/boto3/models.lex.v2-2020-08-07/ListBotAliases) 
+  [ AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/models.lex.v2-2020-08-07/ListBotAliases) 