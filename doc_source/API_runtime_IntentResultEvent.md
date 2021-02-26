# IntentResultEvent<a name="API_runtime_IntentResultEvent"></a>

Contains the current state of the conversation between the client application and Amazon Lex\.

## Contents<a name="API_runtime_IntentResultEvent_Contents"></a>

 **eventId**   <a name="lexv2-Type-runtime_IntentResultEvent-eventId"></a>
A unique identifier of the event sent by Amazon Lex\. The identifier is in the form `RESPONSE-N`, where N is a number starting with one and incremented for each event sent by Amazon Lex in the current session\.  
Type: String  
Length Constraints: Minimum length of 2\. Maximum length of 100\.  
Pattern: `[0-9a-zA-Z._:-]+`   
Required: No

 **inputMode**   <a name="lexv2-Type-runtime_IntentResultEvent-inputMode"></a>
Indicates whether the input to the operation was text or speech\.  
Type: String  
Valid Values:` Text | Speech | DTMF`   
Required: No

 **interpretations**   <a name="lexv2-Type-runtime_IntentResultEvent-interpretations"></a>
A list of intents that Amazon Lex determined might satisfy the user's utterance\.  
Each interpretation includes the intent, a score that indicates how confident Amazon Lex is that the interpretation is the correct one, and an optional sentiment response that indicates the sentiment expressed in the utterance\.  
Type: Array of [Interpretation](API_runtime_Interpretation.md) objects  
Array Members: Maximum number of 5 items\.  
Required: No

 **requestAttributes**   <a name="lexv2-Type-runtime_IntentResultEvent-requestAttributes"></a>
The attributes sent in the request\.  
Type: String to string map  
Key Length Constraints: Minimum length of 1\.  
Required: No

 **sessionId**   <a name="lexv2-Type-runtime_IntentResultEvent-sessionId"></a>
The identifier of the session in use\.  
Type: String  
Length Constraints: Minimum length of 2\. Maximum length of 100\.  
Pattern: `[0-9a-zA-Z._:-]+`   
Required: No

 **sessionState**   <a name="lexv2-Type-runtime_IntentResultEvent-sessionState"></a>
The state of the user's session with Amazon Lex\.  
Type: [SessionState](API_runtime_SessionState.md) object  
Required: No

## See Also<a name="API_runtime_IntentResultEvent_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/runtime.lex.v2-2020-08-07/IntentResultEvent) 
+  [AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/runtime.lex.v2-2020-08-07/IntentResultEvent) 
+  [AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/runtime.lex.v2-2020-08-07/IntentResultEvent) 
+  [AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/runtime.lex.v2-2020-08-07/IntentResultEvent) 