# ResponseSpecification<a name="API_ResponseSpecification"></a>

Specifies a list of message groups that Amazon Lex uses to respond the user input\.

## Contents<a name="API_ResponseSpecification_Contents"></a>

 **allowInterrupt**   <a name="lexv2-Type-ResponseSpecification-allowInterrupt"></a>
Indicates whether the user can interrupt a speech response from Amazon Lex\.  
Type: Boolean  
Required: No

 **messageGroups**   <a name="lexv2-Type-ResponseSpecification-messageGroups"></a>
A collection of responses that Amazon Lex can send to the user\. Amazon Lex chooses the actual response to send at runtime\.  
Type: Array of [MessageGroup](API_MessageGroup.md) objects  
Array Members: Minimum number of 1 item\. Maximum number of 5 items\.  
Required: Yes

## See Also<a name="API_ResponseSpecification_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/models.lex.v2-2020-08-07/ResponseSpecification) 
+  [AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/models.lex.v2-2020-08-07/ResponseSpecification) 
+  [AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/models.lex.v2-2020-08-07/ResponseSpecification) 
+  [AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/models.lex.v2-2020-08-07/ResponseSpecification) 