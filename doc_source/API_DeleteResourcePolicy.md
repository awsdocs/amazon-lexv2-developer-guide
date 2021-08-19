# DeleteResourcePolicy<a name="API_DeleteResourcePolicy"></a>

Removes an existing policy from a bot or bot alias\. If the resource doesn't have a policy attached, Amazon Lex returns an exception\.

## Request Syntax<a name="API_DeleteResourcePolicy_RequestSyntax"></a>

```
DELETE /policy/resourceArn/?expectedRevisionId=expectedRevisionId HTTP/1.1
```

## URI Request Parameters<a name="API_DeleteResourcePolicy_RequestParameters"></a>

The request uses the following URI parameters\.

 ** [expectedRevisionId](#API_DeleteResourcePolicy_RequestSyntax) **   <a name="lexv2-DeleteResourcePolicy-request-expectedRevisionId"></a>
The identifier of the revision to edit\. If this ID doesn't match the current revision number, Amazon Lex returns an exception  
If you don't specify a revision ID, Amazon Lex will delete the current policy\.  
Length Constraints: Minimum length of 1\. Maximum length of 5\.  
Pattern: `^[0-9]+$` 

 ** [resourceArn](#API_DeleteResourcePolicy_RequestSyntax) **   <a name="lexv2-DeleteResourcePolicy-request-resourceArn"></a>
The Amazon Resource Name \(ARN\) of the bot or bot alias that has the resource policy attached\.  
Length Constraints: Minimum length of 1\. Maximum length of 1011\.  
Required: Yes

## Request Body<a name="API_DeleteResourcePolicy_RequestBody"></a>

The request does not have a request body\.

## Response Syntax<a name="API_DeleteResourcePolicy_ResponseSyntax"></a>

```
HTTP/1.1 204
Content-type: application/json

{
   "resourceArn": "string",
   "revisionId": "string"
}
```

## Response Elements<a name="API_DeleteResourcePolicy_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 204 response\.

The following data is returned in JSON format by the service\.

 ** [resourceArn](#API_DeleteResourcePolicy_ResponseSyntax) **   <a name="lexv2-DeleteResourcePolicy-response-resourceArn"></a>
The Amazon Resource Name \(ARN\) of the bot or bot alias that the resource policy was deleted from\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 1011\.

 ** [revisionId](#API_DeleteResourcePolicy_ResponseSyntax) **   <a name="lexv2-DeleteResourcePolicy-response-revisionId"></a>
The current revision of the resource policy\. Use the revision ID to make sure that you are updating the most current version of a resource policy when you add a policy statement to a resource, delete a resource, or update a resource\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 5\.  
Pattern: `^[0-9]+$` 

## Errors<a name="API_DeleteResourcePolicy_Errors"></a>

For information about the errors that are common to all actions, see [Common Errors](CommonErrors.md)\.

 **InternalServerException**   
  
HTTP Status Code: 500

 **PreconditionFailedException**   
  
HTTP Status Code: 412

 **ResourceNotFoundException**   
  
HTTP Status Code: 404

 **ThrottlingException**   
  
HTTP Status Code: 429

## See Also<a name="API_DeleteResourcePolicy_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [ AWS Command Line Interface](https://docs.aws.amazon.com/goto/aws-cli/models.lex.v2-2020-08-07/DeleteResourcePolicy) 
+  [ AWS SDK for \.NET](https://docs.aws.amazon.com/goto/DotNetSDKV3/models.lex.v2-2020-08-07/DeleteResourcePolicy) 
+  [ AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/models.lex.v2-2020-08-07/DeleteResourcePolicy) 
+  [ AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/models.lex.v2-2020-08-07/DeleteResourcePolicy) 
+  [ AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/models.lex.v2-2020-08-07/DeleteResourcePolicy) 
+  [ AWS SDK for JavaScript](https://docs.aws.amazon.com/goto/AWSJavaScriptSDK/models.lex.v2-2020-08-07/DeleteResourcePolicy) 
+  [ AWS SDK for PHP V3](https://docs.aws.amazon.com/goto/SdkForPHPV3/models.lex.v2-2020-08-07/DeleteResourcePolicy) 
+  [ AWS SDK for Python](https://docs.aws.amazon.com/goto/boto3/models.lex.v2-2020-08-07/DeleteResourcePolicy) 
+  [ AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/models.lex.v2-2020-08-07/DeleteResourcePolicy) 