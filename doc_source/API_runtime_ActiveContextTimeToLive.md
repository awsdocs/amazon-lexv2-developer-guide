# ActiveContextTimeToLive<a name="API_runtime_ActiveContextTimeToLive"></a>

The time that a context is active\. You can specify the time to live in seconds or in conversation turns\.

## Contents<a name="API_runtime_ActiveContextTimeToLive_Contents"></a>

 **timeToLiveInSeconds**   <a name="lexv2-Type-runtime_ActiveContextTimeToLive-timeToLiveInSeconds"></a>
The number of seconds that the context is active\. You can specify between 5 and 86400 seconds \(24 hours\)\.  
Type: Integer  
Valid Range: Minimum value of 5\. Maximum value of 86400\.  
Required: Yes

 **turnsToLive**   <a name="lexv2-Type-runtime_ActiveContextTimeToLive-turnsToLive"></a>
The number of turns that the context is active\. You can specify up to 20 turns\. Each request and response from the bot is a turn\.  
Type: Integer  
Valid Range: Minimum value of 1\. Maximum value of 20\.  
Required: Yes

## See Also<a name="API_runtime_ActiveContextTimeToLive_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [ AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/runtime.lex.v2-2020-08-07/ActiveContextTimeToLive) 
+  [ AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/runtime.lex.v2-2020-08-07/ActiveContextTimeToLive) 
+  [ AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/runtime.lex.v2-2020-08-07/ActiveContextTimeToLive) 
+  [ AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/runtime.lex.v2-2020-08-07/ActiveContextTimeToLive) 