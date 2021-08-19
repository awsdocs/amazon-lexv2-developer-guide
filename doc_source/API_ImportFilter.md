# ImportFilter<a name="API_ImportFilter"></a>

Filters the response from the [ListImports](API_ListImports.md) operation\.

## Contents<a name="API_ImportFilter_Contents"></a>

 **name**   <a name="lexv2-Type-ImportFilter-name"></a>
The name of the field to use for filtering\.  
Type: String  
Valid Values:` ImportResourceType`   
Required: Yes

 **operator**   <a name="lexv2-Type-ImportFilter-operator"></a>
The operator to use for the filter\. Specify EQ when the `ListImports` operation should return only resource types that equal the specified value\. Specify CO when the `ListImports` operation should return resource types that contain the specified value\.  
Type: String  
Valid Values:` CO | EQ`   
Required: Yes

 **values**   <a name="lexv2-Type-ImportFilter-values"></a>
The values to use to filter the response\.  
Type: Array of strings  
Array Members: Fixed number of 1 item\.  
Length Constraints: Minimum length of 1\. Maximum length of 100\.  
Pattern: `^[0-9a-zA-Z_()\s-]+$`   
Required: Yes

## See Also<a name="API_ImportFilter_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [ AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/models.lex.v2-2020-08-07/ImportFilter) 
+  [ AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/models.lex.v2-2020-08-07/ImportFilter) 
+  [ AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/models.lex.v2-2020-08-07/ImportFilter) 
+  [ AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/models.lex.v2-2020-08-07/ImportFilter) 