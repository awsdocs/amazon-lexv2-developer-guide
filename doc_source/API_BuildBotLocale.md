# BuildBotLocale<a name="API_BuildBotLocale"></a>

Builds a bot, its intents, and its slot types into a specific locale\. A bot can be built into multiple locales\. At runtime the locale is used to choose a specific build of the bot\.

## Request Syntax<a name="API_BuildBotLocale_RequestSyntax"></a>

```
POST /bots/botId/botversions/botVersion/botlocales/localeId/ HTTP/1.1
```

## URI Request Parameters<a name="API_BuildBotLocale_RequestParameters"></a>

The request uses the following URI parameters\.

 ** [botId](#API_BuildBotLocale_RequestSyntax) **   <a name="lexv2-BuildBotLocale-request-botId"></a>
The identifier of the bot to build\. The identifier is returned in the response from the [CreateBot](API_CreateBot.md) operation\.  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$`   
Required: Yes

 ** [botVersion](#API_BuildBotLocale_RequestSyntax) **   <a name="lexv2-BuildBotLocale-request-botVersion"></a>
The version of the bot to build\. This can only be the draft version of the bot\.  
Length Constraints: Fixed length of 5\.  
Pattern: `^DRAFT$`   
Required: Yes

 ** [localeId](#API_BuildBotLocale_RequestSyntax) **   <a name="lexv2-BuildBotLocale-request-localeId"></a>
The identifier of the language and locale that the bot will be used in\. The string must match one of the supported locales\. All of the intents, slot types, and slots used in the bot must have the same locale\. For more information, see [https://docs.aws.amazon.com/lex/latest/dg/supported-locales.html](https://docs.aws.amazon.com/lex/latest/dg/supported-locales.html)\.  
Required: Yes

## Request Body<a name="API_BuildBotLocale_RequestBody"></a>

The request does not have a request body\.

## Response Syntax<a name="API_BuildBotLocale_ResponseSyntax"></a>

```
HTTP/1.1 202
Content-type: application/json

{
   "botId": "string",
   "botLocaleStatus": "string",
   "botVersion": "string",
   "lastBuildSubmittedDateTime": number,
   "localeId": "string"
}
```

## Response Elements<a name="API_BuildBotLocale_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 202 response\.

The following data is returned in JSON format by the service\.

 ** [botId](#API_BuildBotLocale_ResponseSyntax) **   <a name="lexv2-BuildBotLocale-response-botId"></a>
The identifier of the specified bot\.  
Type: String  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$` 

 ** [botLocaleStatus](#API_BuildBotLocale_ResponseSyntax) **   <a name="lexv2-BuildBotLocale-response-botLocaleStatus"></a>
The bot's build status\. When the status is `ReadyExpressTesting` you can test the bot using the utterances defined for the intents and slot types\. When the status is `Built`, the bot is ready for use and can be tested using any utterance\.  
Type: String  
Valid Values:` Creating | Building | Built | ReadyExpressTesting | Failed | Deleting | NotBuilt` 

 ** [botVersion](#API_BuildBotLocale_ResponseSyntax) **   <a name="lexv2-BuildBotLocale-response-botVersion"></a>
The version of the bot that was built\. This is only the draft version of the bot\.  
Type: String  
Length Constraints: Fixed length of 5\.  
Pattern: `^DRAFT$` 

 ** [lastBuildSubmittedDateTime](#API_BuildBotLocale_ResponseSyntax) **   <a name="lexv2-BuildBotLocale-response-lastBuildSubmittedDateTime"></a>
A timestamp indicating the date and time that the bot was last built for this locale\.  
Type: Timestamp

 ** [localeId](#API_BuildBotLocale_ResponseSyntax) **   <a name="lexv2-BuildBotLocale-response-localeId"></a>
The language and locale specified of where the bot can be used\.  
Type: String

## Errors<a name="API_BuildBotLocale_Errors"></a>

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

## See Also<a name="API_BuildBotLocale_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [AWS Command Line Interface](https://docs.aws.amazon.com/goto/aws-cli/models.lex.v2-2020-08-07/BuildBotLocale) 
+  [AWS SDK for \.NET](https://docs.aws.amazon.com/goto/DotNetSDKV3/models.lex.v2-2020-08-07/BuildBotLocale) 
+  [AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/models.lex.v2-2020-08-07/BuildBotLocale) 
+  [AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/models.lex.v2-2020-08-07/BuildBotLocale) 
+  [AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/models.lex.v2-2020-08-07/BuildBotLocale) 
+  [AWS SDK for JavaScript](https://docs.aws.amazon.com/goto/AWSJavaScriptSDK/models.lex.v2-2020-08-07/BuildBotLocale) 
+  [AWS SDK for PHP V3](https://docs.aws.amazon.com/goto/SdkForPHPV3/models.lex.v2-2020-08-07/BuildBotLocale) 
+  [AWS SDK for Python](https://docs.aws.amazon.com/goto/boto3/models.lex.v2-2020-08-07/BuildBotLocale) 
+  [AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/models.lex.v2-2020-08-07/BuildBotLocale) 