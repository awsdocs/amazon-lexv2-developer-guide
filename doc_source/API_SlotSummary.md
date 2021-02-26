# SlotSummary<a name="API_SlotSummary"></a>

Summary information about a slot, a value that the bot elicits from the user\.

## Contents<a name="API_SlotSummary_Contents"></a>

 **description**   <a name="lexv2-Type-SlotSummary-description"></a>
The description of the slot\.  
Type: String  
Length Constraints: Minimum length of 0\. Maximum length of 200\.  
Required: No

 **lastUpdatedDateTime**   <a name="lexv2-Type-SlotSummary-lastUpdatedDateTime"></a>
The timestamp of the last date and time that the slot was updated\.  
Type: Timestamp  
Required: No

 **slotConstraint**   <a name="lexv2-Type-SlotSummary-slotConstraint"></a>
Whether the slot is required or optional\. An intent is complete when all required slots are filled\.  
Type: String  
Valid Values:` Required | Optional`   
Required: No

 **slotId**   <a name="lexv2-Type-SlotSummary-slotId"></a>
The unique identifier of the slot\.  
Type: String  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$`   
Required: No

 **slotName**   <a name="lexv2-Type-SlotSummary-slotName"></a>
The name given to the slot\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 100\.  
Pattern: `^([0-9a-zA-Z][_-]?)+$`   
Required: No

 **slotTypeId**   <a name="lexv2-Type-SlotSummary-slotTypeId"></a>
The unique identifier for the slot type that defines the values for the slot\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 25\.  
Pattern: `^((AMAZON\.)[a-zA-Z_]+?|[0-9a-zA-Z]+)$`   
Required: No

 **valueElicitationPromptSpecification**   <a name="lexv2-Type-SlotSummary-valueElicitationPromptSpecification"></a>
Prompts that are sent to the user to elicit a value for the slot\.  
Type: [PromptSpecification](API_PromptSpecification.md) object  
Required: No

## See Also<a name="API_SlotSummary_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/models.lex.v2-2020-08-07/SlotSummary) 
+  [AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/models.lex.v2-2020-08-07/SlotSummary) 
+  [AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/models.lex.v2-2020-08-07/SlotSummary) 
+  [AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/models.lex.v2-2020-08-07/SlotSummary) 