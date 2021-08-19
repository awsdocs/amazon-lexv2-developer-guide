# DeleteBot<a name="API_DeleteBot"></a>

Deletes all versions of a bot, including the `Draft` version\. To delete a specific version, use the `DeleteBotVersion` operation\.

When you delete a bot, all of the resources contained in the bot are also deleted\. Deleting a bot removes all locales, intents, slot, and slot types defined for the bot\.

If a bot has an alias, the `DeleteBot` operation returns a `ResourceInUseException` exception\. If you want to delete the bot and the alias, set the `skipResourceInUseCheck` parameter to `true`\.

## Request Syntax<a name="API_DeleteBot_RequestSyntax"></a>

```
DELETE /bots/botId/?skipResourceInUseCheck=skipResourceInUseCheck HTTP/1.1
```

## URI Request Parameters<a name="API_DeleteBot_RequestParameters"></a>

The request uses the following URI parameters\.

 ** [botId](#API_DeleteBot_RequestSyntax) **   <a name="lexv2-DeleteBot-request-botId"></a>
The identifier of the bot to delete\.   
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$`   
Required: Yes

 ** [skipResourceInUseCheck](#API_DeleteBot_RequestSyntax) **   <a name="lexv2-DeleteBot-request-skipResourceInUseCheck"></a>
When `true`, Amazon Lex doesn't check to see if another resource, such as an alias, is using the bot before it is deleted\.

## Request Body<a name="API_DeleteBot_RequestBody"></a>

The request does not have a request body\.

## Response Syntax<a name="API_DeleteBot_ResponseSyntax"></a>

```
HTTP/1.1 202
Content-type: application/json

{
   "botId": "string",
   "botStatus": "string"
}
```

## Response Elements<a name="API_DeleteBot_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 202 response\.

The following data is returned in JSON format by the service\.

 ** [botId](#API_DeleteBot_ResponseSyntax) **   <a name="lexv2-DeleteBot-response-botId"></a>
The unique identifier of the bot that Amazon Lex is deleting\.  
Type: String  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$` 

 ** [botStatus](#API_DeleteBot_ResponseSyntax) **   <a name="lexv2-DeleteBot-response-botStatus"></a>
The current status of the bot\. The status is `Deleting` while the bot and its associated resources are being deleted\.  
Type: String  
Valid Values:` Creating | Available | Inactive | Deleting | Failed | Versioning | Importing` 

## Errors<a name="API_DeleteBot_Errors"></a>

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

## See Also<a name="API_DeleteBot_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [ AWS Command Line Interface](https://docs.aws.amazon.com/goto/aws-cli/models.lex.v2-2020-08-07/DeleteBot) 
+  [ AWS SDK for \.NET](https://docs.aws.amazon.com/goto/DotNetSDKV3/models.lex.v2-2020-08-07/DeleteBot) 
+  [ AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/models.lex.v2-2020-08-07/DeleteBot) 
+  [ AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/models.lex.v2-2020-08-07/DeleteBot) 
+  [ AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/models.lex.v2-2020-08-07/DeleteBot) 
+  [ AWS SDK for JavaScript](https://docs.aws.amazon.com/goto/AWSJavaScriptSDK/models.lex.v2-2020-08-07/DeleteBot) 
+  [ AWS SDK for PHP V3](https://docs.aws.amazon.com/goto/SdkForPHPV3/models.lex.v2-2020-08-07/DeleteBot) 
+  [ AWS SDK for Python](https://docs.aws.amazon.com/goto/boto3/models.lex.v2-2020-08-07/DeleteBot) 
+  [ AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/models.lex.v2-2020-08-07/DeleteBot) 