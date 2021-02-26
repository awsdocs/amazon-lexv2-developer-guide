# CreateBot<a name="API_CreateBot"></a>

Creates an Amazon Lex conversational bot\. 

## Request Syntax<a name="API_CreateBot_RequestSyntax"></a>

```
PUT /bots/ HTTP/1.1
Content-type: application/json

{
   "botName": "string",
   "botTags": { 
      "string" : "string" 
   },
   "dataPrivacy": { 
      "childDirected": boolean
   },
   "description": "string",
   "idleSessionTTLInSeconds": number,
   "roleArn": "string",
   "testBotAliasTags": { 
      "string" : "string" 
   }
}
```

## URI Request Parameters<a name="API_CreateBot_RequestParameters"></a>

The request does not use any URI parameters\.

## Request Body<a name="API_CreateBot_RequestBody"></a>

The request accepts the following data in JSON format\.

 ** [botName](#API_CreateBot_RequestSyntax) **   <a name="lexv2-CreateBot-request-botName"></a>
The name of the bot\. The bot name must be unique in the account that creates the bot\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 100\.  
Pattern: `^([0-9a-zA-Z][_-]?)+$`   
Required: Yes

 ** [botTags](#API_CreateBot_RequestSyntax) **   <a name="lexv2-CreateBot-request-botTags"></a>
A list of tags to add to the bot\. You can only add tags when you create a bot\. You can't use the `UpdateBot` operation to update tags\. To update tags, use the `TagResource` operation\.  
Type: String to string map  
Map Entries: Minimum number of 0 items\. Maximum number of 200 items\.  
Key Length Constraints: Minimum length of 1\. Maximum length of 128\.  
Value Length Constraints: Minimum length of 0\. Maximum length of 256\.  
Required: No

 ** [dataPrivacy](#API_CreateBot_RequestSyntax) **   <a name="lexv2-CreateBot-request-dataPrivacy"></a>
Provides information on additional privacy protections Amazon Lex should use with the bot's data\.  
Type: [DataPrivacy](API_DataPrivacy.md) object  
Required: Yes

 ** [description](#API_CreateBot_RequestSyntax) **   <a name="lexv2-CreateBot-request-description"></a>
A description of the bot\. It appears in lists to help you identify a particular bot\.  
Type: String  
Length Constraints: Minimum length of 0\. Maximum length of 200\.  
Required: No

 ** [idleSessionTTLInSeconds](#API_CreateBot_RequestSyntax) **   <a name="lexv2-CreateBot-request-idleSessionTTLInSeconds"></a>
The time, in seconds, that Amazon Lex should keep information about a user's conversation with the bot\.   
A user interaction remains active for the amount of time specified\. If no conversation occurs during this time, the session expires and Amazon Lex deletes any data provided before the timeout\.  
You can specify between 60 \(1 minute\) and 86,400 \(24 hours\) seconds\.  
Type: Integer  
Valid Range: Minimum value of 60\. Maximum value of 86400\.  
Required: Yes

 ** [roleArn](#API_CreateBot_RequestSyntax) **   <a name="lexv2-CreateBot-request-roleArn"></a>
The Amazon Resource Name \(ARN\) of an IAM role that has permission to access the bot\.  
Type: String  
Length Constraints: Minimum length of 32\. Maximum length of 2048\.  
Pattern: `^arn:aws:iam::[0-9]{12}:role/.*$`   
Required: Yes

 ** [testBotAliasTags](#API_CreateBot_RequestSyntax) **   <a name="lexv2-CreateBot-request-testBotAliasTags"></a>
A list of tags to add to the test alias for a bot\. You can only add tags when you create a bot\. You can't use the `UpdateAlias` operation to update tags\. To update tags on the test alias, use the `TagResource` operation\.  
Type: String to string map  
Map Entries: Minimum number of 0 items\. Maximum number of 200 items\.  
Key Length Constraints: Minimum length of 1\. Maximum length of 128\.  
Value Length Constraints: Minimum length of 0\. Maximum length of 256\.  
Required: No

## Response Syntax<a name="API_CreateBot_ResponseSyntax"></a>

```
HTTP/1.1 202
Content-type: application/json

{
   "botId": "string",
   "botName": "string",
   "botStatus": "string",
   "botTags": { 
      "string" : "string" 
   },
   "creationDateTime": number,
   "dataPrivacy": { 
      "childDirected": boolean
   },
   "description": "string",
   "idleSessionTTLInSeconds": number,
   "roleArn": "string",
   "testBotAliasTags": { 
      "string" : "string" 
   }
}
```

## Response Elements<a name="API_CreateBot_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 202 response\.

The following data is returned in JSON format by the service\.

 ** [botId](#API_CreateBot_ResponseSyntax) **   <a name="lexv2-CreateBot-response-botId"></a>
A unique identifier for a particular bot\. You use this to identify the bot when you call other Amazon Lex API operations\.  
Type: String  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$` 

 ** [botName](#API_CreateBot_ResponseSyntax) **   <a name="lexv2-CreateBot-response-botName"></a>
The name specified for the bot\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 100\.  
Pattern: `^([0-9a-zA-Z][_-]?)+$` 

 ** [botStatus](#API_CreateBot_ResponseSyntax) **   <a name="lexv2-CreateBot-response-botStatus"></a>
Shows the current status of the bot\. The bot is first in the `Creating` status\. Once the bot is read for use, it changes to the `Available` status\. After the bot is created, you can use the `Draft` version of the bot\.  
Type: String  
Valid Values:` Creating | Available | Inactive | Deleting | Failed | Versioning` 

 ** [botTags](#API_CreateBot_ResponseSyntax) **   <a name="lexv2-CreateBot-response-botTags"></a>
A list of tags associated with the bot\.  
Type: String to string map  
Map Entries: Minimum number of 0 items\. Maximum number of 200 items\.  
Key Length Constraints: Minimum length of 1\. Maximum length of 128\.  
Value Length Constraints: Minimum length of 0\. Maximum length of 256\.

 ** [creationDateTime](#API_CreateBot_ResponseSyntax) **   <a name="lexv2-CreateBot-response-creationDateTime"></a>
A timestamp indicating the date and time that the bot was created\.  
Type: Timestamp

 ** [dataPrivacy](#API_CreateBot_ResponseSyntax) **   <a name="lexv2-CreateBot-response-dataPrivacy"></a>
The data privacy settings specified for the bot\.  
Type: [DataPrivacy](API_DataPrivacy.md) object

 ** [description](#API_CreateBot_ResponseSyntax) **   <a name="lexv2-CreateBot-response-description"></a>
The description specified for the bot\.  
Type: String  
Length Constraints: Minimum length of 0\. Maximum length of 200\.

 ** [idleSessionTTLInSeconds](#API_CreateBot_ResponseSyntax) **   <a name="lexv2-CreateBot-response-idleSessionTTLInSeconds"></a>
The session idle time specified for the bot\.  
Type: Integer  
Valid Range: Minimum value of 60\. Maximum value of 86400\.

 ** [roleArn](#API_CreateBot_ResponseSyntax) **   <a name="lexv2-CreateBot-response-roleArn"></a>
The IAM role specified for the bot\.  
Type: String  
Length Constraints: Minimum length of 32\. Maximum length of 2048\.  
Pattern: `^arn:aws:iam::[0-9]{12}:role/.*$` 

 ** [testBotAliasTags](#API_CreateBot_ResponseSyntax) **   <a name="lexv2-CreateBot-response-testBotAliasTags"></a>
A list of tags associated with the test alias for the bot\.  
Type: String to string map  
Map Entries: Minimum number of 0 items\. Maximum number of 200 items\.  
Key Length Constraints: Minimum length of 1\. Maximum length of 128\.  
Value Length Constraints: Minimum length of 0\. Maximum length of 256\.

## Errors<a name="API_CreateBot_Errors"></a>

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

## See Also<a name="API_CreateBot_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [AWS Command Line Interface](https://docs.aws.amazon.com/goto/aws-cli/models.lex.v2-2020-08-07/CreateBot) 
+  [AWS SDK for \.NET](https://docs.aws.amazon.com/goto/DotNetSDKV3/models.lex.v2-2020-08-07/CreateBot) 
+  [AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/models.lex.v2-2020-08-07/CreateBot) 
+  [AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/models.lex.v2-2020-08-07/CreateBot) 
+  [AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/models.lex.v2-2020-08-07/CreateBot) 
+  [AWS SDK for JavaScript](https://docs.aws.amazon.com/goto/AWSJavaScriptSDK/models.lex.v2-2020-08-07/CreateBot) 
+  [AWS SDK for PHP V3](https://docs.aws.amazon.com/goto/SdkForPHPV3/models.lex.v2-2020-08-07/CreateBot) 
+  [AWS SDK for Python](https://docs.aws.amazon.com/goto/boto3/models.lex.v2-2020-08-07/CreateBot) 
+  [AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/models.lex.v2-2020-08-07/CreateBot) 