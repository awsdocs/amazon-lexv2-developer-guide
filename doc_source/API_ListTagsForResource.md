# ListTagsForResource<a name="API_ListTagsForResource"></a>

Gets a list of tags associated with a resource\. Only bots, bot aliases, and bot channels can have tags associated with them\.

## Request Syntax<a name="API_ListTagsForResource_RequestSyntax"></a>

```
GET /tags/resourceARN HTTP/1.1
```

## URI Request Parameters<a name="API_ListTagsForResource_RequestParameters"></a>

The request uses the following URI parameters\.

 ** [resourceARN](#API_ListTagsForResource_RequestSyntax) **   <a name="lexv2-ListTagsForResource-request-resourceARN"></a>
The Amazon Resource Name \(ARN\) of the resource to get a list of tags for\.  
Length Constraints: Minimum length of 1\. Maximum length of 1011\.  
Required: Yes

## Request Body<a name="API_ListTagsForResource_RequestBody"></a>

The request does not have a request body\.

## Response Syntax<a name="API_ListTagsForResource_ResponseSyntax"></a>

```
HTTP/1.1 200
Content-type: application/json

{
   "tags": { 
      "string" : "string" 
   }
}
```

## Response Elements<a name="API_ListTagsForResource_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 200 response\.

The following data is returned in JSON format by the service\.

 ** [tags](#API_ListTagsForResource_ResponseSyntax) **   <a name="lexv2-ListTagsForResource-response-tags"></a>
The tags associated with a resource\.  
Type: String to string map  
Map Entries: Minimum number of 0 items\. Maximum number of 200 items\.  
Key Length Constraints: Minimum length of 1\. Maximum length of 128\.  
Value Length Constraints: Minimum length of 0\. Maximum length of 256\.

## Errors<a name="API_ListTagsForResource_Errors"></a>

For information about the errors that are common to all actions, see [Common Errors](CommonErrors.md)\.

 **InternalServerException**   
  
HTTP Status Code: 500

 **ResourceNotFoundException**   
  
HTTP Status Code: 404

 **ThrottlingException**   
  
HTTP Status Code: 429

 **ValidationException**   
  
HTTP Status Code: 400

## See Also<a name="API_ListTagsForResource_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [ AWS Command Line Interface](https://docs.aws.amazon.com/goto/aws-cli/models.lex.v2-2020-08-07/ListTagsForResource) 
+  [ AWS SDK for \.NET](https://docs.aws.amazon.com/goto/DotNetSDKV3/models.lex.v2-2020-08-07/ListTagsForResource) 
+  [ AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/models.lex.v2-2020-08-07/ListTagsForResource) 
+  [ AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/models.lex.v2-2020-08-07/ListTagsForResource) 
+  [ AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/models.lex.v2-2020-08-07/ListTagsForResource) 
+  [ AWS SDK for JavaScript](https://docs.aws.amazon.com/goto/AWSJavaScriptSDK/models.lex.v2-2020-08-07/ListTagsForResource) 
+  [ AWS SDK for PHP V3](https://docs.aws.amazon.com/goto/SdkForPHPV3/models.lex.v2-2020-08-07/ListTagsForResource) 
+  [ AWS SDK for Python](https://docs.aws.amazon.com/goto/boto3/models.lex.v2-2020-08-07/ListTagsForResource) 
+  [ AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/models.lex.v2-2020-08-07/ListTagsForResource) 