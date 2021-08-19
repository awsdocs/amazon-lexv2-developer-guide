# UpdateBotLocale<a name="API_UpdateBotLocale"></a>

Updates the settings that a bot has for a specific locale\.

## Request Syntax<a name="API_UpdateBotLocale_RequestSyntax"></a>

```
PUT /bots/botId/botversions/botVersion/botlocales/localeId/ HTTP/1.1
Content-type: application/json

{
   "description": "string",
   "nluIntentConfidenceThreshold": number,
   "voiceSettings": { 
      "voiceId": "string"
   }
}
```

## URI Request Parameters<a name="API_UpdateBotLocale_RequestParameters"></a>

The request uses the following URI parameters\.

 ** [botId](#API_UpdateBotLocale_RequestSyntax) **   <a name="lexv2-UpdateBotLocale-request-botId"></a>
The unique identifier of the bot that contains the locale\.  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$`   
Required: Yes

 ** [botVersion](#API_UpdateBotLocale_RequestSyntax) **   <a name="lexv2-UpdateBotLocale-request-botVersion"></a>
The version of the bot that contains the locale to be updated\. The version can only be the `DRAFT` version\.  
Length Constraints: Fixed length of 5\.  
Pattern: `^DRAFT$`   
Required: Yes

 ** [localeId](#API_UpdateBotLocale_RequestSyntax) **   <a name="lexv2-UpdateBotLocale-request-localeId"></a>
The identifier of the language and locale to update\. The string must match one of the supported locales\. For more information, see [Supported languages](https://docs.aws.amazon.com/lexv2/latest/dg/how-languages.html)\.  
Required: Yes

## Request Body<a name="API_UpdateBotLocale_RequestBody"></a>

The request accepts the following data in JSON format\.

 ** [description](#API_UpdateBotLocale_RequestSyntax) **   <a name="lexv2-UpdateBotLocale-request-description"></a>
The new description of the locale\.  
Type: String  
Length Constraints: Minimum length of 0\. Maximum length of 200\.  
Required: No

 ** [nluIntentConfidenceThreshold](#API_UpdateBotLocale_RequestSyntax) **   <a name="lexv2-UpdateBotLocale-request-nluIntentConfidenceThreshold"></a>
The new confidence threshold where Amazon Lex inserts the `AMAZON.FallbackIntent` and `AMAZON.KendraSearchIntent` intents in the list of possible intents for an utterance\.  
Type: Double  
Valid Range: Minimum value of 0\. Maximum value of 1\.  
Required: Yes

 ** [voiceSettings](#API_UpdateBotLocale_RequestSyntax) **   <a name="lexv2-UpdateBotLocale-request-voiceSettings"></a>
The new Amazon Polly voice Amazon Lex should use for voice interaction with the user\.  
Type: [VoiceSettings](API_VoiceSettings.md) object  
Required: No

## Response Syntax<a name="API_UpdateBotLocale_ResponseSyntax"></a>

```
HTTP/1.1 202
Content-type: application/json

{
   "botId": "string",
   "botLocaleStatus": "string",
   "botVersion": "string",
   "creationDateTime": number,
   "description": "string",
   "failureReasons": [ "string" ],
   "lastUpdatedDateTime": number,
   "localeId": "string",
   "localeName": "string",
   "nluIntentConfidenceThreshold": number,
   "voiceSettings": { 
      "voiceId": "string"
   }
}
```

## Response Elements<a name="API_UpdateBotLocale_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 202 response\.

The following data is returned in JSON format by the service\.

 ** [botId](#API_UpdateBotLocale_ResponseSyntax) **   <a name="lexv2-UpdateBotLocale-response-botId"></a>
The identifier of the bot that contains the updated locale\.  
Type: String  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$` 

 ** [botLocaleStatus](#API_UpdateBotLocale_ResponseSyntax) **   <a name="lexv2-UpdateBotLocale-response-botLocaleStatus"></a>
The current status of the locale\. When the bot status is `Built` the locale is ready for use\.  
Type: String  
Valid Values:` Creating | Building | Built | ReadyExpressTesting | Failed | Deleting | NotBuilt | Importing` 

 ** [botVersion](#API_UpdateBotLocale_ResponseSyntax) **   <a name="lexv2-UpdateBotLocale-response-botVersion"></a>
The version of the bot that contains the updated locale\.  
Type: String  
Length Constraints: Fixed length of 5\.  
Pattern: `^DRAFT$` 

 ** [creationDateTime](#API_UpdateBotLocale_ResponseSyntax) **   <a name="lexv2-UpdateBotLocale-response-creationDateTime"></a>
A timestamp of the date and time that the locale was created\.  
Type: Timestamp

 ** [description](#API_UpdateBotLocale_ResponseSyntax) **   <a name="lexv2-UpdateBotLocale-response-description"></a>
The updated description of the locale\.  
Type: String  
Length Constraints: Minimum length of 0\. Maximum length of 200\.

 ** [failureReasons](#API_UpdateBotLocale_ResponseSyntax) **   <a name="lexv2-UpdateBotLocale-response-failureReasons"></a>
If the `botLocaleStatus` is `Failed`, the `failureReasons` field lists the errors that occurred while building the bot\.  
Type: Array of strings

 ** [lastUpdatedDateTime](#API_UpdateBotLocale_ResponseSyntax) **   <a name="lexv2-UpdateBotLocale-response-lastUpdatedDateTime"></a>
A timestamp of the date and time that the locale was last updated\.  
Type: Timestamp

 ** [localeId](#API_UpdateBotLocale_ResponseSyntax) **   <a name="lexv2-UpdateBotLocale-response-localeId"></a>
The language and locale of the updated bot locale\.  
Type: String

 ** [localeName](#API_UpdateBotLocale_ResponseSyntax) **   <a name="lexv2-UpdateBotLocale-response-localeName"></a>
The updated locale name for the locale\.  
Type: String

 ** [nluIntentConfidenceThreshold](#API_UpdateBotLocale_ResponseSyntax) **   <a name="lexv2-UpdateBotLocale-response-nluIntentConfidenceThreshold"></a>
The updated confidence threshold for inserting the `AMAZON.FallbackIntent` and `AMAZON.KendraSearchIntent` intents in the list of possible intents for an utterance\.  
Type: Double  
Valid Range: Minimum value of 0\. Maximum value of 1\.

 ** [voiceSettings](#API_UpdateBotLocale_ResponseSyntax) **   <a name="lexv2-UpdateBotLocale-response-voiceSettings"></a>
The updated Amazon Polly voice to use for voice interaction with the user\.  
Type: [VoiceSettings](API_VoiceSettings.md) object

## Errors<a name="API_UpdateBotLocale_Errors"></a>

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

## See Also<a name="API_UpdateBotLocale_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [ AWS Command Line Interface](https://docs.aws.amazon.com/goto/aws-cli/models.lex.v2-2020-08-07/UpdateBotLocale) 
+  [ AWS SDK for \.NET](https://docs.aws.amazon.com/goto/DotNetSDKV3/models.lex.v2-2020-08-07/UpdateBotLocale) 
+  [ AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/models.lex.v2-2020-08-07/UpdateBotLocale) 
+  [ AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/models.lex.v2-2020-08-07/UpdateBotLocale) 
+  [ AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/models.lex.v2-2020-08-07/UpdateBotLocale) 
+  [ AWS SDK for JavaScript](https://docs.aws.amazon.com/goto/AWSJavaScriptSDK/models.lex.v2-2020-08-07/UpdateBotLocale) 
+  [ AWS SDK for PHP V3](https://docs.aws.amazon.com/goto/SdkForPHPV3/models.lex.v2-2020-08-07/UpdateBotLocale) 
+  [ AWS SDK for Python](https://docs.aws.amazon.com/goto/boto3/models.lex.v2-2020-08-07/UpdateBotLocale) 
+  [ AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/models.lex.v2-2020-08-07/UpdateBotLocale) 