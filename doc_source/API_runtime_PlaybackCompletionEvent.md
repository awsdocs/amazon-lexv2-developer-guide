# PlaybackCompletionEvent<a name="API_runtime_PlaybackCompletionEvent"></a>

Event sent from the client application to Amazon Lex to indicate that playback of audio is complete and that Amazon Lex should start processing the user's input\.

## Contents<a name="API_runtime_PlaybackCompletionEvent_Contents"></a>

 **clientTimestampMillis**   <a name="lexv2-Type-runtime_PlaybackCompletionEvent-clientTimestampMillis"></a>
A timestamp set by the client of the date and time that the event was sent to Amazon Lex\.  
Type: Long  
Required: No

 **eventId**   <a name="lexv2-Type-runtime_PlaybackCompletionEvent-eventId"></a>
A unique identifier that your application assigns to the event\. You can use this to identify events in logs\.  
Type: String  
Length Constraints: Minimum length of 2\. Maximum length of 100\.  
Pattern: `[0-9a-zA-Z._:-]+`   
Required: No

## See Also<a name="API_runtime_PlaybackCompletionEvent_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/runtime.lex.v2-2020-08-07/PlaybackCompletionEvent) 
+  [AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/runtime.lex.v2-2020-08-07/PlaybackCompletionEvent) 
+  [AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/runtime.lex.v2-2020-08-07/PlaybackCompletionEvent) 
+  [AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/runtime.lex.v2-2020-08-07/PlaybackCompletionEvent) 