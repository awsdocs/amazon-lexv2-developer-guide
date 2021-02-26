# IntentFilter<a name="API_IntentFilter"></a>

Filters the response from the `ListIntents` operation\.

## Contents<a name="API_IntentFilter_Contents"></a>

 **name**   <a name="lexv2-Type-IntentFilter-name"></a>
The name of the field to use for the filter\.  
Type: String  
Valid Values:` IntentName`   
Required: Yes

 **operator**   <a name="lexv2-Type-IntentFilter-operator"></a>
The operator to use for the filter\. Specify `EQ` when the `ListIntents` operation should return only aliases that equal the specified value\. Specify `CO` when the `ListIntents` operation should return aliases that contain the specified value\.  
Type: String  
Valid Values:` CO | EQ`   
Required: Yes

 **values**   <a name="lexv2-Type-IntentFilter-values"></a>
The value to use for the filter\.  
Type: Array of strings  
Array Members: Fixed number of 1 item\.  
Length Constraints: Minimum length of 1\. Maximum length of 100\.  
Pattern: `^[0-9a-zA-Z_()\s-]+$`   
Required: Yes

## See Also<a name="API_IntentFilter_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/models.lex.v2-2020-08-07/IntentFilter) 
+  [AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/models.lex.v2-2020-08-07/IntentFilter) 
+  [AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/models.lex.v2-2020-08-07/IntentFilter) 
+  [AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/models.lex.v2-2020-08-07/IntentFilter) 