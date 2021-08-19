# DeleteSession<a name="API_runtime_DeleteSession"></a>

Removes session information for a specified bot, alias, and user ID\. 

You can use this operation to restart a conversation with a bot\. When you remove a session, the entire history of the session is removed so that you can start again\.

You don't need to delete a session\. Sessions have a time limit and will expire\. Set the session time limit when you create the bot\. The default is 5 minutes, but you can specify anything between 1 minute and 24 hours\.

If you specify a bot or alias ID that doesn't exist, you receive a `BadRequestException.` 

If the locale doesn't exist in the bot, or if the locale hasn't been enables for the alias, you receive a `BadRequestException`\.

## Request Syntax<a name="API_runtime_DeleteSession_RequestSyntax"></a>

```
DELETE /bots/botId/botAliases/botAliasId/botLocales/localeId/sessions/sessionId HTTP/1.1
```

## URI Request Parameters<a name="API_runtime_DeleteSession_RequestParameters"></a>

The request uses the following URI parameters\.

 ** [botAliasId](#API_runtime_DeleteSession_RequestSyntax) **   <a name="lexv2-runtime_DeleteSession-request-botAliasId"></a>
The alias identifier in use for the bot that contains the session data\.  
Required: Yes

 ** [botId](#API_runtime_DeleteSession_RequestSyntax) **   <a name="lexv2-runtime_DeleteSession-request-botId"></a>
The identifier of the bot that contains the session data\.  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$`   
Required: Yes

 ** [localeId](#API_runtime_DeleteSession_RequestSyntax) **   <a name="lexv2-runtime_DeleteSession-request-localeId"></a>
The locale where the session is in use\.  
Length Constraints: Minimum length of 1\.  
Required: Yes

 ** [sessionId](#API_runtime_DeleteSession_RequestSyntax) **   <a name="lexv2-runtime_DeleteSession-request-sessionId"></a>
The identifier of the session to delete\.  
Length Constraints: Minimum length of 2\. Maximum length of 100\.  
Pattern: `[0-9a-zA-Z._:-]+`   
Required: Yes

## Request Body<a name="API_runtime_DeleteSession_RequestBody"></a>

The request does not have a request body\.

## Response Syntax<a name="API_runtime_DeleteSession_ResponseSyntax"></a>

```
HTTP/1.1 200
Content-type: application/json

{
   "botAliasId": "string",
   "botId": "string",
   "localeId": "string",
   "sessionId": "string"
}
```

## Response Elements<a name="API_runtime_DeleteSession_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 200 response\.

The following data is returned in JSON format by the service\.

 ** [botAliasId](#API_runtime_DeleteSession_ResponseSyntax) **   <a name="lexv2-runtime_DeleteSession-response-botAliasId"></a>
The alias identifier in use for the bot that contained the session data\.  
Type: String

 ** [botId](#API_runtime_DeleteSession_ResponseSyntax) **   <a name="lexv2-runtime_DeleteSession-response-botId"></a>
The identifier of the bot that contained the session data\.  
Type: String  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$` 

 ** [localeId](#API_runtime_DeleteSession_ResponseSyntax) **   <a name="lexv2-runtime_DeleteSession-response-localeId"></a>
The locale where the session was used\.  
Type: String  
Length Constraints: Minimum length of 1\.

 ** [sessionId](#API_runtime_DeleteSession_ResponseSyntax) **   <a name="lexv2-runtime_DeleteSession-response-sessionId"></a>
The identifier of the deleted session\.  
Type: String  
Length Constraints: Minimum length of 2\. Maximum length of 100\.  
Pattern: `[0-9a-zA-Z._:-]+` 

## Errors<a name="API_runtime_DeleteSession_Errors"></a>

For information about the errors that are common to all actions, see [Common Errors](CommonErrors.md)\.

 **AccessDeniedException**   
  
HTTP Status Code: 403

 **ConflictException**   
  
HTTP Status Code: 409

 **InternalServerException**   
  
HTTP Status Code: 500

 **ResourceNotFoundException**   
  
HTTP Status Code: 404

 **ThrottlingException**   
  
HTTP Status Code: 429

 **ValidationException**   
  
HTTP Status Code: 400

## See Also<a name="API_runtime_DeleteSession_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [ AWS Command Line Interface](https://docs.aws.amazon.com/goto/aws-cli/runtime.lex.v2-2020-08-07/DeleteSession) 
+  [ AWS SDK for \.NET](https://docs.aws.amazon.com/goto/DotNetSDKV3/runtime.lex.v2-2020-08-07/DeleteSession) 
+  [ AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/runtime.lex.v2-2020-08-07/DeleteSession) 
+  [ AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/runtime.lex.v2-2020-08-07/DeleteSession) 
+  [ AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/runtime.lex.v2-2020-08-07/DeleteSession) 
+  [ AWS SDK for JavaScript](https://docs.aws.amazon.com/goto/AWSJavaScriptSDK/runtime.lex.v2-2020-08-07/DeleteSession) 
+  [ AWS SDK for PHP V3](https://docs.aws.amazon.com/goto/SdkForPHPV3/runtime.lex.v2-2020-08-07/DeleteSession) 
+  [ AWS SDK for Python](https://docs.aws.amazon.com/goto/boto3/runtime.lex.v2-2020-08-07/DeleteSession) 
+  [ AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/runtime.lex.v2-2020-08-07/DeleteSession) 