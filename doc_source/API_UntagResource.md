# UntagResource<a name="API_UntagResource"></a>

Removes tags from a bot, bot alias, or bot channel\.

## Request Syntax<a name="API_UntagResource_RequestSyntax"></a>

```
DELETE /tags/resourceARN?tagKeys=tagKeys HTTP/1.1
```

## URI Request Parameters<a name="API_UntagResource_RequestParameters"></a>

The request uses the following URI parameters\.

 ** [resourceARN](#API_UntagResource_RequestSyntax) **   <a name="lexv2-UntagResource-request-resourceARN"></a>
The Amazon Resource Name \(ARN\) of the resource to remove the tags from\.  
Length Constraints: Minimum length of 1\. Maximum length of 1011\.  
Required: Yes

 ** [tagKeys](#API_UntagResource_RequestSyntax) **   <a name="lexv2-UntagResource-request-tagKeys"></a>
A list of tag keys to remove from the resource\. If a tag key does not exist on the resource, it is ignored\.  
Array Members: Minimum number of 0 items\. Maximum number of 200 items\.  
Length Constraints: Minimum length of 1\. Maximum length of 128\.  
Required: Yes

## Request Body<a name="API_UntagResource_RequestBody"></a>

The request does not have a request body\.

## Response Syntax<a name="API_UntagResource_ResponseSyntax"></a>

```
HTTP/1.1 200
```

## Response Elements<a name="API_UntagResource_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 200 response with an empty HTTP body\.

## Errors<a name="API_UntagResource_Errors"></a>

For information about the errors that are common to all actions, see [Common Errors](CommonErrors.md)\.

 **InternalServerException**   
  
HTTP Status Code: 500

 **ResourceNotFoundException**   
  
HTTP Status Code: 404

 **ThrottlingException**   
  
HTTP Status Code: 429

 **ValidationException**   
  
HTTP Status Code: 400

## See Also<a name="API_UntagResource_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [ AWS Command Line Interface](https://docs.aws.amazon.com/goto/aws-cli/models.lex.v2-2020-08-07/UntagResource) 
+  [ AWS SDK for \.NET](https://docs.aws.amazon.com/goto/DotNetSDKV3/models.lex.v2-2020-08-07/UntagResource) 
+  [ AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/models.lex.v2-2020-08-07/UntagResource) 
+  [ AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/models.lex.v2-2020-08-07/UntagResource) 
+  [ AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/models.lex.v2-2020-08-07/UntagResource) 
+  [ AWS SDK for JavaScript](https://docs.aws.amazon.com/goto/AWSJavaScriptSDK/models.lex.v2-2020-08-07/UntagResource) 
+  [ AWS SDK for PHP V3](https://docs.aws.amazon.com/goto/SdkForPHPV3/models.lex.v2-2020-08-07/UntagResource) 
+  [ AWS SDK for Python](https://docs.aws.amazon.com/goto/boto3/models.lex.v2-2020-08-07/UntagResource) 
+  [ AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/models.lex.v2-2020-08-07/UntagResource) 