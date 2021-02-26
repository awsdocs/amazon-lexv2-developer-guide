# MessageGroup<a name="API_MessageGroup"></a>

Provides one or more messages that Amazon Lex should send to the user\.

## Contents<a name="API_MessageGroup_Contents"></a>

 **message**   <a name="lexv2-Type-MessageGroup-message"></a>
The primary message that Amazon Lex should send to the user\.  
Type: [Message](API_Message.md) object  
Required: Yes

 **variations**   <a name="lexv2-Type-MessageGroup-variations"></a>
Message variations to send to the user\. When variations are defined, Amazon Lex chooses the primary message or one of the variations to send to the user\.  
Type: Array of [Message](API_Message.md) objects  
Array Members: Minimum number of 0 items\. Maximum number of 2 items\.  
Required: No

## See Also<a name="API_MessageGroup_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/models.lex.v2-2020-08-07/MessageGroup) 
+  [AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/models.lex.v2-2020-08-07/MessageGroup) 
+  [AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/models.lex.v2-2020-08-07/MessageGroup) 
+  [AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/models.lex.v2-2020-08-07/MessageGroup) 