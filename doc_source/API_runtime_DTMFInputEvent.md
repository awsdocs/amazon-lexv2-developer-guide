# DTMFInputEvent<a name="API_runtime_DTMFInputEvent"></a>

A DTMF character sent from the client application\. DTMF characters are typically sent from a phone keypad to represent numbers\. For example, you can have Amazon Lex V2 process a credit card number input from a phone\.

## Contents<a name="API_runtime_DTMFInputEvent_Contents"></a>

 **clientTimestampMillis**   <a name="lexv2-Type-runtime_DTMFInputEvent-clientTimestampMillis"></a>
A timestamp set by the client of the date and time that the event was sent to Amazon Lex V2\.  
Type: Long  
Required: No

 **eventId**   <a name="lexv2-Type-runtime_DTMFInputEvent-eventId"></a>
A unique identifier that your application assigns to the event\. You can use this to identify events in logs\.  
Type: String  
Length Constraints: Minimum length of 2\. Maximum length of 100\.  
Pattern: `[0-9a-zA-Z._:-]+`   
Required: No

 **inputCharacter**   <a name="lexv2-Type-runtime_DTMFInputEvent-inputCharacter"></a>
The DTMF character that the user pressed\. The allowed characters are A \- D, 0 \- 9, \# and \*\.  
Type: String  
Length Constraints: Fixed length of 1\.  
Pattern: `^[A-D0-9#*]{1}$`   
Required: Yes

## See Also<a name="API_runtime_DTMFInputEvent_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [ AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/runtime.lex.v2-2020-08-07/DTMFInputEvent) 
+  [ AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/runtime.lex.v2-2020-08-07/DTMFInputEvent) 
+  [ AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/runtime.lex.v2-2020-08-07/DTMFInputEvent) 
+  [ AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/runtime.lex.v2-2020-08-07/DTMFInputEvent) 