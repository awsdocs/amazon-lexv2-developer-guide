# DeleteBotAlias<a name="API_DeleteBotAlias"></a>

Deletes the specified bot alias\.

## Request Syntax<a name="API_DeleteBotAlias_RequestSyntax"></a>

```
DELETE /bots/botId/botaliases/botAliasId/?skipResourceInUseCheck=skipResourceInUseCheck HTTP/1.1
```

## URI Request Parameters<a name="API_DeleteBotAlias_RequestParameters"></a>

The request uses the following URI parameters\.

 ** [botAliasId](#API_DeleteBotAlias_RequestSyntax) **   <a name="lexv2-DeleteBotAlias-request-botAliasId"></a>
The unique identifier of the bot alias to delete\.  
Length Constraints: Fixed length of 10\.  
Pattern: `^(\bTSTALIASID\b|[0-9a-zA-Z]+)$`   
Required: Yes

 ** [botId](#API_DeleteBotAlias_RequestSyntax) **   <a name="lexv2-DeleteBotAlias-request-botId"></a>
The unique identifier of the bot associated with the alias to delete\.  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$`   
Required: Yes

 ** [skipResourceInUseCheck](#API_DeleteBotAlias_RequestSyntax) **   <a name="lexv2-DeleteBotAlias-request-skipResourceInUseCheck"></a>
When this parameter is true, Amazon Lex doesn't check to see if any other resource is using the alias before it is deleted\.

## Request Body<a name="API_DeleteBotAlias_RequestBody"></a>

The request does not have a request body\.

## Response Syntax<a name="API_DeleteBotAlias_ResponseSyntax"></a>

```
HTTP/1.1 202
Content-type: application/json

{
   "botAliasId": "string",
   "botAliasStatus": "string",
   "botId": "string"
}
```

## Response Elements<a name="API_DeleteBotAlias_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 202 response\.

The following data is returned in JSON format by the service\.

 ** [botAliasId](#API_DeleteBotAlias_ResponseSyntax) **   <a name="lexv2-DeleteBotAlias-response-botAliasId"></a>
The unique identifier of the bot alias to delete\.  
Type: String  
Length Constraints: Fixed length of 10\.  
Pattern: `^(\bTSTALIASID\b|[0-9a-zA-Z]+)$` 

 ** [botAliasStatus](#API_DeleteBotAlias_ResponseSyntax) **   <a name="lexv2-DeleteBotAlias-response-botAliasStatus"></a>
The current status of the alias\. The status is `Deleting` while the alias is in the process of being deleted\. Once the alias is deleted, it will no longer appear in the list of aliases returned by the `ListBotAliases` operation\.  
Type: String  
Valid Values:` Creating | Available | Deleting | Failed` 

 ** [botId](#API_DeleteBotAlias_ResponseSyntax) **   <a name="lexv2-DeleteBotAlias-response-botId"></a>
The unique identifier of the bot that contains the alias to delete\.  
Type: String  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$` 

## Errors<a name="API_DeleteBotAlias_Errors"></a>

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

## See Also<a name="API_DeleteBotAlias_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [AWS Command Line Interface](https://docs.aws.amazon.com/goto/aws-cli/models.lex.v2-2020-08-07/DeleteBotAlias) 
+  [AWS SDK for \.NET](https://docs.aws.amazon.com/goto/DotNetSDKV3/models.lex.v2-2020-08-07/DeleteBotAlias) 
+  [AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/models.lex.v2-2020-08-07/DeleteBotAlias) 
+  [AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/models.lex.v2-2020-08-07/DeleteBotAlias) 
+  [AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/models.lex.v2-2020-08-07/DeleteBotAlias) 
+  [AWS SDK for JavaScript](https://docs.aws.amazon.com/goto/AWSJavaScriptSDK/models.lex.v2-2020-08-07/DeleteBotAlias) 
+  [AWS SDK for PHP V3](https://docs.aws.amazon.com/goto/SdkForPHPV3/models.lex.v2-2020-08-07/DeleteBotAlias) 
+  [AWS SDK for Python](https://docs.aws.amazon.com/goto/boto3/models.lex.v2-2020-08-07/DeleteBotAlias) 
+  [AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/models.lex.v2-2020-08-07/DeleteBotAlias) 