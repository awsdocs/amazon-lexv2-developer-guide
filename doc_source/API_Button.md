# Button<a name="API_Button"></a>

Describes a button to use on a response card used to gather slot values from a user\.

## Contents<a name="API_Button_Contents"></a>

 **text**   <a name="lexv2-Type-Button-text"></a>
The text that appears on the button\. Use this to tell the user what value is returned when they choose this button\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 50\.  
Required: Yes

 **value**   <a name="lexv2-Type-Button-value"></a>
The value returned to Amazon Lex when the user chooses this button\. This must be one of the slot values configured for the slot\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 50\.  
Required: Yes

## See Also<a name="API_Button_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/models.lex.v2-2020-08-07/Button) 
+  [AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/models.lex.v2-2020-08-07/Button) 
+  [AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/models.lex.v2-2020-08-07/Button) 
+  [AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/models.lex.v2-2020-08-07/Button) 