# KendraConfiguration<a name="API_KendraConfiguration"></a>

Provides configuration information for the AMAZON\.KendraSearchIntent intent\. When you use this intent, Amazon Lex searches the specified Amazon Kendra index and returns documents from the index that match the user's utterance\.

## Contents<a name="API_KendraConfiguration_Contents"></a>

 **kendraIndex**   <a name="lexv2-Type-KendraConfiguration-kendraIndex"></a>
The Amazon Resource Name \(ARN\) of the Amazon Kendra index that you want the AMAZON\.KendraSearchIntent intent to search\. The index must be in the same account and Region as the Amazon Lex bot\.  
Type: String  
Length Constraints: Minimum length of 32\. Maximum length of 2048\.  
Pattern: `^arn:aws:kendra:[a-z]+-[a-z]+-[0-9]:[0-9]{12}:index\/[a-zA-Z0-9][a-zA-Z0-9_-]*$`   
Required: Yes

 **queryFilterString**   <a name="lexv2-Type-KendraConfiguration-queryFilterString"></a>
A query filter that Amazon Lex sends to Amazon Kendra to filter the response from a query\. The filter is in the format defined by Amazon Kendra\. For more information, see [Filtering queries](https://docs.aws.amazon.com/kendra/latest/dg/filtering.html)\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 5000\.  
Required: No

 **queryFilterStringEnabled**   <a name="lexv2-Type-KendraConfiguration-queryFilterStringEnabled"></a>
Determines whether the AMAZON\.KendraSearchIntent intent uses a custom query string to query the Amazon Kendra index\.  
Type: Boolean  
Required: No

## See Also<a name="API_KendraConfiguration_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/models.lex.v2-2020-08-07/KendraConfiguration) 
+  [AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/models.lex.v2-2020-08-07/KendraConfiguration) 
+  [AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/models.lex.v2-2020-08-07/KendraConfiguration) 
+  [AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/models.lex.v2-2020-08-07/KendraConfiguration) 