# DialogAction<a name="API_runtime_DialogAction"></a>

The next action that Amazon Lex V2 should take\.

## Contents<a name="API_runtime_DialogAction_Contents"></a>

 **slotToElicit**   <a name="lexv2-Type-runtime_DialogAction-slotToElicit"></a>
The name of the slot that should be elicited from the user\.  
Type: String  
Length Constraints: Minimum length of 1\.  
Required: No

 **type**   <a name="lexv2-Type-runtime_DialogAction-type"></a>
The next action that the bot should take in its interaction with the user\. The possible values are:  
+  `Close` \- Indicates that there will not be a response from the user\. For example, the statement "Your order has been placed" does not require a response\.
+  `ConfirmIntent` \- The next action is asking the user if the intent is complete and ready to be fulfilled\. This is a yes/no question such as "Place the order?"
+  `Delegate` \- The next action is determined by Amazon Lex V2\.
+  `ElicitSlot` \- The next action is to elicit a slot value from the user\.
Type: String  
Valid Values:` Close | ConfirmIntent | Delegate | ElicitIntent | ElicitSlot | None`   
Required: Yes

## See Also<a name="API_runtime_DialogAction_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [ AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/runtime.lex.v2-2020-08-07/DialogAction) 
+  [ AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/runtime.lex.v2-2020-08-07/DialogAction) 
+  [ AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/runtime.lex.v2-2020-08-07/DialogAction) 
+  [ AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/runtime.lex.v2-2020-08-07/DialogAction) 