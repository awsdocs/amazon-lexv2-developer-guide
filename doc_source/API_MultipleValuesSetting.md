# MultipleValuesSetting<a name="API_MultipleValuesSetting"></a>

Indicates whether a slot can return multiple values\.

## Contents<a name="API_MultipleValuesSetting_Contents"></a>

 **allowMultipleValues**   <a name="lexv2-Type-MultipleValuesSetting-allowMultipleValues"></a>
Indicates whether a slot can return multiple values\. When `true`, the slot may return more than one value in a response\. When `false`, the slot returns only a single value\.  
Multi\-value slots are only available in the en\-US locale\. If you set this value to `true` in any other locale, Amazon Lex throws a `ValidationException`\.  
If the `allowMutlipleValues` is not set, the default value is `false`\.  
Type: Boolean  
Required: No

## See Also<a name="API_MultipleValuesSetting_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [ AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/models.lex.v2-2020-08-07/MultipleValuesSetting) 
+  [ AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/models.lex.v2-2020-08-07/MultipleValuesSetting) 
+  [ AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/models.lex.v2-2020-08-07/MultipleValuesSetting) 
+  [ AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/models.lex.v2-2020-08-07/MultipleValuesSetting) 