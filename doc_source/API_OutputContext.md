# OutputContext<a name="API_OutputContext"></a>

Describes a session context that is activated when an intent is fulfilled\.

## Contents<a name="API_OutputContext_Contents"></a>

 **name**   <a name="lexv2-Type-OutputContext-name"></a>
The name of the output context\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 100\.  
Pattern: `^([0-9a-zA-Z][_-]?)+$`   
Required: Yes

 **timeToLiveInSeconds**   <a name="lexv2-Type-OutputContext-timeToLiveInSeconds"></a>
The amount of time, in seconds, that the output context should remain active\. The time is figured from the first time the context is sent to the user\.  
Type: Integer  
Valid Range: Minimum value of 5\. Maximum value of 86400\.  
Required: Yes

 **turnsToLive**   <a name="lexv2-Type-OutputContext-turnsToLive"></a>
The number of conversation turns that the output context should remain active\. The number of turns is counted from the first time that the context is sent to the user\.  
Type: Integer  
Valid Range: Minimum value of 1\. Maximum value of 20\.  
Required: Yes

## See Also<a name="API_OutputContext_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [ AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/models.lex.v2-2020-08-07/OutputContext) 
+  [ AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/models.lex.v2-2020-08-07/OutputContext) 
+  [ AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/models.lex.v2-2020-08-07/OutputContext) 
+  [ AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/models.lex.v2-2020-08-07/OutputContext) 