# DescribeBotVersion<a name="API_DescribeBotVersion"></a>

Provides metadata about a version of a bot\.

## Request Syntax<a name="API_DescribeBotVersion_RequestSyntax"></a>

```
GET /bots/botId/botversions/botVersion/ HTTP/1.1
```

## URI Request Parameters<a name="API_DescribeBotVersion_RequestParameters"></a>

The request uses the following URI parameters\.

 ** [botId](#API_DescribeBotVersion_RequestSyntax) **   <a name="lexv2-DescribeBotVersion-request-botId"></a>
The identifier of the bot containing the version to return metadata for\.  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$`   
Required: Yes

 ** [botVersion](#API_DescribeBotVersion_RequestSyntax) **   <a name="lexv2-DescribeBotVersion-request-botVersion"></a>
The version of the bot to return metadata for\.  
Length Constraints: Minimum length of 1\. Maximum length of 5\.  
Pattern: `^[0-9]+$`   
Required: Yes

## Request Body<a name="API_DescribeBotVersion_RequestBody"></a>

The request does not have a request body\.

## Response Syntax<a name="API_DescribeBotVersion_ResponseSyntax"></a>

```
HTTP/1.1 200
Content-type: application/json

{
   "botId": "string",
   "botName": "string",
   "botStatus": "string",
   "botVersion": "string",
   "creationDateTime": number,
   "dataPrivacy": { 
      "childDirected": boolean
   },
   "description": "string",
   "failureReasons": [ "string" ],
   "idleSessionTTLInSeconds": number,
   "roleArn": "string"
}
```

## Response Elements<a name="API_DescribeBotVersion_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 200 response\.

The following data is returned in JSON format by the service\.

 ** [botId](#API_DescribeBotVersion_ResponseSyntax) **   <a name="lexv2-DescribeBotVersion-response-botId"></a>
The identifier of the bot that contains the version\.  
Type: String  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$` 

 ** [botName](#API_DescribeBotVersion_ResponseSyntax) **   <a name="lexv2-DescribeBotVersion-response-botName"></a>
The name of the bot that contains the version\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 100\.  
Pattern: `^([0-9a-zA-Z][_-]?)+$` 

 ** [botStatus](#API_DescribeBotVersion_ResponseSyntax) **   <a name="lexv2-DescribeBotVersion-response-botStatus"></a>
The current status of the bot\. When the status is `Available`, the bot version is ready for use\.  
Type: String  
Valid Values:` Creating | Available | Inactive | Deleting | Failed | Versioning | Importing` 

 ** [botVersion](#API_DescribeBotVersion_ResponseSyntax) **   <a name="lexv2-DescribeBotVersion-response-botVersion"></a>
The version of the bot to describe\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 5\.  
Pattern: `^[0-9]+$` 

 ** [creationDateTime](#API_DescribeBotVersion_ResponseSyntax) **   <a name="lexv2-DescribeBotVersion-response-creationDateTime"></a>
A timestamp of the date and time that the bot version was created\.  
Type: Timestamp

 ** [dataPrivacy](#API_DescribeBotVersion_ResponseSyntax) **   <a name="lexv2-DescribeBotVersion-response-dataPrivacy"></a>
Data privacy settings for the bot version\.  
Type: [DataPrivacy](API_DataPrivacy.md) object

 ** [description](#API_DescribeBotVersion_ResponseSyntax) **   <a name="lexv2-DescribeBotVersion-response-description"></a>
The description specified for the bot\.  
Type: String  
Length Constraints: Minimum length of 0\. Maximum length of 200\.

 ** [failureReasons](#API_DescribeBotVersion_ResponseSyntax) **   <a name="lexv2-DescribeBotVersion-response-failureReasons"></a>
If the `botStatus` is `Failed`, this contains a list of reasons that the version couldn't be built\.  
Type: Array of strings

 ** [idleSessionTTLInSeconds](#API_DescribeBotVersion_ResponseSyntax) **   <a name="lexv2-DescribeBotVersion-response-idleSessionTTLInSeconds"></a>
The number of seconds that a session with the bot remains active before it is discarded by Amazon Lex\.  
Type: Integer  
Valid Range: Minimum value of 60\. Maximum value of 86400\.

 ** [roleArn](#API_DescribeBotVersion_ResponseSyntax) **   <a name="lexv2-DescribeBotVersion-response-roleArn"></a>
The Amazon Resource Name \(ARN\) of an IAM role that has permission to access the bot version\.  
Type: String  
Length Constraints: Minimum length of 32\. Maximum length of 2048\.  
Pattern: `^arn:aws:iam::[0-9]{12}:role/.*$` 

## Errors<a name="API_DescribeBotVersion_Errors"></a>

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

## See Also<a name="API_DescribeBotVersion_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [ AWS Command Line Interface](https://docs.aws.amazon.com/goto/aws-cli/models.lex.v2-2020-08-07/DescribeBotVersion) 
+  [ AWS SDK for \.NET](https://docs.aws.amazon.com/goto/DotNetSDKV3/models.lex.v2-2020-08-07/DescribeBotVersion) 
+  [ AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/models.lex.v2-2020-08-07/DescribeBotVersion) 
+  [ AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/models.lex.v2-2020-08-07/DescribeBotVersion) 
+  [ AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/models.lex.v2-2020-08-07/DescribeBotVersion) 
+  [ AWS SDK for JavaScript](https://docs.aws.amazon.com/goto/AWSJavaScriptSDK/models.lex.v2-2020-08-07/DescribeBotVersion) 
+  [ AWS SDK for PHP V3](https://docs.aws.amazon.com/goto/SdkForPHPV3/models.lex.v2-2020-08-07/DescribeBotVersion) 
+  [ AWS SDK for Python](https://docs.aws.amazon.com/goto/boto3/models.lex.v2-2020-08-07/DescribeBotVersion) 
+  [ AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/models.lex.v2-2020-08-07/DescribeBotVersion) 