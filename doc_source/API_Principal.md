# Principal<a name="API_Principal"></a>

The IAM principal that you allowing or denying access to an Amazon Lex action\. You must provide a `service` or an `arn`, but not both in the same statement\. For more information, see [ AWS JSON policy elements: Principal ](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_elements_principal.html)\.

## Contents<a name="API_Principal_Contents"></a>

 **arn**   <a name="lexv2-Type-Principal-arn"></a>
The Amazon Resource Name \(ARN\) of the principal\.  
Type: String  
Length Constraints: Minimum length of 30\. Maximum length of 1024\.  
Pattern: `^arn:aws:iam::[0-9]{12}:(root|(user|role)/.*)$`   
Required: No

 **service**   <a name="lexv2-Type-Principal-service"></a>
The name of the AWS service that should allowed or denied access to an Amazon Lex action\.  
Type: String  
Length Constraints: Minimum length of 15\. Maximum length of 1024\.  
Pattern: `^[0-9a-zA-Z_.]+$`   
Required: No

## See Also<a name="API_Principal_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [ AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/models.lex.v2-2020-08-07/Principal) 
+  [ AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/models.lex.v2-2020-08-07/Principal) 
+  [ AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/models.lex.v2-2020-08-07/Principal) 
+  [ AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/models.lex.v2-2020-08-07/Principal) 