# AudioResponseEvent<a name="API_runtime_AudioResponseEvent"></a>

An event sent from Amazon Lex V2 to your client application containing audio to play to the user\. 

## Contents<a name="API_runtime_AudioResponseEvent_Contents"></a>

 **audioChunk**   <a name="lexv2-Type-runtime_AudioResponseEvent-audioChunk"></a>
A chunk of the audio to play\.   
Type: Base64\-encoded binary data object  
Required: No

 **contentType**   <a name="lexv2-Type-runtime_AudioResponseEvent-contentType"></a>
The encoding of the audio chunk\. This is the same as the encoding configure in the `contentType` field of the `ConfigurationEvent`\.  
Type: String  
Length Constraints: Minimum length of 1\.  
Required: No

 **eventId**   <a name="lexv2-Type-runtime_AudioResponseEvent-eventId"></a>
A unique identifier of the event sent by Amazon Lex V2\. The identifier is in the form `RESPONSE-N`, where N is a number starting with one and incremented for each event sent by Amazon Lex V2 in the current session\.  
Type: String  
Length Constraints: Minimum length of 2\. Maximum length of 100\.  
Pattern: `[0-9a-zA-Z._:-]+`   
Required: No

## See Also<a name="API_runtime_AudioResponseEvent_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [ AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/runtime.lex.v2-2020-08-07/AudioResponseEvent) 
+  [ AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/runtime.lex.v2-2020-08-07/AudioResponseEvent) 
+  [ AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/runtime.lex.v2-2020-08-07/AudioResponseEvent) 
+  [ AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/runtime.lex.v2-2020-08-07/AudioResponseEvent) 