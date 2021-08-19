# SlotValueSelectionSetting<a name="API_SlotValueSelectionSetting"></a>

Contains settings used by Amazon Lex to select a slot value\.

## Contents<a name="API_SlotValueSelectionSetting_Contents"></a>

 **regexFilter**   <a name="lexv2-Type-SlotValueSelectionSetting-regexFilter"></a>
A regular expression used to validate the value of a slot\.  
Type: [SlotValueRegexFilter](API_SlotValueRegexFilter.md) object  
Required: No

 **resolutionStrategy**   <a name="lexv2-Type-SlotValueSelectionSetting-resolutionStrategy"></a>
Determines the slot resolution strategy that Amazon Lex uses to return slot type values\. The field can be set to one of the following values:  
+ OriginalValue \- Returns the value entered by the user, if the user value is similar to the slot value\.
+ TopResolution \- If there is a resolution list for the slot, return the first value in the resolution list as the slot type value\. If there is no resolution list, null is returned\.
If you don't specify the valueSelectionStrategy, the default is OriginalValue\.   
Type: String  
Valid Values:` OriginalValue | TopResolution`   
Required: Yes

## See Also<a name="API_SlotValueSelectionSetting_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [ AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/models.lex.v2-2020-08-07/SlotValueSelectionSetting) 
+  [ AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/models.lex.v2-2020-08-07/SlotValueSelectionSetting) 
+  [ AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/models.lex.v2-2020-08-07/SlotValueSelectionSetting) 
+  [ AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/models.lex.v2-2020-08-07/SlotValueSelectionSetting) 