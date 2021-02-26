# UpdateBot<a name="API_UpdateBot"></a>

Updates the configuration of an existing bot\. 

## Request Syntax<a name="API_UpdateBot_RequestSyntax"></a>

```
PUT /bots/botId/ HTTP/1.1
Content-type: application/json

{
   "botName": "string",
   "dataPrivacy": { 
      "childDirected": boolean
   },
   "description": "string",
   "idleSessionTTLInSeconds": number,
   "roleArn": "string"
}
```

## URI Request Parameters<a name="API_UpdateBot_RequestParameters"></a>

The request uses the following URI parameters\.

 ** [botId](#API_UpdateBot_RequestSyntax) **   <a name="lexv2-UpdateBot-request-botId"></a>
The unique identifier of the bot to update\. This identifier is returned by the [CreateBot](API_CreateBot.md) operation\.  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$`   
Required: Yes

## Request Body<a name="API_UpdateBot_RequestBody"></a>

The request accepts the following data in JSON format\.

 ** [botName](#API_UpdateBot_RequestSyntax) **   <a name="lexv2-UpdateBot-request-botName"></a>
The new name of the bot\. The name must be unique in the account that creates the bot\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 100\.  
Pattern: `^([0-9a-zA-Z][_-]?)+$`   
Required: Yes

 ** [dataPrivacy](#API_UpdateBot_RequestSyntax) **   <a name="lexv2-UpdateBot-request-dataPrivacy"></a>
Provides information on additional privacy protections Amazon Lex should use with the bot's data\.  
Type: [DataPrivacy](API_DataPrivacy.md) object  
Required: Yes

 ** [description](#API_UpdateBot_RequestSyntax) **   <a name="lexv2-UpdateBot-request-description"></a>
A description of the bot\.  
Type: String  
Length Constraints: Minimum length of 0\. Maximum length of 200\.  
Required: No

 ** [idleSessionTTLInSeconds](#API_UpdateBot_RequestSyntax) **   <a name="lexv2-UpdateBot-request-idleSessionTTLInSeconds"></a>
The time, in seconds, that Amazon Lex should keep information about a user's conversation with the bot\.  
A user interaction remains active for the amount of time specified\. If no conversation occurs during this time, the session expires and Amazon Lex deletes any data provided before the timeout\.  
You can specify between 60 \(1 minute\) and 86,400 \(24 hours\) seconds\.  
Type: Integer  
Valid Range: Minimum value of 60\. Maximum value of 86400\.  
Required: Yes

 ** [roleArn](#API_UpdateBot_RequestSyntax) **   <a name="lexv2-UpdateBot-request-roleArn"></a>
The Amazon Resource Name \(ARN\) of an IAM role that has permissions to access the bot\.  
Type: String  
Length Constraints: Minimum length of 32\. Maximum length of 2048\.  
Pattern: `^arn:aws:iam::[0-9]{12}:role/.*$`   
Required: Yes

## Response Syntax<a name="API_UpdateBot_ResponseSyntax"></a>

```
HTTP/1.1 202
Content-type: application/json

{
   "botId": "string",
   "botName": "string",
   "botStatus": "string",
   "creationDateTime": number,
   "dataPrivacy": { 
      "childDirected": boolean
   },
   "description": "string",
   "idleSessionTTLInSeconds": number,
   "lastUpdatedDateTime": number,
   "roleArn": "string"
}
```

## Response Elements<a name="API_UpdateBot_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 202 response\.

The following data is returned in JSON format by the service\.

 ** [botId](#API_UpdateBot_ResponseSyntax) **   <a name="lexv2-UpdateBot-response-botId"></a>
The unique identifier of the bot that was updated\.  
Type: String  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$` 

 ** [botName](#API_UpdateBot_ResponseSyntax) **   <a name="lexv2-UpdateBot-response-botName"></a>
The name of the bot after the update\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 100\.  
Pattern: `^([0-9a-zA-Z][_-]?)+$` 

 ** [botStatus](#API_UpdateBot_ResponseSyntax) **   <a name="lexv2-UpdateBot-response-botStatus"></a>
Shows the current status of the bot\. The bot is first in the `Creating` status\. Once the bot is read for use, it changes to the `Available` status\. After the bot is created, you can use the `DRAFT` version of the bot\.  
Type: String  
Valid Values:` Creating | Available | Inactive | Deleting | Failed | Versioning` 

 ** [creationDateTime](#API_UpdateBot_ResponseSyntax) **   <a name="lexv2-UpdateBot-response-creationDateTime"></a>
A timestamp of the date and time that the bot was created\.  
Type: Timestamp

 ** [dataPrivacy](#API_UpdateBot_ResponseSyntax) **   <a name="lexv2-UpdateBot-response-dataPrivacy"></a>
The data privacy settings for the bot after the update\.  
Type: [DataPrivacy](API_DataPrivacy.md) object

 ** [description](#API_UpdateBot_ResponseSyntax) **   <a name="lexv2-UpdateBot-response-description"></a>
The description of the bot after the update\.  
Type: String  
Length Constraints: Minimum length of 0\. Maximum length of 200\.

 ** [idleSessionTTLInSeconds](#API_UpdateBot_ResponseSyntax) **   <a name="lexv2-UpdateBot-response-idleSessionTTLInSeconds"></a>
The session timeout, in seconds, for the bot after the update\.  
Type: Integer  
Valid Range: Minimum value of 60\. Maximum value of 86400\.

 ** [lastUpdatedDateTime](#API_UpdateBot_ResponseSyntax) **   <a name="lexv2-UpdateBot-response-lastUpdatedDateTime"></a>
A timestamp of the date and time that the bot was last updated\.  
Type: Timestamp

 ** [roleArn](#API_UpdateBot_ResponseSyntax) **   <a name="lexv2-UpdateBot-response-roleArn"></a>
The Amazon Resource Name \(ARN\) of the IAM role used by the bot after the update\.  
Type: String  
Length Constraints: Minimum length of 32\. Maximum length of 2048\.  
Pattern: `^arn:aws:iam::[0-9]{12}:role/.*$` 

## Errors<a name="API_UpdateBot_Errors"></a>

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

## See Also<a name="API_UpdateBot_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [AWS Command Line Interface](https://docs.aws.amazon.com/goto/aws-cli/models.lex.v2-2020-08-07/UpdateBot) 
+  [AWS SDK for \.NET](https://docs.aws.amazon.com/goto/DotNetSDKV3/models.lex.v2-2020-08-07/UpdateBot) 
+  [AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/models.lex.v2-2020-08-07/UpdateBot) 
+  [AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/models.lex.v2-2020-08-07/UpdateBot) 
+  [AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/models.lex.v2-2020-08-07/UpdateBot) 
+  [AWS SDK for JavaScript](https://docs.aws.amazon.com/goto/AWSJavaScriptSDK/models.lex.v2-2020-08-07/UpdateBot) 
+  [AWS SDK for PHP V3](https://docs.aws.amazon.com/goto/SdkForPHPV3/models.lex.v2-2020-08-07/UpdateBot) 
+  [AWS SDK for Python](https://docs.aws.amazon.com/goto/boto3/models.lex.v2-2020-08-07/UpdateBot) 
+  [AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/models.lex.v2-2020-08-07/UpdateBot) 