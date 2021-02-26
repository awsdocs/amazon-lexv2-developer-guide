# SessionState<a name="API_runtime_SessionState"></a>

The state of the user's session with Amazon Lex\.

## Contents<a name="API_runtime_SessionState_Contents"></a>

 **activeContexts**   <a name="lexv2-Type-runtime_SessionState-activeContexts"></a>
One or more contexts that indicate to Amazon Lex the context of a request\. When a context is active, Amazon Lex considers intents with the matching context as a trigger as the next intent in a session\.  
Type: Array of [ActiveContext](API_runtime_ActiveContext.md) objects  
Array Members: Minimum number of 0 items\. Maximum number of 20 items\.  
Required: No

 **dialogAction**   <a name="lexv2-Type-runtime_SessionState-dialogAction"></a>
The next step that Amazon Lex should take in the conversation with a user\.  
Type: [DialogAction](API_runtime_DialogAction.md) object  
Required: No

 **intent**   <a name="lexv2-Type-runtime_SessionState-intent"></a>
The active intent that Amazon Lex is processing\.  
Type: [Intent](API_runtime_Intent.md) object  
Required: No

 **originatingRequestId**   <a name="lexv2-Type-runtime_SessionState-originatingRequestId"></a>
  
Type: String  
Length Constraints: Minimum length of 1\.  
Required: No

 **sessionAttributes**   <a name="lexv2-Type-runtime_SessionState-sessionAttributes"></a>
Map of key/value pairs representing session\-specific context information\. It contains application information passed between Amazon Lex and a client application\.  
Type: String to string map  
Key Length Constraints: Minimum length of 1\.  
Required: No

## See Also<a name="API_runtime_SessionState_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/runtime.lex.v2-2020-08-07/SessionState) 
+  [AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/runtime.lex.v2-2020-08-07/SessionState) 
+  [AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/runtime.lex.v2-2020-08-07/SessionState) 
+  [AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/runtime.lex.v2-2020-08-07/SessionState) 