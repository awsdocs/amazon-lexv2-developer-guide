# AudioInputEvent<a name="API_runtime_AudioInputEvent"></a>

Represents a chunk of audio sent from the client application to Amazon Lex\. The audio is all or part of an utterance from the user\.

Amazon Lex accumulates audio chunks until it recognizes a natural pause in speech before processing the input\.

## Contents<a name="API_runtime_AudioInputEvent_Contents"></a>

 **audioChunk**   <a name="lexv2-Type-runtime_AudioInputEvent-audioChunk"></a>
An encoded stream of audio\.  
Type: Base64\-encoded binary data object  
Required: No

 **clientTimestampMillis**   <a name="lexv2-Type-runtime_AudioInputEvent-clientTimestampMillis"></a>
A timestamp set by the client of the date and time that the event was sent to Amazon Lex\.  
Type: Long  
Required: No

 **contentType**   <a name="lexv2-Type-runtime_AudioInputEvent-contentType"></a>
The encoding used for the audio chunk\. You must use 8 KHz PCM 16\-bit mono\-channel little\-endian format\. The value of the field should be:  
 `audio/lpcm; sample-rate=8000; sample-size-bits=16; channel-count=1; is-big-endian=false`   
Type: String  
Length Constraints: Minimum length of 1\.  
Required: Yes

 **eventId**   <a name="lexv2-Type-runtime_AudioInputEvent-eventId"></a>
A unique identifier that your application assigns to the event\. You can use this to identify events in logs\.  
Type: String  
Length Constraints: Minimum length of 2\. Maximum length of 100\.  
Pattern: `[0-9a-zA-Z._:-]+`   
Required: No

## See Also<a name="API_runtime_AudioInputEvent_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/runtime.lex.v2-2020-08-07/AudioInputEvent) 
+  [AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/runtime.lex.v2-2020-08-07/AudioInputEvent) 
+  [AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/runtime.lex.v2-2020-08-07/AudioInputEvent) 
+  [AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/runtime.lex.v2-2020-08-07/AudioInputEvent) 