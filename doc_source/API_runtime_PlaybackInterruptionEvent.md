# PlaybackInterruptionEvent<a name="API_runtime_PlaybackInterruptionEvent"></a>

Event sent from Amazon Lex V2 to indicate to the client application should stop playback of audio\. For example, if the client is playing a prompt that asks for the user's telephone number, the user might start to say the phone number before the prompt is complete\. Amazon Lex V2 sends this event to the client application to indicate that the user is responding and that Amazon Lex V2 is processing their input\.

## Contents<a name="API_runtime_PlaybackInterruptionEvent_Contents"></a>

 **causedByEventId**   <a name="lexv2-Type-runtime_PlaybackInterruptionEvent-causedByEventId"></a>
The identifier of the event that contained the audio, DTMF, or text that caused the interruption\.  
Type: String  
Length Constraints: Minimum length of 2\. Maximum length of 100\.  
Pattern: `[0-9a-zA-Z._:-]+`   
Required: No

 **eventId**   <a name="lexv2-Type-runtime_PlaybackInterruptionEvent-eventId"></a>
A unique identifier of the event sent by Amazon Lex V2\. The identifier is in the form `RESPONSE-N`, where N is a number starting with one and incremented for each event sent by Amazon Lex V2 in the current session\.  
Type: String  
Length Constraints: Minimum length of 2\. Maximum length of 100\.  
Pattern: `[0-9a-zA-Z._:-]+`   
Required: No

 **eventReason**   <a name="lexv2-Type-runtime_PlaybackInterruptionEvent-eventReason"></a>
Indicates the type of user input that Amazon Lex V2 detected\.  
Type: String  
Valid Values:` DTMF_START_DETECTED | TEXT_DETECTED | VOICE_START_DETECTED`   
Required: No

## See Also<a name="API_runtime_PlaybackInterruptionEvent_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [ AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/runtime.lex.v2-2020-08-07/PlaybackInterruptionEvent) 
+  [ AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/runtime.lex.v2-2020-08-07/PlaybackInterruptionEvent) 
+  [ AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/runtime.lex.v2-2020-08-07/PlaybackInterruptionEvent) 
+  [ AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/runtime.lex.v2-2020-08-07/PlaybackInterruptionEvent) 