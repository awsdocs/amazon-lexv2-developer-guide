# DeleteBotVersion<a name="API_DeleteBotVersion"></a>

Deletes a specific version of a bot\. To delete all version of a bot, use the [DeleteBot](API_DeleteBot.md) operation\.

## Request Syntax<a name="API_DeleteBotVersion_RequestSyntax"></a>

```
DELETE /bots/botId/botversions/botVersion/?skipResourceInUseCheck=skipResourceInUseCheck HTTP/1.1
```

## URI Request Parameters<a name="API_DeleteBotVersion_RequestParameters"></a>

The request uses the following URI parameters\.

 ** [botId](#API_DeleteBotVersion_RequestSyntax) **   <a name="lexv2-DeleteBotVersion-request-botId"></a>
The identifier of the bot that contains the version\.  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$`   
Required: Yes

 ** [botVersion](#API_DeleteBotVersion_RequestSyntax) **   <a name="lexv2-DeleteBotVersion-request-botVersion"></a>
The version of the bot to delete\.  
Length Constraints: Minimum length of 1\. Maximum length of 5\.  
Pattern: `^[0-9]+$`   
Required: Yes

 ** [skipResourceInUseCheck](#API_DeleteBotVersion_RequestSyntax) **   <a name="lexv2-DeleteBotVersion-request-skipResourceInUseCheck"></a>
By default, the `DeleteBotVersion` operations throws a `ResourceInUseException` exception if you try to delete a bot version that has an alias pointing at it\. Set the `skipResourceInUseCheck` parameter to `true` to skip this check and remove the version even if an alias points to it\.

## Request Body<a name="API_DeleteBotVersion_RequestBody"></a>

The request does not have a request body\.

## Response Syntax<a name="API_DeleteBotVersion_ResponseSyntax"></a>

```
HTTP/1.1 202
Content-type: application/json

{
   "botId": "string",
   "botStatus": "string",
   "botVersion": "string"
}
```

## Response Elements<a name="API_DeleteBotVersion_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 202 response\.

The following data is returned in JSON format by the service\.

 ** [botId](#API_DeleteBotVersion_ResponseSyntax) **   <a name="lexv2-DeleteBotVersion-response-botId"></a>
The identifier of the bot that is being deleted\.  
Type: String  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$` 

 ** [botStatus](#API_DeleteBotVersion_ResponseSyntax) **   <a name="lexv2-DeleteBotVersion-response-botStatus"></a>
The current status of the bot\.   
Type: String  
Valid Values:` Creating | Available | Inactive | Deleting | Failed | Versioning | Importing` 

 ** [botVersion](#API_DeleteBotVersion_ResponseSyntax) **   <a name="lexv2-DeleteBotVersion-response-botVersion"></a>
The version of the bot that is being deleted\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 5\.  
Pattern: `^[0-9]+$` 

## Errors<a name="API_DeleteBotVersion_Errors"></a>

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

## See Also<a name="API_DeleteBotVersion_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [ AWS Command Line Interface](https://docs.aws.amazon.com/goto/aws-cli/models.lex.v2-2020-08-07/DeleteBotVersion) 
+  [ AWS SDK for \.NET](https://docs.aws.amazon.com/goto/DotNetSDKV3/models.lex.v2-2020-08-07/DeleteBotVersion) 
+  [ AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/models.lex.v2-2020-08-07/DeleteBotVersion) 
+  [ AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/models.lex.v2-2020-08-07/DeleteBotVersion) 
+  [ AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/models.lex.v2-2020-08-07/DeleteBotVersion) 
+  [ AWS SDK for JavaScript](https://docs.aws.amazon.com/goto/AWSJavaScriptSDK/models.lex.v2-2020-08-07/DeleteBotVersion) 
+  [ AWS SDK for PHP V3](https://docs.aws.amazon.com/goto/SdkForPHPV3/models.lex.v2-2020-08-07/DeleteBotVersion) 
+  [ AWS SDK for Python](https://docs.aws.amazon.com/goto/boto3/models.lex.v2-2020-08-07/DeleteBotVersion) 
+  [ AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/models.lex.v2-2020-08-07/DeleteBotVersion) 