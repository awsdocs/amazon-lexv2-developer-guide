# CreateResourcePolicy<a name="API_CreateResourcePolicy"></a>

Creates a new resource policy with the specified policy statements\.

## Request Syntax<a name="API_CreateResourcePolicy_RequestSyntax"></a>

```
POST /policy/resourceArn/ HTTP/1.1
Content-type: application/json

{
   "policy": "string"
}
```

## URI Request Parameters<a name="API_CreateResourcePolicy_RequestParameters"></a>

The request uses the following URI parameters\.

 ** [resourceArn](#API_CreateResourcePolicy_RequestSyntax) **   <a name="lexv2-CreateResourcePolicy-request-resourceArn"></a>
The Amazon Resource Name \(ARN\) of the bot or bot alias that the resource policy is attached to\.  
Length Constraints: Minimum length of 1\. Maximum length of 1011\.  
Required: Yes

## Request Body<a name="API_CreateResourcePolicy_RequestBody"></a>

The request accepts the following data in JSON format\.

 ** [policy](#API_CreateResourcePolicy_RequestSyntax) **   <a name="lexv2-CreateResourcePolicy-request-policy"></a>
A resource policy to add to the resource\. The policy is a JSON structure that contains one or more statements that define the policy\. The policy must follow the IAM syntax\. For more information about the contents of a JSON policy document, see [ IAM JSON policy reference ](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies.html)\.   
If the policy isn't valid, Amazon Lex returns a validation exception\.  
Type: String  
Length Constraints: Minimum length of 2\.  
Required: Yes

## Response Syntax<a name="API_CreateResourcePolicy_ResponseSyntax"></a>

```
HTTP/1.1 200
Content-type: application/json

{
   "resourceArn": "string",
   "revisionId": "string"
}
```

## Response Elements<a name="API_CreateResourcePolicy_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 200 response\.

The following data is returned in JSON format by the service\.

 ** [resourceArn](#API_CreateResourcePolicy_ResponseSyntax) **   <a name="lexv2-CreateResourcePolicy-response-resourceArn"></a>
The Amazon Resource Name \(ARN\) of the bot or bot alias that the resource policy was attached to\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 1011\.

 ** [revisionId](#API_CreateResourcePolicy_ResponseSyntax) **   <a name="lexv2-CreateResourcePolicy-response-revisionId"></a>
The current revision of the resource policy\. Use the revision ID to make sure that you are updating the most current version of a resource policy when you add a policy statement to a resource, delete a resource, or update a resource\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 5\.  
Pattern: `^[0-9]+$` 

## Errors<a name="API_CreateResourcePolicy_Errors"></a>

For information about the errors that are common to all actions, see [Common Errors](CommonErrors.md)\.

 **InternalServerException**   
  
HTTP Status Code: 500

 **PreconditionFailedException**   
  
HTTP Status Code: 412

 **ResourceNotFoundException**   
  
HTTP Status Code: 404

 **ServiceQuotaExceededException**   
  
HTTP Status Code: 402

 **ThrottlingException**   
  
HTTP Status Code: 429

 **ValidationException**   
  
HTTP Status Code: 400

## See Also<a name="API_CreateResourcePolicy_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [ AWS Command Line Interface](https://docs.aws.amazon.com/goto/aws-cli/models.lex.v2-2020-08-07/CreateResourcePolicy) 
+  [ AWS SDK for \.NET](https://docs.aws.amazon.com/goto/DotNetSDKV3/models.lex.v2-2020-08-07/CreateResourcePolicy) 
+  [ AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/models.lex.v2-2020-08-07/CreateResourcePolicy) 
+  [ AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/models.lex.v2-2020-08-07/CreateResourcePolicy) 
+  [ AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/models.lex.v2-2020-08-07/CreateResourcePolicy) 
+  [ AWS SDK for JavaScript](https://docs.aws.amazon.com/goto/AWSJavaScriptSDK/models.lex.v2-2020-08-07/CreateResourcePolicy) 
+  [ AWS SDK for PHP V3](https://docs.aws.amazon.com/goto/SdkForPHPV3/models.lex.v2-2020-08-07/CreateResourcePolicy) 
+  [ AWS SDK for Python](https://docs.aws.amazon.com/goto/boto3/models.lex.v2-2020-08-07/CreateResourcePolicy) 
+  [ AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/models.lex.v2-2020-08-07/CreateResourcePolicy) 