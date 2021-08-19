# DescribeBot<a name="API_DescribeBot"></a>

Provides metadata information about a bot\. 

## Request Syntax<a name="API_DescribeBot_RequestSyntax"></a>

```
GET /bots/botId/ HTTP/1.1
```

## URI Request Parameters<a name="API_DescribeBot_RequestParameters"></a>

The request uses the following URI parameters\.

 ** [botId](#API_DescribeBot_RequestSyntax) **   <a name="lexv2-DescribeBot-request-botId"></a>
The unique identifier of the bot to describe\.  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$`   
Required: Yes

## Request Body<a name="API_DescribeBot_RequestBody"></a>

The request does not have a request body\.

## Response Syntax<a name="API_DescribeBot_ResponseSyntax"></a>

```
HTTP/1.1 200
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

## Response Elements<a name="API_DescribeBot_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 200 response\.

The following data is returned in JSON format by the service\.

 ** [botId](#API_DescribeBot_ResponseSyntax) **   <a name="lexv2-DescribeBot-response-botId"></a>
The unique identifier of the bot\.  
Type: String  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$` 

 ** [botName](#API_DescribeBot_ResponseSyntax) **   <a name="lexv2-DescribeBot-response-botName"></a>
The name of the bot\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 100\.  
Pattern: `^([0-9a-zA-Z][_-]?)+$` 

 ** [botStatus](#API_DescribeBot_ResponseSyntax) **   <a name="lexv2-DescribeBot-response-botStatus"></a>
The current status of the bot\. When the status is `Available` the bot is ready to be used in conversations with users\.  
Type: String  
Valid Values:` Creating | Available | Inactive | Deleting | Failed | Versioning | Importing` 

 ** [creationDateTime](#API_DescribeBot_ResponseSyntax) **   <a name="lexv2-DescribeBot-response-creationDateTime"></a>
A timestamp of the date and time that the bot was created\.  
Type: Timestamp

 ** [dataPrivacy](#API_DescribeBot_ResponseSyntax) **   <a name="lexv2-DescribeBot-response-dataPrivacy"></a>
Settings for managing data privacy of the bot and its conversations with users\.  
Type: [DataPrivacy](API_DataPrivacy.md) object

 ** [description](#API_DescribeBot_ResponseSyntax) **   <a name="lexv2-DescribeBot-response-description"></a>
The description of the bot\.   
Type: String  
Length Constraints: Minimum length of 0\. Maximum length of 200\.

 ** [idleSessionTTLInSeconds](#API_DescribeBot_ResponseSyntax) **   <a name="lexv2-DescribeBot-response-idleSessionTTLInSeconds"></a>
The maximum time in seconds that Amazon Lex retains the data gathered in a conversation\.  
Type: Integer  
Valid Range: Minimum value of 60\. Maximum value of 86400\.

 ** [lastUpdatedDateTime](#API_DescribeBot_ResponseSyntax) **   <a name="lexv2-DescribeBot-response-lastUpdatedDateTime"></a>
A timestamp of the date and time that the bot was last updated\.  
Type: Timestamp

 ** [roleArn](#API_DescribeBot_ResponseSyntax) **   <a name="lexv2-DescribeBot-response-roleArn"></a>
The Amazon Resource Name \(ARN\) of an IAM role that has permission to access the bot\.  
Type: String  
Length Constraints: Minimum length of 32\. Maximum length of 2048\.  
Pattern: `^arn:aws:iam::[0-9]{12}:role/.*$` 

## Errors<a name="API_DescribeBot_Errors"></a>

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

## See Also<a name="API_DescribeBot_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [ AWS Command Line Interface](https://docs.aws.amazon.com/goto/aws-cli/models.lex.v2-2020-08-07/DescribeBot) 
+  [ AWS SDK for \.NET](https://docs.aws.amazon.com/goto/DotNetSDKV3/models.lex.v2-2020-08-07/DescribeBot) 
+  [ AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/models.lex.v2-2020-08-07/DescribeBot) 
+  [ AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/models.lex.v2-2020-08-07/DescribeBot) 
+  [ AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/models.lex.v2-2020-08-07/DescribeBot) 
+  [ AWS SDK for JavaScript](https://docs.aws.amazon.com/goto/AWSJavaScriptSDK/models.lex.v2-2020-08-07/DescribeBot) 
+  [ AWS SDK for PHP V3](https://docs.aws.amazon.com/goto/SdkForPHPV3/models.lex.v2-2020-08-07/DescribeBot) 
+  [ AWS SDK for Python](https://docs.aws.amazon.com/goto/boto3/models.lex.v2-2020-08-07/DescribeBot) 
+  [ AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/models.lex.v2-2020-08-07/DescribeBot) 