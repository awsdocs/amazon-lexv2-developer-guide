# Slot<a name="API_runtime_Slot"></a>

A value that Amazon Lex V2 uses to fulfill an intent\. 

## Contents<a name="API_runtime_Slot_Contents"></a>

 **shape**   <a name="lexv2-Type-runtime_Slot-shape"></a>
When the `shape` value is `List`, it indicates that the `values` field contains a list of slot values\. When the value is `Scalar`, it indicates that the `value` field contains a single value\.  
Type: String  
Valid Values:` Scalar | List`   
Required: No

 **value**   <a name="lexv2-Type-runtime_Slot-value"></a>
The current value of the slot\.  
Type: [Value](API_runtime_Value.md) object  
Required: No

 **values**   <a name="lexv2-Type-runtime_Slot-values"></a>
A list of one or more values that the user provided for the slot\. For example, if a for a slot that elicits pizza toppings, the values might be "pepperoni" and "pineapple\."   
Type: Array of [Slot](#API_runtime_Slot) objects  
Required: No

## See Also<a name="API_runtime_Slot_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [ AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/runtime.lex.v2-2020-08-07/Slot) 
+  [ AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/runtime.lex.v2-2020-08-07/Slot) 
+  [ AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/runtime.lex.v2-2020-08-07/Slot) 
+  [ AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/runtime.lex.v2-2020-08-07/Slot) 