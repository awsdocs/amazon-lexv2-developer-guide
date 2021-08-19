# ListExports<a name="API_ListExports"></a>

Lists the exports for a bot or bot locale\. Exports are kept in the list for 7 days\.

## Request Syntax<a name="API_ListExports_RequestSyntax"></a>

```
POST /exports/ HTTP/1.1
Content-type: application/json

{
   "botId": "string",
   "botVersion": "string",
   "filters": [ 
      { 
         "name": "string",
         "operator": "string",
         "values": [ "string" ]
      }
   ],
   "maxResults": number,
   "nextToken": "string",
   "sortBy": { 
      "attribute": "string",
      "order": "string"
   }
}
```

## URI Request Parameters<a name="API_ListExports_RequestParameters"></a>

The request does not use any URI parameters\.

## Request Body<a name="API_ListExports_RequestBody"></a>

The request accepts the following data in JSON format\.

 ** [botId](#API_ListExports_RequestSyntax) **   <a name="lexv2-ListExports-request-botId"></a>
The unique identifier that Amazon Lex assigned to the bot\.  
Type: String  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$`   
Required: No

 ** [botVersion](#API_ListExports_RequestSyntax) **   <a name="lexv2-ListExports-request-botVersion"></a>
The version of the bot to list exports for\.   
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 5\.  
Pattern: `^(DRAFT|[0-9]+)$`   
Required: No

 ** [filters](#API_ListExports_RequestSyntax) **   <a name="lexv2-ListExports-request-filters"></a>
Provides the specification of a filter used to limit the exports in the response to only those that match the filter specification\. You can only specify one filter and one string to filter on\.  
Type: Array of [ExportFilter](API_ExportFilter.md) objects  
Array Members: Fixed number of 1 item\.  
Required: No

 ** [maxResults](#API_ListExports_RequestSyntax) **   <a name="lexv2-ListExports-request-maxResults"></a>
The maximum number of exports to return in each page of results\. If there are fewer results than the max page size, only the actual number of results are returned\.  
Type: Integer  
Valid Range: Minimum value of 1\. Maximum value of 1000\.  
Required: No

 ** [nextToken](#API_ListExports_RequestSyntax) **   <a name="lexv2-ListExports-request-nextToken"></a>
If the response from the `ListExports` operation contans more results that specified in the `maxResults` parameter, a token is returned in the response\. Use that token in the `nextToken` parameter to return the next page of results\.  
Type: String  
Required: No

 ** [sortBy](#API_ListExports_RequestSyntax) **   <a name="lexv2-ListExports-request-sortBy"></a>
Determines the field that the list of exports is sorted by\. You can sort by the `LastUpdatedDateTime` field in ascending or descending order\.  
Type: [ExportSortBy](API_ExportSortBy.md) object  
Required: No

## Response Syntax<a name="API_ListExports_ResponseSyntax"></a>

```
HTTP/1.1 200
Content-type: application/json

{
   "botId": "string",
   "botVersion": "string",
   "exportSummaries": [ 
      { 
         "creationDateTime": number,
         "exportId": "string",
         "exportStatus": "string",
         "fileFormat": "string",
         "lastUpdatedDateTime": number,
         "resourceSpecification": { 
            "botExportSpecification": { 
               "botId": "string",
               "botVersion": "string"
            },
            "botLocaleExportSpecification": { 
               "botId": "string",
               "botVersion": "string",
               "localeId": "string"
            }
         }
      }
   ],
   "nextToken": "string"
}
```

## Response Elements<a name="API_ListExports_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 200 response\.

The following data is returned in JSON format by the service\.

 ** [botId](#API_ListExports_ResponseSyntax) **   <a name="lexv2-ListExports-response-botId"></a>
The unique identifier assigned to the bot by Amazon Lex\.  
Type: String  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$` 

 ** [botVersion](#API_ListExports_ResponseSyntax) **   <a name="lexv2-ListExports-response-botVersion"></a>
The version of the bot that was exported\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 5\.  
Pattern: `^(DRAFT|[0-9]+)$` 

 ** [exportSummaries](#API_ListExports_ResponseSyntax) **   <a name="lexv2-ListExports-response-exportSummaries"></a>
Summary information for the exports that meet the filter criteria specified in the request\. The length of the list is specified in the `maxResults` parameter\. If there are more exports available, the `nextToken` field contains a token to get the next page of results\.  
Type: Array of [ExportSummary](API_ExportSummary.md) objects

 ** [nextToken](#API_ListExports_ResponseSyntax) **   <a name="lexv2-ListExports-response-nextToken"></a>
A token that indicates whether there are more results to return in a response to the `ListExports` operation\. If the `nextToken` field is present, you send the contents as the `nextToken` parameter of a `ListExports` operation request to get the next page of results\.  
Type: String

## Errors<a name="API_ListExports_Errors"></a>

For information about the errors that are common to all actions, see [Common Errors](CommonErrors.md)\.

 **InternalServerException**   
  
HTTP Status Code: 500

 **ThrottlingException**   
  
HTTP Status Code: 429

 **ValidationException**   
  
HTTP Status Code: 400

## See Also<a name="API_ListExports_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [ AWS Command Line Interface](https://docs.aws.amazon.com/goto/aws-cli/models.lex.v2-2020-08-07/ListExports) 
+  [ AWS SDK for \.NET](https://docs.aws.amazon.com/goto/DotNetSDKV3/models.lex.v2-2020-08-07/ListExports) 
+  [ AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/models.lex.v2-2020-08-07/ListExports) 
+  [ AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/models.lex.v2-2020-08-07/ListExports) 
+  [ AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/models.lex.v2-2020-08-07/ListExports) 
+  [ AWS SDK for JavaScript](https://docs.aws.amazon.com/goto/AWSJavaScriptSDK/models.lex.v2-2020-08-07/ListExports) 
+  [ AWS SDK for PHP V3](https://docs.aws.amazon.com/goto/SdkForPHPV3/models.lex.v2-2020-08-07/ListExports) 
+  [ AWS SDK for Python](https://docs.aws.amazon.com/goto/boto3/models.lex.v2-2020-08-07/ListExports) 
+  [ AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/models.lex.v2-2020-08-07/ListExports) 