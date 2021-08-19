# Intent<a name="API_runtime_Intent"></a>

The current intent that Amazon Lex V2 is attempting to fulfill\.

## Contents<a name="API_runtime_Intent_Contents"></a>

 **confirmationState**   <a name="lexv2-Type-runtime_Intent-confirmationState"></a>
Contains information about whether fulfillment of the intent has been confirmed\.  
Type: String  
Valid Values:` Confirmed | Denied | None`   
Required: No

 **name**   <a name="lexv2-Type-runtime_Intent-name"></a>
The name of the intent\.  
Type: String  
Length Constraints: Minimum length of 1\.  
Required: Yes

 **slots**   <a name="lexv2-Type-runtime_Intent-slots"></a>
A map of all of the slots for the intent\. The name of the slot maps to the value of the slot\. If a slot has not been filled, the value is null\.  
Type: String to [Slot](API_runtime_Slot.md) object map  
Key Length Constraints: Minimum length of 1\.  
Required: No

 **state**   <a name="lexv2-Type-runtime_Intent-state"></a>
Contains fulfillment information for the intent\.   
Type: String  
Valid Values:` Failed | Fulfilled | InProgress | ReadyForFulfillment | Waiting | FulfillmentInProgress`   
Required: No

## See Also<a name="API_runtime_Intent_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [ AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/runtime.lex.v2-2020-08-07/Intent) 
+  [ AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/runtime.lex.v2-2020-08-07/Intent) 
+  [ AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/runtime.lex.v2-2020-08-07/Intent) 
+  [ AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/runtime.lex.v2-2020-08-07/Intent) 