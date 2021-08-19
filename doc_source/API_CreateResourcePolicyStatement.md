# CreateResourcePolicyStatement<a name="API_CreateResourcePolicyStatement"></a>

Adds a new resource policy statement to a bot or bot alias\. If a resource policy exists, the statement is added to the current resource policy\. If a policy doesn't exist, a new policy is created\.

You can't create a resource policy statement that allows cross\-account access\.

## Request Syntax<a name="API_CreateResourcePolicyStatement_RequestSyntax"></a>

```
POST /policy/resourceArn/statements/?expectedRevisionId=expectedRevisionId HTTP/1.1
Content-type: application/json

{
   "action": [ "string" ],
   "condition": { 
      "string" : { 
         "string" : "string" 
      }
   },
   "effect": "string",
   "principal": [ 
      { 
         "arn": "string",
         "service": "string"
      }
   ],
   "statementId": "string"
}
```

## URI Request Parameters<a name="API_CreateResourcePolicyStatement_RequestParameters"></a>

The request uses the following URI parameters\.

 ** [expectedRevisionId](#API_CreateResourcePolicyStatement_RequestSyntax) **   <a name="lexv2-CreateResourcePolicyStatement-request-expectedRevisionId"></a>
The identifier of the revision of the policy to edit\. If this revision ID doesn't match the current revision ID, Amazon Lex throws an exception\.  
If you don't specify a revision, Amazon Lex overwrites the contents of the policy with the new values\.  
Length Constraints: Minimum length of 1\. Maximum length of 5\.  
Pattern: `^[0-9]+$` 

 ** [resourceArn](#API_CreateResourcePolicyStatement_RequestSyntax) **   <a name="lexv2-CreateResourcePolicyStatement-request-resourceArn"></a>
The Amazon Resource Name \(ARN\) of the bot or bot alias that the resource policy is attached to\.  
Length Constraints: Minimum length of 1\. Maximum length of 1011\.  
Required: Yes

## Request Body<a name="API_CreateResourcePolicyStatement_RequestBody"></a>

The request accepts the following data in JSON format\.

 ** [action](#API_CreateResourcePolicyStatement_RequestSyntax) **   <a name="lexv2-CreateResourcePolicyStatement-request-action"></a>
The Amazon Lex action that this policy either allows or denies\. The action must apply to the resource type of the specified ARN\. For more information, see [ Actions, resources, and condition keys for Amazon Lex V2](https://docs.aws.amazon.com/service-authorization/latest/reference/list_amazonlexv2.html)\.  
Type: Array of strings  
Length Constraints: Minimum length of 5\. Maximum length of 50\.  
Pattern: `lex:[a-zA-Z*]+$`   
Required: Yes

 ** [condition](#API_CreateResourcePolicyStatement_RequestSyntax) **   <a name="lexv2-CreateResourcePolicyStatement-request-condition"></a>
Specifies a condition when the policy is in effect\. If the principal of the policy is a service principal, you must provide two condition blocks, one with a SourceAccount global condition key and one with a SourceArn global condition key\.  
For more information, see [IAM JSON policy elements: Condition ](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_elements_condition.html)\.  
Type: String to string to string map map  
Map Entries: Minimum number of 0 items\. Maximum number of 10 items\.  
Key Length Constraints: Minimum length of 1\.  
Map Entries: Minimum number of 0 items\. Maximum number of 10 items\.  
Key Length Constraints: Minimum length of 1\. Maximum length of 1024\.  
Value Length Constraints: Minimum length of 1\. Maximum length of 1024\.  
Required: No

 ** [effect](#API_CreateResourcePolicyStatement_RequestSyntax) **   <a name="lexv2-CreateResourcePolicyStatement-request-effect"></a>
Determines whether the statement allows or denies access to the resource\.  
Type: String  
Valid Values:` Allow | Deny`   
Required: Yes

 ** [principal](#API_CreateResourcePolicyStatement_RequestSyntax) **   <a name="lexv2-CreateResourcePolicyStatement-request-principal"></a>
An IAM principal, such as an IAM users, IAM roles, or AWS services that is allowed or denied access to a resource\. For more information, see [AWS JSON policy elements: Principal](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_elements_principal.html)\.  
Type: Array of [Principal](API_Principal.md) objects  
Required: Yes

 ** [statementId](#API_CreateResourcePolicyStatement_RequestSyntax) **   <a name="lexv2-CreateResourcePolicyStatement-request-statementId"></a>
The name of the statement\. The ID is the same as the `Sid` IAM property\. The statement name must be unique within the policy\. For more information, see [IAM JSON policy elements: Sid](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_elements_sid.html)\.   
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 100\.  
Pattern: `^([0-9a-zA-Z][_-]?)+$`   
Required: Yes

## Response Syntax<a name="API_CreateResourcePolicyStatement_ResponseSyntax"></a>

```
HTTP/1.1 200
Content-type: application/json

{
   "resourceArn": "string",
   "revisionId": "string"
}
```

## Response Elements<a name="API_CreateResourcePolicyStatement_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 200 response\.

The following data is returned in JSON format by the service\.

 ** [resourceArn](#API_CreateResourcePolicyStatement_ResponseSyntax) **   <a name="lexv2-CreateResourcePolicyStatement-response-resourceArn"></a>
The Amazon Resource Name \(ARN\) of the bot or bot alias that the resource policy is attached to\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 1011\.

 ** [revisionId](#API_CreateResourcePolicyStatement_ResponseSyntax) **   <a name="lexv2-CreateResourcePolicyStatement-response-revisionId"></a>
The current revision of the resource policy\. Use the revision ID to make sure that you are updating the most current version of a resource policy when you add a policy statement to a resource, delete a resource, or update a resource\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 5\.  
Pattern: `^[0-9]+$` 

## Errors<a name="API_CreateResourcePolicyStatement_Errors"></a>

For information about the errors that are common to all actions, see [Common Errors](CommonErrors.md)\.

 **ConflictException**   
  
HTTP Status Code: 409

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

## See Also<a name="API_CreateResourcePolicyStatement_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [ AWS Command Line Interface](https://docs.aws.amazon.com/goto/aws-cli/models.lex.v2-2020-08-07/CreateResourcePolicyStatement) 
+  [ AWS SDK for \.NET](https://docs.aws.amazon.com/goto/DotNetSDKV3/models.lex.v2-2020-08-07/CreateResourcePolicyStatement) 
+  [ AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/models.lex.v2-2020-08-07/CreateResourcePolicyStatement) 
+  [ AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/models.lex.v2-2020-08-07/CreateResourcePolicyStatement) 
+  [ AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/models.lex.v2-2020-08-07/CreateResourcePolicyStatement) 
+  [ AWS SDK for JavaScript](https://docs.aws.amazon.com/goto/AWSJavaScriptSDK/models.lex.v2-2020-08-07/CreateResourcePolicyStatement) 
+  [ AWS SDK for PHP V3](https://docs.aws.amazon.com/goto/SdkForPHPV3/models.lex.v2-2020-08-07/CreateResourcePolicyStatement) 
+  [ AWS SDK for Python](https://docs.aws.amazon.com/goto/boto3/models.lex.v2-2020-08-07/CreateResourcePolicyStatement) 
+  [ AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/models.lex.v2-2020-08-07/CreateResourcePolicyStatement) 