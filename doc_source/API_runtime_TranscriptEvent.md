# TranscriptEvent<a name="API_runtime_TranscriptEvent"></a>

Event sent from Amazon Lex V2 to your client application that contains a transcript of voice audio\. 

## Contents<a name="API_runtime_TranscriptEvent_Contents"></a>

 **eventId**   <a name="lexv2-Type-runtime_TranscriptEvent-eventId"></a>
A unique identifier of the event sent by Amazon Lex V2\. The identifier is in the form `RESPONSE-N`, where N is a number starting with one and incremented for each event sent by Amazon Lex V2 in the current session\.  
Type: String  
Length Constraints: Minimum length of 2\. Maximum length of 100\.  
Pattern: `[0-9a-zA-Z._:-]+`   
Required: No

 **transcript**   <a name="lexv2-Type-runtime_TranscriptEvent-transcript"></a>
The transcript of the voice audio from the user\.  
Type: String  
Required: No

## See Also<a name="API_runtime_TranscriptEvent_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [ AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/runtime.lex.v2-2020-08-07/TranscriptEvent) 
+  [ AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/runtime.lex.v2-2020-08-07/TranscriptEvent) 
+  [ AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/runtime.lex.v2-2020-08-07/TranscriptEvent) 
+  [ AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/runtime.lex.v2-2020-08-07/TranscriptEvent) 