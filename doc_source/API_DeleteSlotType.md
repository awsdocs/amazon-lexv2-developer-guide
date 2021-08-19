# DeleteSlotType<a name="API_DeleteSlotType"></a>

Deletes a slot type from a bot locale\.

If a slot is using the slot type, Amazon Lex throws a `ResourceInUseException` exception\. To avoid the exception, set the `skipResourceInUseCheck` parameter to `true`\.

## Request Syntax<a name="API_DeleteSlotType_RequestSyntax"></a>

```
DELETE /bots/botId/botversions/botVersion/botlocales/localeId/slottypes/slotTypeId/?skipResourceInUseCheck=skipResourceInUseCheck HTTP/1.1
```

## URI Request Parameters<a name="API_DeleteSlotType_RequestParameters"></a>

The request uses the following URI parameters\.

 ** [botId](#API_DeleteSlotType_RequestSyntax) **   <a name="lexv2-DeleteSlotType-request-botId"></a>
The identifier of the bot associated with the slot type\.  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$`   
Required: Yes

 ** [botVersion](#API_DeleteSlotType_RequestSyntax) **   <a name="lexv2-DeleteSlotType-request-botVersion"></a>
The version of the bot associated with the slot type\.  
Length Constraints: Fixed length of 5\.  
Pattern: `^DRAFT$`   
Required: Yes

 ** [localeId](#API_DeleteSlotType_RequestSyntax) **   <a name="lexv2-DeleteSlotType-request-localeId"></a>
The identifier of the language and locale that the slot type will be deleted from\. The string must match one of the supported locales\. For more information, see [Supported languages](https://docs.aws.amazon.com/lexv2/latest/dg/how-languages.html)\.  
Required: Yes

 ** [skipResourceInUseCheck](#API_DeleteSlotType_RequestSyntax) **   <a name="lexv2-DeleteSlotType-request-skipResourceInUseCheck"></a>
By default, the `DeleteSlotType` operations throws a `ResourceInUseException` exception if you try to delete a slot type used by a slot\. Set the `skipResourceInUseCheck` parameter to `true` to skip this check and remove the slot type even if a slot uses it\.

 ** [slotTypeId](#API_DeleteSlotType_RequestSyntax) **   <a name="lexv2-DeleteSlotType-request-slotTypeId"></a>
The identifier of the slot type to delete\.  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$`   
Required: Yes

## Request Body<a name="API_DeleteSlotType_RequestBody"></a>

The request does not have a request body\.

## Response Syntax<a name="API_DeleteSlotType_ResponseSyntax"></a>

```
HTTP/1.1 204
```

## Response Elements<a name="API_DeleteSlotType_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 204 response with an empty HTTP body\.

## Errors<a name="API_DeleteSlotType_Errors"></a>

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

## See Also<a name="API_DeleteSlotType_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [ AWS Command Line Interface](https://docs.aws.amazon.com/goto/aws-cli/models.lex.v2-2020-08-07/DeleteSlotType) 
+  [ AWS SDK for \.NET](https://docs.aws.amazon.com/goto/DotNetSDKV3/models.lex.v2-2020-08-07/DeleteSlotType) 
+  [ AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/models.lex.v2-2020-08-07/DeleteSlotType) 
+  [ AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/models.lex.v2-2020-08-07/DeleteSlotType) 
+  [ AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/models.lex.v2-2020-08-07/DeleteSlotType) 
+  [ AWS SDK for JavaScript](https://docs.aws.amazon.com/goto/AWSJavaScriptSDK/models.lex.v2-2020-08-07/DeleteSlotType) 
+  [ AWS SDK for PHP V3](https://docs.aws.amazon.com/goto/SdkForPHPV3/models.lex.v2-2020-08-07/DeleteSlotType) 
+  [ AWS SDK for Python](https://docs.aws.amazon.com/goto/boto3/models.lex.v2-2020-08-07/DeleteSlotType) 
+  [ AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/models.lex.v2-2020-08-07/DeleteSlotType) 