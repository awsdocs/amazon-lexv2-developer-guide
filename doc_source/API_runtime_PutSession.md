# PutSession<a name="API_runtime_PutSession"></a>

Creates a new session or modifies an existing session with an Amazon Lex V2 bot\. Use this operation to enable your application to set the state of the bot\.

## Request Syntax<a name="API_runtime_PutSession_RequestSyntax"></a>

```
POST /bots/botId/botAliases/botAliasId/botLocales/localeId/sessions/sessionId HTTP/1.1
ResponseContentType: responseContentType
Content-type: application/json

{
   "messages": [ 
      { 
         "content": "string",
         "contentType": "string",
         "imageResponseCard": { 
            "buttons": [ 
               { 
                  "text": "string",
                  "value": "string"
               }
            ],
            "imageUrl": "string",
            "subtitle": "string",
            "title": "string"
         }
      }
   ],
   "requestAttributes": { 
      "string" : "string" 
   },
   "sessionState": { 
      "activeContexts": [ 
         { 
            "contextAttributes": { 
               "string" : "string" 
            },
            "name": "string",
            "timeToLive": { 
               "timeToLiveInSeconds": number,
               "turnsToLive": number
            }
         }
      ],
      "dialogAction": { 
         "slotToElicit": "string",
         "type": "string"
      },
      "intent": { 
         "confirmationState": "string",
         "name": "string",
         "slots": { 
            "string" : { 
               "shape": "string",
               "value": { 
                  "interpretedValue": "string",
                  "originalValue": "string",
                  "resolvedValues": [ "string" ]
               },
               "values": [ 
                  "Slot"
               ]
            }
         },
         "state": "string"
      },
      "originatingRequestId": "string",
      "sessionAttributes": { 
         "string" : "string" 
      }
   }
}
```

## URI Request Parameters<a name="API_runtime_PutSession_RequestParameters"></a>

