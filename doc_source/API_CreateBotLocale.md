# CreateBotLocale<a name="API_CreateBotLocale"></a>

Creates a locale in the bot\. The locale contains the intents and slot types that the bot uses in conversations with users in the specified language and locale\. You must add a locale to a bot before you can add intents and slot types to the bot\.

## Request Syntax<a name="API_CreateBotLocale_RequestSyntax"></a>

```
PUT /bots/botId/botversions/botVersion/botlocales/ HTTP/1.1
Content-type: application/json

{
   "description": "string",
   "localeId": "string",
   "nluIntentConfidenceThreshold": number,
   "voiceSettings": { 
      "voiceId": "string"
   }
}
```

## URI Request Parameters<a name="API_CreateBotLocale_RequestParameters"></a>

The request uses the following URI parameters\.

 ** [botId](#API_CreateBotLocale_RequestSyntax) **   <a name="lexv2-CreateBotLocale-request-botId"></a>
The identifier of the bot to create the locale for\.  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$`   
Required: Yes

 ** [botVersion](#API_CreateBotLocale_RequestSyntax) **   <a name="lexv2-CreateBotLocale-request-botVersion"></a>
The version of the bot to create the locale for\. This can only be the draft version of the bot\.  
Length Constraints: Fixed length of 5\.  
Pattern: `^DRAFT$`   
Required: Yes

## Request Body<a name="API_CreateBotLocale_RequestBody"></a>

The request accepts the following data in JSON format\.

 ** [description](#API_CreateBotLocale_RequestSyntax) **   <a name="lexv2-CreateBotLocale-request-description"></a>
A description of the bot locale\. Use this to help identify the bot locale in lists\.  
Type: String  
Length Constraints: Minimum length of 0\. Maximum length of 200\.  
Required: No

 ** [localeId](#API_CreateBotLocale_RequestSyntax) **   <a name="lexv2-CreateBotLocale-request-localeId"></a>
The identifier of the language and locale that the bot will be used in\. The string must match one of the supported locales\. All of the intents, slot types, and slots used in the bot must have the same locale\. For more information, see [https://docs.aws.amazon.com/lex/latest/dg/supported-locales.html](https://docs.aws.amazon.com/lex/latest/dg/supported-locales.html)\.  
Type: String  
Required: Yes

 ** [nluIntentConfidenceThreshold](#API_CreateBotLocale_RequestSyntax) **   <a name="lexv2-CreateBotLocale-request-nluIntentConfidenceThreshold"></a>
Determines the threshold where Amazon Lex will insert the `AMAZON.FallbackIntent`, `AMAZON.KendraSearchIntent`, or both when returning alternative intents\. `AMAZON.FallbackIntent` and `AMAZON.KendraSearchIntent` are only inserted if they are configured for the bot\.  
For example, suppose a bot is configured with the confidence threshold of 0\.80 and the `AMAZON.FallbackIntent`\. Amazon Lex returns three alternative intents with the following confidence scores: IntentA \(0\.70\), IntentB \(0\.60\), IntentC \(0\.50\)\. The response from the PostText operation would be:  
+ AMAZON\.FallbackIntent
+ IntentA
+ IntentB
+ IntentC
Type: Double  
Valid Range: Minimum value of 0\. Maximum value of 1\.  
Required: Yes

 ** [voiceSettings](#API_CreateBotLocale_RequestSyntax) **   <a name="lexv2-CreateBotLocale-request-voiceSettings"></a>
The Amazon Polly voice ID that Amazon Lex uses for voice interaction with the user\.  
Type: [VoiceSettings](API_VoiceSettings.md) object  
Required: No

## Response Syntax<a name="API_CreateBotLocale_ResponseSyntax"></a>

```
HTTP/1.1 202
Content-type: application/json

{
   "botId": "string",
   "botLocaleStatus": "string",
   "botVersion": "string",
   "creationDateTime": number,
   "description": "string",
   "localeId": "string",
   "localeName": "string",
   "nluIntentConfidenceThreshold": number,
   "voiceSettings": { 
      "voiceId": "string"
   }
}
```

## Response Elements<a name="API_CreateBotLocale_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 202 response\.

The following data is returned in JSON format by the service\.

 ** [botId](#API_CreateBotLocale_ResponseSyntax) **   <a name="lexv2-CreateBotLocale-response-botId"></a>
The specified bot identifier\.  
Type: String  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$` 

 ** [botLocaleStatus](#API_CreateBotLocale_ResponseSyntax) **   <a name="lexv2-CreateBotLocale-response-botLocaleStatus"></a>
The status of the bot\.  
When the status is `Creating` the bot locale is being configured\. When the status is `Building` Amazon Lex is building the bot for testing and use\.  
If the status of the bot is `ReadyExpressTesting`, you can test the bot using the exact utterances specified in the bots' intents\. When the bot is ready for full testing or to run, the status is `Built`\.  
If there was a problem with building the bot, the status is `Failed`\. If the bot was saved but not built, the status is `NotBuilt`\.  
Type: String  
Valid Values:` Creating | Building | Built | ReadyExpressTesting | Failed | Deleting | NotBuilt` 

 ** [botVersion](#API_CreateBotLocale_ResponseSyntax) **   <a name="lexv2-CreateBotLocale-response-botVersion"></a>
The specified bot version\.  
Type: String  
Length Constraints: Fixed length of 5\.  
Pattern: `^DRAFT$` 

 ** [creationDateTime](#API_CreateBotLocale_ResponseSyntax) **   <a name="lexv2-CreateBotLocale-response-creationDateTime"></a>
A timestamp specifying the date and time that the bot locale was created\.  
Type: Timestamp

 ** [description](#API_CreateBotLocale_ResponseSyntax) **   <a name="lexv2-CreateBotLocale-response-description"></a>
The specified description of the bot locale\.  
Type: String  
Length Constraints: Minimum length of 0\. Maximum length of 200\.

 ** [localeId](#API_CreateBotLocale_ResponseSyntax) **   <a name="lexv2-CreateBotLocale-response-localeId"></a>
The specified locale identifier\.  
Type: String

 ** [localeName](#API_CreateBotLocale_ResponseSyntax) **   <a name="lexv2-CreateBotLocale-response-localeName"></a>
The specified locale name\.  
Type: String

 ** [nluIntentConfidenceThreshold](#API_CreateBotLocale_ResponseSyntax) **   <a name="lexv2-CreateBotLocale-response-nluIntentConfidenceThreshold"></a>
The specified confidence threshold for inserting the `AMAZON.FallbackIntent` and `AMAZON.KendraSearchIntent` intents\.  
Type: Double  
Valid Range: Minimum value of 0\. Maximum value of 1\.

 ** [voiceSettings](#API_CreateBotLocale_ResponseSyntax) **   <a name="lexv2-CreateBotLocale-response-voiceSettings"></a>
The Amazon Polly voice ID that Amazon Lex uses for voice interaction with the user\.  
Type: [VoiceSettings](API_VoiceSettings.md) object

## Errors<a name="API_CreateBotLocale_Errors"></a>

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

## See Also<a name="API_CreateBotLocale_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [AWS Command Line Interface](https://docs.aws.amazon.com/goto/aws-cli/models.lex.v2-2020-08-07/CreateBotLocale) 
+  [AWS SDK for \.NET](https://docs.aws.amazon.com/goto/DotNetSDKV3/models.lex.v2-2020-08-07/CreateBotLocale) 
+  [AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/models.lex.v2-2020-08-07/CreateBotLocale) 
+  [AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/models.lex.v2-2020-08-07/CreateBotLocale) 
+  [AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/models.lex.v2-2020-08-07/CreateBotLocale) 
+  [AWS SDK for JavaScript](https://docs.aws.amazon.com/goto/AWSJavaScriptSDK/models.lex.v2-2020-08-07/CreateBotLocale) 
+  [AWS SDK for PHP V3](https://docs.aws.amazon.com/goto/SdkForPHPV3/models.lex.v2-2020-08-07/CreateBotLocale) 
+  [AWS SDK for Python](https://docs.aws.amazon.com/goto/boto3/models.lex.v2-2020-08-07/CreateBotLocale) 
+  [AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/models.lex.v2-2020-08-07/CreateBotLocale) 