# DeleteIntent<a name="API_DeleteIntent"></a>

Removes the specified intent\.

Deleting an intent also deletes the slots associated with the intent\.

## Request Syntax<a name="API_DeleteIntent_RequestSyntax"></a>

```
DELETE /bots/botId/botversions/botVersion/botlocales/localeId/intents/intentId/ HTTP/1.1
```

## URI Request Parameters<a name="API_DeleteIntent_RequestParameters"></a>

The request uses the following URI parameters\.

 ** [botId](#API_DeleteIntent_RequestSyntax) **   <a name="lexv2-DeleteIntent-request-botId"></a>
The identifier of the bot associated with the intent\.  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$`   
Required: Yes

 ** [botVersion](#API_DeleteIntent_RequestSyntax) **   <a name="lexv2-DeleteIntent-request-botVersion"></a>
The version of the bot associated with the intent\.  
Length Constraints: Fixed length of 5\.  
Pattern: `^DRAFT$`   
Required: Yes

 ** [intentId](#API_DeleteIntent_RequestSyntax) **   <a name="lexv2-DeleteIntent-request-intentId"></a>
The unique identifier of the intent to delete\.  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$`   
Required: Yes

 ** [localeId](#API_DeleteIntent_RequestSyntax) **   <a name="lexv2-DeleteIntent-request-localeId"></a>
The identifier of the language and locale where the bot will be deleted\. The string must match one of the supported locales\. For more information, see [https://docs.aws.amazon.com/lex/latest/dg/supported-locales.html](https://docs.aws.amazon.com/lex/latest/dg/supported-locales.html)\.  
Required: Yes

## Request Body<a name="API_DeleteIntent_RequestBody"></a>

The request does not have a request body\.

## Response Syntax<a name="API_DeleteIntent_ResponseSyntax"></a>

```
HTTP/1.1 204
```

## Response Elements<a name="API_DeleteIntent_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 204 response with an empty HTTP body\.

## Errors<a name="API_DeleteIntent_Errors"></a>

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

## See Also<a name="API_DeleteIntent_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [AWS Command Line Interface](https://docs.aws.amazon.com/goto/aws-cli/models.lex.v2-2020-08-07/DeleteIntent) 
+  [AWS SDK for \.NET](https://docs.aws.amazon.com/goto/DotNetSDKV3/models.lex.v2-2020-08-07/DeleteIntent) 
+  [AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/models.lex.v2-2020-08-07/DeleteIntent) 
+  [AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/models.lex.v2-2020-08-07/DeleteIntent) 
+  [AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/models.lex.v2-2020-08-07/DeleteIntent) 
+  [AWS SDK for JavaScript](https://docs.aws.amazon.com/goto/AWSJavaScriptSDK/models.lex.v2-2020-08-07/DeleteIntent) 
+  [AWS SDK for PHP V3](https://docs.aws.amazon.com/goto/SdkForPHPV3/models.lex.v2-2020-08-07/DeleteIntent) 
+  [AWS SDK for Python](https://docs.aws.amazon.com/goto/boto3/models.lex.v2-2020-08-07/DeleteIntent) 
+  [AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/models.lex.v2-2020-08-07/DeleteIntent) 