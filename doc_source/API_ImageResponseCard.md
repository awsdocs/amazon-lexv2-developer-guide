# ImageResponseCard<a name="API_ImageResponseCard"></a>

A card that is shown to the user by a messaging platform\. You define the contents of the card, the card is displayed by the platform\. 

When you use a response card, the response from the user is constrained to the text associated with a button on the card\.

## Contents<a name="API_ImageResponseCard_Contents"></a>

 **buttons**   <a name="lexv2-Type-ImageResponseCard-buttons"></a>
A list of buttons that should be displayed on the response card\. The arrangement of the buttons is determined by the platform that displays the button\.  
Type: Array of [Button](API_Button.md) objects  
Array Members: Minimum number of 0 items\. Maximum number of 5 items\.  
Required: No

 **imageUrl**   <a name="lexv2-Type-ImageResponseCard-imageUrl"></a>
The URL of an image to display on the response card\. The image URL must be publicly available so that the platform displaying the response card has access to the image\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 250\.  
Required: No

 **subtitle**   <a name="lexv2-Type-ImageResponseCard-subtitle"></a>
The subtitle to display on the response card\. The format of the subtitle is determined by the platform displaying the response card\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 250\.  
Required: No

 **title**   <a name="lexv2-Type-ImageResponseCard-title"></a>
The title to display on the response card\. The format of the title is determined by the platform displaying the response card\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 250\.  
Required: Yes

## See Also<a name="API_ImageResponseCard_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [ AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/models.lex.v2-2020-08-07/ImageResponseCard) 
+  [ AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/models.lex.v2-2020-08-07/ImageResponseCard) 
+  [ AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/models.lex.v2-2020-08-07/ImageResponseCard) 
+  [ AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/models.lex.v2-2020-08-07/ImageResponseCard) 