# ActiveContext<a name="API_runtime_ActiveContext"></a>

Contains information about the contexts that a user is using in a session\. You can configure Amazon Lex V2 to set a context when an intent is fulfilled, or you can set a context using the [PutSession](API_runtime_PutSession.md), [RecognizeText](API_runtime_RecognizeText.md), or [RecognizeUtterance](API_runtime_RecognizeUtterance.md) operations\.

Use a context to indicate to Amazon Lex V2 intents that should be used as follow\-up intents\. For example, if the active context is `order-fulfilled`, only intents that have `order-fulfilled` configured as a trigger are considered for follow up\.

## Contents<a name="API_runtime_ActiveContext_Contents"></a>

 **contextAttributes**   <a name="lexv2-Type-runtime_ActiveContext-contextAttributes"></a>
A lis tof contexts active for the request\. A context can be activated when a previous intent is fulfilled, or by including the context in the request\.  
If you don't specify a list of contexts, Amazon Lex will use the current list of contexts for the session\. If you specify an empty list, all contexts for the session are cleared\.   
Type: String to string map  
Map Entries: Minimum number of 0 items\. Maximum number of 10 items\.  
Key Length Constraints: Minimum length of 1\. Maximum length of 100\.  
Value Length Constraints: Minimum length of 1\. Maximum length of 1024\.  
Required: Yes

 **name**   <a name="lexv2-Type-runtime_ActiveContext-name"></a>
The name of the context\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 100\.  
Pattern: `^([A-Za-z]_?)+$`   
Required: Yes

 **timeToLive**   <a name="lexv2-Type-runtime_ActiveContext-timeToLive"></a>
Indicates the number of turns or seconds that the context is active\. Once the time to live expires, the context is no longer returned in a response\.  
Type: [ActiveContextTimeToLive](API_runtime_ActiveContextTimeToLive.md) object  
Required: Yes

## See Also<a name="API_runtime_ActiveContext_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [ AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/runtime.lex.v2-2020-08-07/ActiveContext) 
+  [ AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/runtime.lex.v2-2020-08-07/ActiveContext) 
+  [ AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/runtime.lex.v2-2020-08-07/ActiveContext) 
+  [ AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/runtime.lex.v2-2020-08-07/ActiveContext) 