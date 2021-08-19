# DeleteResourcePolicyStatement<a name="API_DeleteResourcePolicyStatement"></a>

Deletes a policy statement from a resource policy\. If you delete the last statement from a policy, the policy is deleted\. If you specify a statement ID that doesn't exist in the policy, or if the bot or bot alias doesn't have a policy attached, Amazon Lex returns an exception\.

## Request Syntax<a name="API_DeleteResourcePolicyStatement_RequestSyntax"></a>

```
DELETE /policy/resourceArn/statements/statementId/?expectedRevisionId=expectedRevisionId HTTP/1.1
```

## URI Request Parameters<a name="API_DeleteResourcePolicyStatement_RequestParameters"></a>

The request uses the following URI parameters\.

 ** [expectedRevisionId](#API_DeleteResourcePolicyStatement_RequestSyntax) **   <a name="lexv2-DeleteResourcePolicyStatement-request-expectedRevisionId"></a>
The identifier of the revision of the policy to delete the statement from\. If this revision ID doesn't match the current revision ID, Amazon Lex throws an exception\.  
If you don't specify a revision, Amazon Lex removes the current contents of the statement\.   
Length Constraints: Minimum length of 1\. Maximum length of 5\.  
Pattern: `^[0-9]+$` 

 ** [resourceArn](#API_DeleteResourcePolicyStatement_RequestSyntax) **   <a name="lexv2-DeleteResourcePolicyStatement-request-resourceArn"></a>
The Amazon Resource Name \(ARN\) of the bot or bot alias that the resource policy is attached to\.  
Length Constraints: Minimum length of 1\. Maximum length of 1011\.  
Required: Yes

 ** [statementId](#API_DeleteResourcePolicyStatement_RequestSyntax) **   <a name="lexv2-DeleteResourcePolicyStatement-request-statementId"></a>
The name of the statement \(SID\) to delete from the policy\.  
Length Constraints: Minimum length of 1\. Maximum length of 100\.  
Pattern: `^([0-9a-zA-Z][_-]?)+$`   
Required: Yes

## Request Body<a name="API_DeleteResourcePolicyStatement_RequestBody"></a>

The request does not have a request body\.

## Response Syntax<a name="API_DeleteResourcePolicyStatement_ResponseSyntax"></a>

```
HTTP/1.1 204
Content-type: application/json

{
   "resourceArn": "string",
   "revisionId": "string"
}
```

## Response Elements<a name="API_DeleteResourcePolicyStatement_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 204 response\.

The following data is returned in JSON format by the service\.

 ** [resourceArn](#API_DeleteResourcePolicyStatement_ResponseSyntax) **   <a name="lexv2-DeleteResourcePolicyStatement-response-resourceArn"></a>
The Amazon Resource Name \(ARN\) of the bot or bot alias that the resource policy statement was removed from\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 1011\.

 ** [revisionId](#API_DeleteResourcePolicyStatement_ResponseSyntax) **   <a name="lexv2-DeleteResourcePolicyStatement-response-revisionId"></a>
The current revision of the resource policy\. Use the revision ID to make sure that you are updating the most current version of a resource policy when you add a policy statement to a resource, delete a resource, or update a resource\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 5\.  
Pattern: `^[0-9]+$` 

## Errors<a name="API_DeleteResourcePolicyStatement_Errors"></a>

For information about the errors that are common to all actions, see [Common Errors](CommonErrors.md)\.

 **InternalServerException**   
  
HTTP Status Code: 500

 **PreconditionFailedException**   
  
HTTP Status Code: 412

 **ResourceNotFoundException**   
  
HTTP Status Code: 404

 **ThrottlingException**   
  
HTTP Status Code: 429

## See Also<a name="API_DeleteResourcePolicyStatement_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [ AWS Command Line Interface](https://docs.aws.amazon.com/goto/aws-cli/models.lex.v2-2020-08-07/DeleteResourcePolicyStatement) 
+  [ AWS SDK for \.NET](https://docs.aws.amazon.com/goto/DotNetSDKV3/models.lex.v2-2020-08-07/DeleteResourcePolicyStatement) 
+  [ AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/models.lex.v2-2020-08-07/DeleteResourcePolicyStatement) 
+  [ AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/models.lex.v2-2020-08-07/DeleteResourcePolicyStatement) 
+  [ AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/models.lex.v2-2020-08-07/DeleteResourcePolicyStatement) 
+  [ AWS SDK for JavaScript](https://docs.aws.amazon.com/goto/AWSJavaScriptSDK/models.lex.v2-2020-08-07/DeleteResourcePolicyStatement) 
+  [ AWS SDK for PHP V3](https://docs.aws.amazon.com/goto/SdkForPHPV3/models.lex.v2-2020-08-07/DeleteResourcePolicyStatement) 
+  [ AWS SDK for Python](https://docs.aws.amazon.com/goto/boto3/models.lex.v2-2020-08-07/DeleteResourcePolicyStatement) 
+  [ AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/models.lex.v2-2020-08-07/DeleteResourcePolicyStatement) 