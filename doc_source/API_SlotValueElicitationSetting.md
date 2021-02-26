# SlotValueElicitationSetting<a name="API_SlotValueElicitationSetting"></a>

Settings that you can use for eliciting a slot value\.

## Contents<a name="API_SlotValueElicitationSetting_Contents"></a>

 **defaultValueSpecification**   <a name="lexv2-Type-SlotValueElicitationSetting-defaultValueSpecification"></a>
A list of default values for a slot\. Default values are used when Amazon Lex hasn't determined a value for a slot\. You can specify default values from context variables, sesion attributes, and defined values\.  
Type: [SlotDefaultValueSpecification](API_SlotDefaultValueSpecification.md) object  
Required: No

 **promptSpecification**   <a name="lexv2-Type-SlotValueElicitationSetting-promptSpecification"></a>
The prompt that Amazon Lex uses to elicit the slot value from the user\.  
Type: [PromptSpecification](API_PromptSpecification.md) object  
Required: No

 **sampleUtterances**   <a name="lexv2-Type-SlotValueElicitationSetting-sampleUtterances"></a>
If you know a specific pattern that users might respond to an Amazon Lex request for a slot value, you can provide those utterances to improve accuracy\. This is optional\. In most cases, Amazon Lex is capable of understanding user utterances\.  
Type: Array of [SampleUtterance](API_SampleUtterance.md) objects  
Required: No

 **slotConstraint**   <a name="lexv2-Type-SlotValueElicitationSetting-slotConstraint"></a>
Specifies whether the slot is required or optional\.  
Type: String  
Valid Values:` Required | Optional`   
Required: Yes

 **waitAndContinueSpecification**   <a name="lexv2-Type-SlotValueElicitationSetting-waitAndContinueSpecification"></a>
Specifies the prompts that Amazon Lex uses while a bot is waiting for customer input\.   
Type: [WaitAndContinueSpecification](API_WaitAndContinueSpecification.md) object  
Required: No

## See Also<a name="API_SlotValueElicitationSetting_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/models.lex.v2-2020-08-07/SlotValueElicitationSetting) 
+  [AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/models.lex.v2-2020-08-07/SlotValueElicitationSetting) 
+  [AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/models.lex.v2-2020-08-07/SlotValueElicitationSetting) 
+  [AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/models.lex.v2-2020-08-07/SlotValueElicitationSetting) 