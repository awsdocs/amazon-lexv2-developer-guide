# LambdaCodeHook<a name="API_LambdaCodeHook"></a>

Specifies a Lambda function that verifies requests to a bot or fulfilles the user's request to a bot\.

## Contents<a name="API_LambdaCodeHook_Contents"></a>

 **codeHookInterfaceVersion**   <a name="lexv2-Type-LambdaCodeHook-codeHookInterfaceVersion"></a>
The version of the request\-response that you want Amazon Lex to use to invoke your Lambda function\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 5\.  
Required: Yes

 **lambdaARN**   <a name="lexv2-Type-LambdaCodeHook-lambdaARN"></a>
The Amazon Resource Name \(ARN\) of the Lambda function\.  
Type: String  
Length Constraints: Minimum length of 20\. Maximum length of 2048\.  
Pattern: `arn:aws:lambda:[a-z]+-[a-z]+-[0-9]:[0-9]{12}:function:[a-zA-Z0-9-_]+(/[0-9a-f]{8}-[0-9a-f]{4}-[0-9a-f]{4}-[0-9a-f]{4}-[0-9a-f]{12})?(:[a-zA-Z0-9-_]+)?`   
Required: Yes

## See Also<a name="API_LambdaCodeHook_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [ AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/models.lex.v2-2020-08-07/LambdaCodeHook) 
+  [ AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/models.lex.v2-2020-08-07/LambdaCodeHook) 
+  [ AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/models.lex.v2-2020-08-07/LambdaCodeHook) 
+  [ AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/models.lex.v2-2020-08-07/LambdaCodeHook) 