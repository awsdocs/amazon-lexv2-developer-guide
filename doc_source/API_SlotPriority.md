# SlotPriority<a name="API_SlotPriority"></a>

Sets the priority that Amazon Lex should use when eliciting slot values from a user\.

## Contents<a name="API_SlotPriority_Contents"></a>

 **priority**   <a name="lexv2-Type-SlotPriority-priority"></a>
The priority that a slot should be elicited\.  
Type: Integer  
Valid Range: Minimum value of 0\. Maximum value of 25\.  
Required: Yes

 **slotId**   <a name="lexv2-Type-SlotPriority-slotId"></a>
The unique identifier of the slot\.  
Type: String  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$`   
Required: Yes

## See Also<a name="API_SlotPriority_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/models.lex.v2-2020-08-07/SlotPriority) 
+  [AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/models.lex.v2-2020-08-07/SlotPriority) 
+  [AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/models.lex.v2-2020-08-07/SlotPriority) 
+  [AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/models.lex.v2-2020-08-07/SlotPriority) 