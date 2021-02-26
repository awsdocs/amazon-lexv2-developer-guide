# DeleteBotLocale<a name="API_DeleteBotLocale"></a>

Removes a locale from a bot\.

When you delete a locale, all intents, slots, and slot types defined for the locale are also deleted\.

## Request Syntax<a name="API_DeleteBotLocale_RequestSyntax"></a>

```
DELETE /bots/botId/botversions/botVersion/botlocales/localeId/ HTTP/1.1
```

## URI Request Parameters<a name="API_DeleteBotLocale_RequestParameters"></a>

The request uses the following URI parameters\.

 ** [botId](#API_DeleteBotLocale_RequestSyntax) **   <a name="lexv2-DeleteBotLocale-request-botId"></a>
The unique identifier of the bot that contains the locale\.  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$`   
Required: Yes

 ** [botVersion](#API_DeleteBotLocale_RequestSyntax) **   <a name="lexv2-DeleteBotLocale-request-botVersion"></a>
The version of the bot that contains the locale\.   
Length Constraints: Fixed length of 5\.  
Pattern: `^DRAFT$`   
Required: Yes

 ** [localeId](#API_DeleteBotLocale_RequestSyntax) **   <a name="lexv2-DeleteBotLocale-request-localeId"></a>
The identifier of the language and locale that will be deleted\. The string must match one of the supported locales\. For more information, see [https://docs.aws.amazon.com/lex/latest/dg/supported-locales.html](https://docs.aws.amazon.com/lex/latest/dg/supported-locales.html)\.  
Required: Yes

## Request Body<a name="API_DeleteBotLocale_RequestBody"></a>

The request does not have a request body\.

## Response Syntax<a name="API_DeleteBotLocale_ResponseSyntax"></a>

```
HTTP/1.1 202
Content-type: application/json

{
   "botId": "string",
   "botLocaleStatus": "string",
   "botVersion": "string",
   "localeId": "string"
}
```

## Response Elements<a name="API_DeleteBotLocale_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 202 response\.

The following data is returned in JSON format by the service\.

 ** [botId](#API_DeleteBotLocale_ResponseSyntax) **   <a name="lexv2-DeleteBotLocale-response-botId"></a>
The identifier of the bot that contained the deleted locale\.  
Type: String  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$` 

 ** [botLocaleStatus](#API_DeleteBotLocale_ResponseSyntax) **   <a name="lexv2-DeleteBotLocale-response-botLocaleStatus"></a>
The status of deleting the bot locale\. The locale first enters the `Deleting` status\. Once the locale is deleted it no longer appears in the list of locales for the bot\.  
Type: String  
Valid Values:` Creating | Building | Built | ReadyExpressTesting | Failed | Deleting | NotBuilt` 

 ** [botVersion](#API_DeleteBotLocale_ResponseSyntax) **   <a name="lexv2-DeleteBotLocale-response-botVersion"></a>
The version of the bot that contained the deleted locale\.  
Type: String  
Length Constraints: Fixed length of 5\.  
Pattern: `^DRAFT$` 

 ** [localeId](#API_DeleteBotLocale_ResponseSyntax) **   <a name="lexv2-DeleteBotLocale-response-localeId"></a>
The language and locale of the deleted locale\.  
Type: String

## Errors<a name="API_DeleteBotLocale_Errors"></a>

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

## See Also<a name="API_DeleteBotLocale_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [AWS Command Line Interface](https://docs.aws.amazon.com/goto/aws-cli/models.lex.v2-2020-08-07/DeleteBotLocale) 
+  [AWS SDK for \.NET](https://docs.aws.amazon.com/goto/DotNetSDKV3/models.lex.v2-2020-08-07/DeleteBotLocale) 
+  [AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/models.lex.v2-2020-08-07/DeleteBotLocale) 
+  [AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/models.lex.v2-2020-08-07/DeleteBotLocale) 
+  [AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/models.lex.v2-2020-08-07/DeleteBotLocale) 
+  [AWS SDK for JavaScript](https://docs.aws.amazon.com/goto/AWSJavaScriptSDK/models.lex.v2-2020-08-07/DeleteBotLocale) 
+  [AWS SDK for PHP V3](https://docs.aws.amazon.com/goto/SdkForPHPV3/models.lex.v2-2020-08-07/DeleteBotLocale) 
+  [AWS SDK for Python](https://docs.aws.amazon.com/goto/boto3/models.lex.v2-2020-08-07/DeleteBotLocale) 
+  [AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/models.lex.v2-2020-08-07/DeleteBotLocale) 