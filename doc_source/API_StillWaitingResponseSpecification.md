# StillWaitingResponseSpecification<a name="API_StillWaitingResponseSpecification"></a>

Defines the messages that Amazon Lex sends to a user to remind them that the bot is waiting for a response\.

## Contents<a name="API_StillWaitingResponseSpecification_Contents"></a>

 **allowInterrupt**   <a name="lexv2-Type-StillWaitingResponseSpecification-allowInterrupt"></a>
Indicates that the user can interrupt the response by speaking while the message is being played\.  
Type: Boolean  
Required: No

 **frequencyInSeconds**   <a name="lexv2-Type-StillWaitingResponseSpecification-frequencyInSeconds"></a>
How often a message should be sent to the user\. Minimum of 1 second, maximum of 5 minutes\.  
Type: Integer  
Valid Range: Minimum value of 1\. Maximum value of 300\.  
Required: Yes

 **messageGroups**   <a name="lexv2-Type-StillWaitingResponseSpecification-messageGroups"></a>
One or more message groups, each containing one or more messages, that define the prompts that Amazon Lex sends to the user\.  
Type: Array of [MessageGroup](API_MessageGroup.md) objects  
Array Members: Minimum number of 1 item\. Maximum number of 5 items\.  
Required: Yes

 **timeoutInSeconds**   <a name="lexv2-Type-StillWaitingResponseSpecification-timeoutInSeconds"></a>
If Amazon Lex waits longer than this length of time for a response, it will stop sending messages\.  
Type: Integer  
Valid Range: Minimum value of 1\. Maximum value of 900\.  
Required: Yes

## See Also<a name="API_StillWaitingResponseSpecification_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [ AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/models.lex.v2-2020-08-07/StillWaitingResponseSpecification) 
+  [ AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/models.lex.v2-2020-08-07/StillWaitingResponseSpecification) 
+  [ AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/models.lex.v2-2020-08-07/StillWaitingResponseSpecification) 
+  [ AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/models.lex.v2-2020-08-07/StillWaitingResponseSpecification) 