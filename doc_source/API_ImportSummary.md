# ImportSummary<a name="API_ImportSummary"></a>

Provides summary information about an import in an import list\.

## Contents<a name="API_ImportSummary_Contents"></a>

 **creationDateTime**   <a name="lexv2-Type-ImportSummary-creationDateTime"></a>
The date and time that the import was created\.  
Type: Timestamp  
Required: No

 **importedResourceId**   <a name="lexv2-Type-ImportSummary-importedResourceId"></a>
The unique identifier that Amazon Lex assigned to the imported resource\.  
Type: String  
Length Constraints: Minimum length of 5\. Maximum length of 10\.  
Pattern: `^([0-9a-zA-Z_])+$`   
Required: No

 **importedResourceName**   <a name="lexv2-Type-ImportSummary-importedResourceName"></a>
The name that you gave the imported resource\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 100\.  
Pattern: `^([0-9a-zA-Z][_-]?)+$`   
Required: No

 **importId**   <a name="lexv2-Type-ImportSummary-importId"></a>
The unique identifier that Amazon Lex assigned to the import\.  
Type: String  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$`   
Required: No

 **importStatus**   <a name="lexv2-Type-ImportSummary-importStatus"></a>
The status of the resource\. When the status is `Completed` the resource is ready to build\.  
Type: String  
Valid Values:` InProgress | Completed | Failed | Deleting`   
Required: No

 **lastUpdatedDateTime**   <a name="lexv2-Type-ImportSummary-lastUpdatedDateTime"></a>
The date and time that the import was last updated\.  
Type: Timestamp  
Required: No

 **mergeStrategy**   <a name="lexv2-Type-ImportSummary-mergeStrategy"></a>
The strategy used to merge existing bot or bot locale definitions with the imported definition\.  
Type: String  
Valid Values:` Overwrite | FailOnConflict`   
Required: No

## See Also<a name="API_ImportSummary_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [ AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/models.lex.v2-2020-08-07/ImportSummary) 
+  [ AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/models.lex.v2-2020-08-07/ImportSummary) 
+  [ AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/models.lex.v2-2020-08-07/ImportSummary) 
+  [ AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/models.lex.v2-2020-08-07/ImportSummary) 