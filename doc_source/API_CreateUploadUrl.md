# CreateUploadUrl<a name="API_CreateUploadUrl"></a>

Gets a pre\-signed S3 write URL that you use to upload the zip archive when importing a bot or a bot locale\. 

## Request Syntax<a name="API_CreateUploadUrl_RequestSyntax"></a>

```
POST /createuploadurl/ HTTP/1.1
```

## URI Request Parameters<a name="API_CreateUploadUrl_RequestParameters"></a>

The request does not use any URI parameters\.

## Request Body<a name="API_CreateUploadUrl_RequestBody"></a>

The request does not have a request body\.

## Response Syntax<a name="API_CreateUploadUrl_ResponseSyntax"></a>

```
HTTP/1.1 200
Content-type: application/json

{
   "importId": "string",
   "uploadUrl": "string"
}
```

## Response Elements<a name="API_CreateUploadUrl_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 200 response\.

The following data is returned in JSON format by the service\.

 ** [importId](#API_CreateUploadUrl_ResponseSyntax) **   <a name="lexv2-CreateUploadUrl-response-importId"></a>
An identifier for a unique import job\. Use it when you call the [StartImport](API_StartImport.md) operation\.  
Type: String  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$` 

 ** [uploadUrl](#API_CreateUploadUrl_ResponseSyntax) **   <a name="lexv2-CreateUploadUrl-response-uploadUrl"></a>
A pre\-signed S3 write URL\. Upload the zip archive file that contains the definition of your bot or bot locale\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 1024\.

## Errors<a name="API_CreateUploadUrl_Errors"></a>

For information about the errors that are common to all actions, see [Common Errors](CommonErrors.md)\.

 **ConflictException**   
  
HTTP Status Code: 409

 **InternalServerException**   
  
HTTP Status Code: 500

 **ResourceNotFoundException**   
  
HTTP Status Code: 404

 **ThrottlingException**   
  
HTTP Status Code: 429

 **ValidationException**   
  
HTTP Status Code: 400

## See Also<a name="API_CreateUploadUrl_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [ AWS Command Line Interface](https://docs.aws.amazon.com/goto/aws-cli/models.lex.v2-2020-08-07/CreateUploadUrl) 
+  [ AWS SDK for \.NET](https://docs.aws.amazon.com/goto/DotNetSDKV3/models.lex.v2-2020-08-07/CreateUploadUrl) 
+  [ AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/models.lex.v2-2020-08-07/CreateUploadUrl) 
+  [ AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/models.lex.v2-2020-08-07/CreateUploadUrl) 
+  [ AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/models.lex.v2-2020-08-07/CreateUploadUrl) 
+  [ AWS SDK for JavaScript](https://docs.aws.amazon.com/goto/AWSJavaScriptSDK/models.lex.v2-2020-08-07/CreateUploadUrl) 
+  [ AWS SDK for PHP V3](https://docs.aws.amazon.com/goto/SdkForPHPV3/models.lex.v2-2020-08-07/CreateUploadUrl) 
+  [ AWS SDK for Python](https://docs.aws.amazon.com/goto/boto3/models.lex.v2-2020-08-07/CreateUploadUrl) 
+  [ AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/models.lex.v2-2020-08-07/CreateUploadUrl) 