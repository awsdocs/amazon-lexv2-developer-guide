# DescribeBotLocale<a name="API_DescribeBotLocale"></a>

Describes the settings that a bot has for a specific locale\. 

## Request Syntax<a name="API_DescribeBotLocale_RequestSyntax"></a>

```
GET /bots/botId/botversions/botVersion/botlocales/localeId/ HTTP/1.1
```

## URI Request Parameters<a name="API_DescribeBotLocale_RequestParameters"></a>

The request uses the following URI parameters\.

 ** [botId](#API_DescribeBotLocale_RequestSyntax) **   <a name="lexv2-DescribeBotLocale-request-botId"></a>
The identifier of the bot associated with the locale\.  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$`   
Required: Yes

 ** [botVersion](#API_DescribeBotLocale_RequestSyntax) **   <a name="lexv2-DescribeBotLocale-request-botVersion"></a>
The identifier of the version of the bot associated with the locale\.  
Length Constraints: Minimum length of 1\. Maximum length of 5\.  
Pattern: `^(DRAFT|[0-9]+)$`   
Required: Yes

 ** [localeId](#API_DescribeBotLocale_RequestSyntax) **   <a name="lexv2-DescribeBotLocale-request-localeId"></a>
The unique identifier of the locale to describe\. The string must match one of the supported locales\. For more information, see [https://docs.aws.amazon.com/lex/latest/dg/supported-locales.html](https://docs.aws.amazon.com/lex/latest/dg/supported-locales.html)\.   
Required: Yes

## Request Body<a name="API_DescribeBotLocale_RequestBody"></a>

The request does not have a request body\.

## Response Syntax<a name="API_DescribeBotLocale_ResponseSyntax"></a>

```
HTTP/1.1 200
Content-type: application/json

{
   "botId": "string",
   "botLocaleHistoryEvents": [ 
      { 
         "event": "string",
         "eventDate": number
      }
   ],
   "botLocaleStatus": "string",
   "botVersion": "string",
   "creationDateTime": number,
   "description": "string",
   "failureReasons": [ "string" ],
   "intentsCount": number,
   "lastBuildSubmittedDateTime": number,
   "lastUpdatedDateTime": number,
   "localeId": "string",
   "localeName": "string",
   "nluIntentConfidenceThreshold": number,
   "slotTypesCount": number,
   "voiceSettings": { 
      "voiceId": "string"
   }
}
```

## Response Elements<a name="API_DescribeBotLocale_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 200 response\.

The following data is returned in JSON format by the service\.

 ** [botId](#API_DescribeBotLocale_ResponseSyntax) **   <a name="lexv2-DescribeBotLocale-response-botId"></a>
The identifier of the bot associated with the locale\.  
Type: String  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$` 

 ** [botLocaleHistoryEvents](#API_DescribeBotLocale_ResponseSyntax) **   <a name="lexv2-DescribeBotLocale-response-botLocaleHistoryEvents"></a>
History of changes, such as when a locale is used in an alias, that have taken place for the locale\.  
Type: Array of [BotLocaleHistoryEvent](API_BotLocaleHistoryEvent.md) objects

 ** [botLocaleStatus](#API_DescribeBotLocale_ResponseSyntax) **   <a name="lexv2-DescribeBotLocale-response-botLocaleStatus"></a>
The status of the bot\. If the status is `Failed`, the reasons for the failure are listed in the `failureReasons` field\.  
Type: String  
Valid Values:` Creating | Building | Built | ReadyExpressTesting | Failed | Deleting | NotBuilt` 

 ** [botVersion](#API_DescribeBotLocale_ResponseSyntax) **   <a name="lexv2-DescribeBotLocale-response-botVersion"></a>
The identifier of the version of the bot associated with the locale\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 5\.  
Pattern: `^(DRAFT|[0-9]+)$` 

 ** [creationDateTime](#API_DescribeBotLocale_ResponseSyntax) **   <a name="lexv2-DescribeBotLocale-response-creationDateTime"></a>
The date and time that the locale was created\.  
Type: Timestamp

 ** [description](#API_DescribeBotLocale_ResponseSyntax) **   <a name="lexv2-DescribeBotLocale-response-description"></a>
The description of the locale\.  
Type: String  
Length Constraints: Minimum length of 0\. Maximum length of 200\.

 ** [failureReasons](#API_DescribeBotLocale_ResponseSyntax) **   <a name="lexv2-DescribeBotLocale-response-failureReasons"></a>
if `botLocaleStatus` is `Failed`, Amazon Lex explains why it failed to build the bot\.  
Type: Array of strings

 ** [intentsCount](#API_DescribeBotLocale_ResponseSyntax) **   <a name="lexv2-DescribeBotLocale-response-intentsCount"></a>
The number of intents defined for the locale\.  
Type: Integer

 ** [lastBuildSubmittedDateTime](#API_DescribeBotLocale_ResponseSyntax) **   <a name="lexv2-DescribeBotLocale-response-lastBuildSubmittedDateTime"></a>
The date and time that the locale was last submitted for building\.  
Type: Timestamp

 ** [lastUpdatedDateTime](#API_DescribeBotLocale_ResponseSyntax) **   <a name="lexv2-DescribeBotLocale-response-lastUpdatedDateTime"></a>
The date and time that the locale was last updated\.  
Type: Timestamp

 ** [localeId](#API_DescribeBotLocale_ResponseSyntax) **   <a name="lexv2-DescribeBotLocale-response-localeId"></a>
The unique identifier of the described locale\.  
Type: String

 ** [localeName](#API_DescribeBotLocale_ResponseSyntax) **   <a name="lexv2-DescribeBotLocale-response-localeName"></a>
The name of the locale\.  
Type: String

 ** [nluIntentConfidenceThreshold](#API_DescribeBotLocale_ResponseSyntax) **   <a name="lexv2-DescribeBotLocale-response-nluIntentConfidenceThreshold"></a>
The confidence threshold where Amazon Lex inserts the `AMAZON.FallbackIntent` and `AMAZON.KendraSearchIntent` intents in the list of possible intents for an utterance\.  
Type: Double  
Valid Range: Minimum value of 0\. Maximum value of 1\.

 ** [slotTypesCount](#API_DescribeBotLocale_ResponseSyntax) **   <a name="lexv2-DescribeBotLocale-response-slotTypesCount"></a>
The number of slot types defined for the locale\.  
Type: Integer

 ** [voiceSettings](#API_DescribeBotLocale_ResponseSyntax) **   <a name="lexv2-DescribeBotLocale-response-voiceSettings"></a>
The Amazon Polly voice Amazon Lex uses for voice interaction with the user\.  
Type: [VoiceSettings](API_VoiceSettings.md) object

## Errors<a name="API_DescribeBotLocale_Errors"></a>

For information about the errors that are common to all actions, see [Common Errors](CommonErrors.md)\.

 **InternalServerException**   
  
HTTP Status Code: 500

 **ResourceNotFoundException**   
  
HTTP Status Code: 404

 **ServiceQuotaExceededException**   
  
HTTP Status Code: 402

 **ThrottlingException**   
  
HTTP Status Code: 429

 **ValidationException**   
  
HTTP Status Code: 400

## See Also<a name="API_DescribeBotLocale_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [AWS Command Line Interface](https://docs.aws.amazon.com/goto/aws-cli/models.lex.v2-2020-08-07/DescribeBotLocale) 
+  [AWS SDK for \.NET](https://docs.aws.amazon.com/goto/DotNetSDKV3/models.lex.v2-2020-08-07/DescribeBotLocale) 
+  [AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/models.lex.v2-2020-08-07/DescribeBotLocale) 
+  [AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/models.lex.v2-2020-08-07/DescribeBotLocale) 
+  [AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/models.lex.v2-2020-08-07/DescribeBotLocale) 
+  [AWS SDK for JavaScript](https://docs.aws.amazon.com/goto/AWSJavaScriptSDK/models.lex.v2-2020-08-07/DescribeBotLocale) 
+  [AWS SDK for PHP V3](https://docs.aws.amazon.com/goto/SdkForPHPV3/models.lex.v2-2020-08-07/DescribeBotLocale) 
+  [AWS SDK for Python](https://docs.aws.amazon.com/goto/boto3/models.lex.v2-2020-08-07/DescribeBotLocale) 
+  [AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/models.lex.v2-2020-08-07/DescribeBotLocale) 