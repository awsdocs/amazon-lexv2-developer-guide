# SlotTypeSummary<a name="API_SlotTypeSummary"></a>

Provides summary information about a slot type\.

## Contents<a name="API_SlotTypeSummary_Contents"></a>

 **description**   <a name="lexv2-Type-SlotTypeSummary-description"></a>
The description of the slot type\.  
Type: String  
Length Constraints: Minimum length of 0\. Maximum length of 200\.  
Required: No

 **lastUpdatedDateTime**   <a name="lexv2-Type-SlotTypeSummary-lastUpdatedDateTime"></a>
A timestamp of the date and time that the slot type was last updated\.  
Type: Timestamp  
Required: No

 **parentSlotTypeSignature**   <a name="lexv2-Type-SlotTypeSummary-parentSlotTypeSignature"></a>
If the slot type is derived from a built\-on slot type, the name of the parent slot type\.  
Type: String  
Required: No

 **slotTypeId**   <a name="lexv2-Type-SlotTypeSummary-slotTypeId"></a>
The unique identifier assigned to the slot type\.  
Type: String  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$`   
Required: No

 **slotTypeName**   <a name="lexv2-Type-SlotTypeSummary-slotTypeName"></a>
The name of the slot type\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 100\.  
Pattern: `^([0-9a-zA-Z][_-]?)+$`   
Required: No

## See Also<a name="API_SlotTypeSummary_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/models.lex.v2-2020-08-07/SlotTypeSummary) 
+  [AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/models.lex.v2-2020-08-07/SlotTypeSummary) 
+  [AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/models.lex.v2-2020-08-07/SlotTypeSummary) 
+  [AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/models.lex.v2-2020-08-07/SlotTypeSummary) 