The request uses the following URI parameters\.

 ** [botAliasId](#API_runtime_PutSession_RequestSyntax) **   <a name="lexv2-runtime_PutSession-request-botAliasId"></a>
The alias identifier of the bot that receives the session data\.  
Required: Yes

 ** [botId](#API_runtime_PutSession_RequestSyntax) **   <a name="lexv2-runtime_PutSession-request-botId"></a>
The identifier of the bot that receives the session data\.  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$`   
Required: Yes

 ** [localeId](#API_runtime_PutSession_RequestSyntax) **   <a name="lexv2-runtime_PutSession-request-localeId"></a>
The locale where the session is in use\.  
Length Constraints: Minimum length of 1\.  
Required: Yes

 ** [responseContentType](#API_runtime_PutSession_RequestSyntax) **   <a name="lexv2-runtime_PutSession-request-responseContentType"></a>
The message that Amazon Lex V2 returns in the response can be either text or speech depending on the value of this parameter\.   
+ If the value is `text/plain; charset=utf-8`, Amazon Lex V2 returns text in the response\.
Length Constraints: Minimum length of 1\.

 ** [sessionId](#API_runtime_PutSession_RequestSyntax) **   <a name="lexv2-runtime_PutSession-request-sessionId"></a>
The identifier of the session that receives the session data\.  
Length Constraints: Minimum length of 2\. Maximum length of 100\.  
Pattern: `[0-9a-zA-Z._:-]+`   
Required: Yes

## Request Body<a name="API_runtime_PutSession_RequestBody"></a>

The request accepts the following data in JSON format\.

 ** [messages](#API_runtime_PutSession_RequestSyntax) **   <a name="lexv2-runtime_PutSession-request-messages"></a>
A list of messages to send to the user\. Messages are sent in the order that they are defined in the list\.  
Type: Array of [Message](API_runtime_Message.md) objects  
Array Members: Maximum number of 10 items\.  
Required: No

 ** [requestAttributes](#API_runtime_PutSession_RequestSyntax) **   <a name="lexv2-runtime_PutSession-request-requestAttributes"></a>
Request\-specific information passed between Amazon Lex V2 and the client application\.  
The namespace `x-amz-lex:` is reserved for special attributes\. Don't create any request attributes with the prefix `x-amz-lex:`\.  
Type: String to string map  
Key Length Constraints: Minimum length of 1\.  
Required: No

 ** [sessionState](#API_runtime_PutSession_RequestSyntax) **   <a name="lexv2-runtime_PutSession-request-sessionState"></a>
Sets the state of the session with the user\. You can use this to set the current intent, attributes, context, and dialog action\. Use the dialog action to determine the next step that Amazon Lex V2 should use in the conversation with the user\.  
Type: [SessionState](API_runtime_SessionState.md) object  
Required: Yes

## Response Syntax<a name="API_runtime_PutSession_ResponseSyntax"></a>

```
HTTP/1.1 200
Content-Type: contentType
x-amz-lex-messages: messages
x-amz-lex-session-state: sessionState
x-amz-lex-request-attributes: requestAttributes
x-amz-lex-session-id: sessionId

audioStream
```

## Response Elements<a name="API_runtime_PutSession_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 200 response\.

The response returns the following HTTP headers\.

 ** [contentType](#API_runtime_PutSession_ResponseSyntax) **   <a name="lexv2-runtime_PutSession-response-contentType"></a>
The type of response\. Same as the type specified in the `responseContentType` field in the request\.  
Length Constraints: Minimum length of 1\.

 ** [messages](#API_runtime_PutSession_ResponseSyntax) **   <a name="lexv2-runtime_PutSession-response-messages"></a>
A list of messages that were last sent to the user\. The messages are ordered based on how you return the messages from you Lambda function or the order that the messages are defined in the bot\.  
Length Constraints: Minimum length of 1\.

 ** [requestAttributes](#API_runtime_PutSession_ResponseSyntax) **   <a name="lexv2-runtime_PutSession-response-requestAttributes"></a>
Request\-specific information passed between the client application and Amazon Lex V2\. These are the same as the `requestAttribute` parameter in the call to the `PutSession` operation\.  
Length Constraints: Minimum length of 1\.

 ** [sessionId](#API_runtime_PutSession_ResponseSyntax) **   <a name="lexv2-runtime_PutSession-response-sessionId"></a>
The identifier of the session that received the data\.  
Length Constraints: Minimum length of 2\. Maximum length of 100\.  
Pattern: `[0-9a-zA-Z._:-]+` 

 ** [sessionState](#API_runtime_PutSession_ResponseSyntax) **   <a name="lexv2-runtime_PutSession-response-sessionState"></a>
Represents the current state of the dialog between the user and the bot\.  
Use this to determine the progress of the conversation and what the next action may be\.  
Length Constraints: Minimum length of 1\.

The response returns the following as the HTTP body\.

 ** [audioStream](#API_runtime_PutSession_ResponseSyntax) **   <a name="lexv2-runtime_PutSession-response-audioStream"></a>
If the requested content type was audio, the audio version of the message to convey to the user\.

## Errors<a name="API_runtime_PutSession_Errors"></a>

For information about the errors that are common to all actions, see [Common Errors](CommonErrors.md)\.

 **AccessDeniedException**   
  
HTTP Status Code: 403

 **BadGatewayException**   
  
HTTP Status Code: 502

 **ConflictException**   
  
HTTP Status Code: 409

 **DependencyFailedException**   
  
HTTP Status Code: 424

 **InternalServerException**   
  
HTTP Status Code: 500

 **ResourceNotFoundException**   
  
HTTP Status Code: 404

 **ThrottlingException**   
  
HTTP Status Code: 429

 **ValidationException**   
  
HTTP Status Code: 400

## See Also<a name="API_runtime_PutSession_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [ AWS Command Line Interface](https://docs.aws.amazon.com/goto/aws-cli/runtime.lex.v2-2020-08-07/PutSession) 
+  [ AWS SDK for \.NET](https://docs.aws.amazon.com/goto/DotNetSDKV3/runtime.lex.v2-2020-08-07/PutSession) 
+  [ AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/runtime.lex.v2-2020-08-07/PutSession) 
+  [ AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/runtime.lex.v2-2020-08-07/PutSession) 
+  [ AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/runtime.lex.v2-2020-08-07/PutSession) 
+  [ AWS SDK for JavaScript](https://docs.aws.amazon.com/goto/AWSJavaScriptSDK/runtime.lex.v2-2020-08-07/PutSession) 
+  [ AWS SDK for PHP V3](https://docs.aws.amazon.com/goto/SdkForPHPV3/runtime.lex.v2-2020-08-07/PutSession) 
+  [ AWS SDK for Python](https://docs.aws.amazon.com/goto/boto3/runtime.lex.v2-2020-08-07/PutSession) 
+  [ AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/runtime.lex.v2-2020-08-07/PutSession) 