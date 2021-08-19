# StartImport<a name="API_StartImport"></a>

Starts importing a bot or bot locale from a zip archive that you uploaded to an S3 bucket\.

## Request Syntax<a name="API_StartImport_RequestSyntax"></a>

```
PUT /imports/ HTTP/1.1
Content-type: application/json

{
   "filePassword": "string",
   "importId": "string",
   "mergeStrategy": "string",
   "resourceSpecification": { 
      "botImportSpecification": { 
         "botName": "string",
         "botTags": { 
            "string" : "string" 
         },
         "dataPrivacy": { 
            "childDirected": boolean
         },
         "idleSessionTTLInSeconds": number,
         "roleArn": "string",
         "testBotAliasTags": { 
            "string" : "string" 
         }
      },
      "botLocaleImportSpecification": { 
         "botId": "string",
         "botVersion": "string",
         "localeId": "string",
         "nluIntentConfidenceThreshold": number,
         "voiceSettings": { 
            "voiceId": "string"
         }
      }
   }
}
```

## URI Request Parameters<a name="API_StartImport_RequestParameters"></a>

The request does not use any URI parameters\.

## Request Body<a name="API_StartImport_RequestBody"></a>

The request accepts the following data in JSON format\.

 ** [filePassword](#API_StartImport_RequestSyntax) **   <a name="lexv2-StartImport-request-filePassword"></a>
The password used to encrypt the zip archive that contains the bot or bot locale definition\. You should always encrypt the zip archive to protect it during transit between your site and Amazon Lex\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 1024\.  
Required: No

 ** [importId](#API_StartImport_RequestSyntax) **   <a name="lexv2-StartImport-request-importId"></a>
The unique identifier for the import\. It is included in the response from the [CreateUploadUrl](API_CreateUploadUrl.md) operation\.  
Type: String  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$`   
Required: Yes

 ** [mergeStrategy](#API_StartImport_RequestSyntax) **   <a name="lexv2-StartImport-request-mergeStrategy"></a>
The strategy to use when there is a name conflict between the imported resource and an existing resource\. When the merge strategy is `FailOnConflict` existing resources are not overwritten and the import fails\.  
Type: String  
Valid Values:` Overwrite | FailOnConflict`   
Required: Yes

 ** [resourceSpecification](#API_StartImport_RequestSyntax) **   <a name="lexv2-StartImport-request-resourceSpecification"></a>
Parameters for creating the bot or bot locale\.  
Type: [ImportResourceSpecification](API_ImportResourceSpecification.md) object  
Required: Yes

## Response Syntax<a name="API_StartImport_ResponseSyntax"></a>

```
HTTP/1.1 202
Content-type: application/json

{
   "creationDateTime": number,
   "importId": "string",
   "importStatus": "string",
   "mergeStrategy": "string",
   "resourceSpecification": { 
      "botImportSpecification": { 
         "botName": "string",
         "botTags": { 
            "string" : "string" 
         },
         "dataPrivacy": { 
            "childDirected": boolean
         },
         "idleSessionTTLInSeconds": number,
         "roleArn": "string",
         "testBotAliasTags": { 
            "string" : "string" 
         }
      },
      "botLocaleImportSpecification": { 
         "botId": "string",
         "botVersion": "string",
         "localeId": "string",
         "nluIntentConfidenceThreshold": number,
         "voiceSettings": { 
            "voiceId": "string"
         }
      }
   }
}
```

## Response Elements<a name="API_StartImport_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 202 response\.

The following data is returned in JSON format by the service\.

 ** [creationDateTime](#API_StartImport_ResponseSyntax) **   <a name="lexv2-StartImport-response-creationDateTime"></a>
The date and time that the import request was created\.  
Type: Timestamp

 ** [importId](#API_StartImport_ResponseSyntax) **   <a name="lexv2-StartImport-response-importId"></a>
A unique identifier for the import\.  
Type: String  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$` 

 ** [importStatus](#API_StartImport_ResponseSyntax) **   <a name="lexv2-StartImport-response-importStatus"></a>
The current status of the import\. When the status is `Complete` the bot or bot alias is ready to use\.  
Type: String  
Valid Values:` InProgress | Completed | Failed | Deleting` 

 ** [mergeStrategy](#API_StartImport_ResponseSyntax) **   <a name="lexv2-StartImport-response-mergeStrategy"></a>
The strategy used when there was a name conflict between the imported resource and an existing resource\. When the merge strategy is `FailOnConflict` existing resources are not overwritten and the import fails\.  
Type: String  
Valid Values:` Overwrite | FailOnConflict` 

 ** [resourceSpecification](#API_StartImport_ResponseSyntax) **   <a name="lexv2-StartImport-response-resourceSpecification"></a>
The parameters used when importing the bot or bot locale\.  
Type: [ImportResourceSpecification](API_ImportResourceSpecification.md) object

## Errors<a name="API_StartImport_Errors"></a>

For information about the errors that are common to all actions, see [Common Errors](CommonErrors.md)\.

 **ConflictException**   
  
HTTP Status Code: 409

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

## See Also<a name="API_StartImport_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [ AWS Command Line Interface](https://docs.aws.amazon.com/goto/aws-cli/models.lex.v2-2020-08-07/StartImport) 
+  [ AWS SDK for \.NET](https://docs.aws.amazon.com/goto/DotNetSDKV3/models.lex.v2-2020-08-07/StartImport) 
+  [ AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/models.lex.v2-2020-08-07/StartImport) 
+  [ AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/models.lex.v2-2020-08-07/StartImport) 
+  [ AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/models.lex.v2-2020-08-07/StartImport) 
+  [ AWS SDK for JavaScript](https://docs.aws.amazon.com/goto/AWSJavaScriptSDK/models.lex.v2-2020-08-07/StartImport) 
+  [ AWS SDK for PHP V3](https://docs.aws.amazon.com/goto/SdkForPHPV3/models.lex.v2-2020-08-07/StartImport) 
+  [ AWS SDK for Python](https://docs.aws.amazon.com/goto/boto3/models.lex.v2-2020-08-07/StartImport) 
+  [ AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/models.lex.v2-2020-08-07/StartImport) 