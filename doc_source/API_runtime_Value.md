# Value<a name="API_runtime_Value"></a>

The value of a slot\.

## Contents<a name="API_runtime_Value_Contents"></a>

 **interpretedValue**   <a name="lexv2-Type-runtime_Value-interpretedValue"></a>
The value that Amazon Lex V2 determines for the slot\. The actual value depends on the setting of the value selection strategy for the bot\. You can choose to use the value entered by the user, or you can have Amazon Lex V2 choose the first value in the `resolvedValues` list\.  
Type: String  
Length Constraints: Minimum length of 1\.  
Required: Yes

 **originalValue**   <a name="lexv2-Type-runtime_Value-originalValue"></a>
The text of the utterance from the user that was entered for the slot\.  
Type: String  
Length Constraints: Minimum length of 1\.  
Required: No

 **resolvedValues**   <a name="lexv2-Type-runtime_Value-resolvedValues"></a>
A list of additional values that have been recognized for the slot\.  
Type: Array of strings  
Length Constraints: Minimum length of 1\.  
Required: No

## See Also<a name="API_runtime_Value_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [ AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/runtime.lex.v2-2020-08-07/Value) 
+  [ AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/runtime.lex.v2-2020-08-07/Value) 
+  [ AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/runtime.lex.v2-2020-08-07/Value) 
+  [ AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/runtime.lex.v2-2020-08-07/Value) 