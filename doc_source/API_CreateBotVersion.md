# CreateBotVersion<a name="API_CreateBotVersion"></a>

Creates a new version of the bot based on the `DRAFT` version\. If the `DRAFT` version of this resource hasn't changed since you created the last version, Amazon Lex doesn't create a new version, it returns the last created version\.

When you create the first version of a bot, Amazon Lex sets the version to 1\. Subsequent versions increment by 1\.

## Request Syntax<a name="API_CreateBotVersion_RequestSyntax"></a>

```
PUT /bots/botId/botversions/ HTTP/1.1
Content-type: application/json

{
   "botVersionLocaleSpecification": { 
      "string" : { 
         "sourceBotVersion": "string"
      }
   },
   "description": "string"
}
```

## URI Request Parameters<a name="API_CreateBotVersion_RequestParameters"></a>

The request uses the following URI parameters\.

 ** [botId](#API_CreateBotVersion_RequestSyntax) **   <a name="lexv2-CreateBotVersion-request-botId"></a>
The identifier of the bot to create the version for\.  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$`   
Required: Yes

## Request Body<a name="API_CreateBotVersion_RequestBody"></a>

The request accepts the following data in JSON format\.

 ** [botVersionLocaleSpecification](#API_CreateBotVersion_RequestSyntax) **   <a name="lexv2-CreateBotVersion-request-botVersionLocaleSpecification"></a>
Specifies the locales that Amazon Lex adds to this version\. You can choose the `Draft` version or any other previously published version for each locale\. When you specify a source version, the locale data is copied from the source version to the new version\.  
Type: String to [BotVersionLocaleDetails](API_BotVersionLocaleDetails.md) object map  
Map Entries: Maximum number of items\.  
Required: Yes

 ** [description](#API_CreateBotVersion_RequestSyntax) **   <a name="lexv2-CreateBotVersion-request-description"></a>
A description of the version\. Use the description to help identify the version in lists\.  
Type: String  
Length Constraints: Minimum length of 0\. Maximum length of 200\.  
Required: No

## Response Syntax<a name="API_CreateBotVersion_ResponseSyntax"></a>

```
HTTP/1.1 202
Content-type: application/json

{
   "botId": "string",
   "botStatus": "string",
   "botVersion": "string",
   "botVersionLocaleSpecification": { 
      "string" : { 
         "sourceBotVersion": "string"
      }
   },
   "creationDateTime": number,
   "description": "string"
}
```

## Response Elements<a name="API_CreateBotVersion_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 202 response\.

The following data is returned in JSON format by the service\.

 ** [botId](#API_CreateBotVersion_ResponseSyntax) **   <a name="lexv2-CreateBotVersion-response-botId"></a>
The bot identifier specified in the request\.  
Type: String  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$` 

 ** [botStatus](#API_CreateBotVersion_ResponseSyntax) **   <a name="lexv2-CreateBotVersion-response-botStatus"></a>
When you send a request to create or update a bot, Amazon Lex sets the status response element to `Creating`\. After Amazon Lex builds the bot, it sets status to `Available`\. If Amazon Lex can't build the bot, it sets status to `Failed`\.  
Type: String  
Valid Values:` Creating | Available | Inactive | Deleting | Failed | Versioning | Importing` 

 ** [botVersion](#API_CreateBotVersion_ResponseSyntax) **   <a name="lexv2-CreateBotVersion-response-botVersion"></a>
The version number assigned to the version\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 5\.  
Pattern: `^[0-9]+$` 

 ** [botVersionLocaleSpecification](#API_CreateBotVersion_ResponseSyntax) **   <a name="lexv2-CreateBotVersion-response-botVersionLocaleSpecification"></a>
The source versions used for each locale in the new version\.  
Type: String to [BotVersionLocaleDetails](API_BotVersionLocaleDetails.md) object map  
Map Entries: Maximum number of items\.

 ** [creationDateTime](#API_CreateBotVersion_ResponseSyntax) **   <a name="lexv2-CreateBotVersion-response-creationDateTime"></a>
A timestamp of the date and time that the version was created\.  
Type: Timestamp

 ** [description](#API_CreateBotVersion_ResponseSyntax) **   <a name="lexv2-CreateBotVersion-response-description"></a>
The description of the version specified in the request\.  
Type: String  
Length Constraints: Minimum length of 0\. Maximum length of 200\.

## Errors<a name="API_CreateBotVersion_Errors"></a>

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

## See Also<a name="API_CreateBotVersion_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [ AWS Command Line Interface](https://docs.aws.amazon.com/goto/aws-cli/models.lex.v2-2020-08-07/CreateBotVersion) 
+  [ AWS SDK for \.NET](https://docs.aws.amazon.com/goto/DotNetSDKV3/models.lex.v2-2020-08-07/CreateBotVersion) 
+  [ AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/models.lex.v2-2020-08-07/CreateBotVersion) 
+  [ AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/models.lex.v2-2020-08-07/CreateBotVersion) 
+  [ AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/models.lex.v2-2020-08-07/CreateBotVersion) 
+  [ AWS SDK for JavaScript](https://docs.aws.amazon.com/goto/AWSJavaScriptSDK/models.lex.v2-2020-08-07/CreateBotVersion) 
+  [ AWS SDK for PHP V3](https://docs.aws.amazon.com/goto/SdkForPHPV3/models.lex.v2-2020-08-07/CreateBotVersion) 
+  [ AWS SDK for Python](https://docs.aws.amazon.com/goto/boto3/models.lex.v2-2020-08-07/CreateBotVersion) 
+  [ AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/models.lex.v2-2020-08-07/CreateBotVersion) 