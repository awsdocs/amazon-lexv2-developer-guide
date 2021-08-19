# Message<a name="API_runtime_Message"></a>

Container for text that is returned to the customer\.\.

## Contents<a name="API_runtime_Message_Contents"></a>

 **content**   <a name="lexv2-Type-runtime_Message-content"></a>
The text of the message\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 1024\.  
Required: No

 **contentType**   <a name="lexv2-Type-runtime_Message-contentType"></a>
Indicates the type of response\.  
Type: String  
Valid Values:` CustomPayload | ImageResponseCard | PlainText | SSML`   
Required: Yes

 **imageResponseCard**   <a name="lexv2-Type-runtime_Message-imageResponseCard"></a>
A card that is shown to the user by a messaging platform\. You define the contents of the card, the card is displayed by the platform\.   
When you use a response card, the response from the user is constrained to the text associated with a button on the card\.  
Type: [ImageResponseCard](API_runtime_ImageResponseCard.md) object  
Required: No

## See Also<a name="API_runtime_Message_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [ AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/runtime.lex.v2-2020-08-07/Message) 
+  [ AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/runtime.lex.v2-2020-08-07/Message) 
+  [ AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/runtime.lex.v2-2020-08-07/Message) 
+  [ AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/runtime.lex.v2-2020-08-07/Message) 