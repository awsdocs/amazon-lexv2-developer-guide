# RecognizeUtterance<a name="API_runtime_RecognizeUtterance"></a>

Sends user input to Amazon Lex V2\. You can send text or speech\. Clients use this API to send text and audio requests to Amazon Lex V2 at runtime\. Amazon Lex V2 interprets the user input using the machine learning model built for the bot\.

The following request fields must be compressed with gzip and then base64 encoded before you send them to Amazon Lex V2\. 
+ requestAttributes
+ sessionState

The following response fields are compressed using gzip and then base64 encoded by Amazon Lex V2\. Before you can use these fields, you must decode and decompress them\. 
+ inputTranscript
+ interpretations
+ messages
+ requestAttributes
+ sessionState

The example contains a Java application that compresses and encodes a Java object to send to Amazon Lex V2, and a second that decodes and decompresses a response from Amazon Lex V2\.

## Request Syntax<a name="API_runtime_RecognizeUtterance_RequestSyntax"></a>

```
POST /bots/botId/botAliases/botAliasId/botLocales/localeId/sessions/sessionId/utterance HTTP/1.1
x-amz-lex-session-state: sessionState
x-amz-lex-request-attributes: requestAttributes
Content-Type: requestContentType
Response-Content-Type: responseContentType

inputStream
```

## URI Request Parameters<a name="API_runtime_RecognizeUtterance_RequestParameters"></a>

The request uses the following URI parameters\.

 ** [botAliasId](#API_runtime_RecognizeUtterance_RequestSyntax) **   <a name="lexv2-runtime_RecognizeUtterance-request-botAliasId"></a>
The alias identifier in use for the bot that should receive the request\.  
Required: Yes

 ** [botId](#API_runtime_RecognizeUtterance_RequestSyntax) **   <a name="lexv2-runtime_RecognizeUtterance-request-botId"></a>
The identifier of the bot that should receive the request\.  
Length Constraints: Fixed length of 10\.  
Pattern: `^[0-9a-zA-Z]+$`   
Required: Yes

 ** [localeId](#API_runtime_RecognizeUtterance_RequestSyntax) **   <a name="lexv2-runtime_RecognizeUtterance-request-localeId"></a>
The locale where the session is in use\.  
Length Constraints: Minimum length of 1\.  
Required: Yes

 ** [requestAttributes](#API_runtime_RecognizeUtterance_RequestSyntax) **   <a name="lexv2-runtime_RecognizeUtterance-request-requestAttributes"></a>
Request\-specific information passed between the client application and Amazon Lex V2   
The namespace `x-amz-lex:` is reserved for special attributes\. Don't create any request attributes for prefix `x-amz-lex:`\.  
The `requestAttributes` field must be compressed using gzip and then base64 encoded before sending to Amazon Lex V2\.

 ** [requestContentType](#API_runtime_RecognizeUtterance_RequestSyntax) **   <a name="lexv2-runtime_RecognizeUtterance-request-requestContentType"></a>
Indicates the format for audio input or that the content is text\. The header must start with one of the following prefixes:  
+ PCM format, audio data must be in little\-endian byte order\.
  + audio/l16; rate=16000; channels=1
  + audio/x\-l16; sample\-rate=16000; channel\-count=1
  + audio/lpcm; sample\-rate=8000; sample\-size\-bits=16; channel\-count=1; is\-big\-endian=false
+ Opus format
  + audio/x\-cbr\-opus\-with\-preamble;preamble\-size=0;bit\-rate=256000;frame\-size\-milliseconds=4
+ Text format
  + text/plain; charset=utf\-8
Length Constraints: Minimum length of 1\.  
Required: Yes

 ** [responseContentType](#API_runtime_RecognizeUtterance_RequestSyntax) **   <a name="lexv2-runtime_RecognizeUtterance-request-responseContentType"></a>
The message that Amazon Lex V2 returns in the response can be either text or speech based on the `responseContentType` value\.  
+ If the value is `text/plain;charset=utf-8`, Amazon Lex V2 returns text in the response\.
+ If the value begins with `audio/`, Amazon Lex V2 returns speech in the response\. Amazon Lex V2 uses Amazon Polly to generate the speech using the configuration that you specified in the `requestContentType` parameter\. For example, if you specify `audio/mpeg` as the value, Amazon Lex V2 returns speech in the MPEG format\.
+ If the value is `audio/pcm`, the speech returned is `audio/pcm` at 16 KHz in 16\-bit, little\-endian format\.
+ The following are the accepted values:
  + audio/mpeg
  + audio/ogg
  + audio/pcm \(16 KHz\)
  + audio/\* \(defaults to mpeg\)
  + text/plain; charset=utf\-8
Length Constraints: Minimum length of 1\.

 ** [sessionId](#API_runtime_RecognizeUtterance_RequestSyntax) **   <a name="lexv2-runtime_RecognizeUtterance-request-sessionId"></a>
The identifier of the session in use\.  
Length Constraints: Minimum length of 2\. Maximum length of 100\.  
Pattern: `[0-9a-zA-Z._:-]+`   
Required: Yes

 ** [sessionState](#API_runtime_RecognizeUtterance_RequestSyntax) **   <a name="lexv2-runtime_RecognizeUtterance-request-sessionState"></a>
Sets the state of the session with the user\. You can use this to set the current intent, attributes, context, and dialog action\. Use the dialog action to determine the next step that Amazon Lex V2 should use in the conversation with the user\.  
The `sessionState` field must be compressed using gzip and then base64 encoded before sending to Amazon Lex V2\.

## Request Body<a name="API_runtime_RecognizeUtterance_RequestBody"></a>

The request accepts the following binary data\.

 ** [inputStream](#API_runtime_RecognizeUtterance_RequestSyntax) **   <a name="lexv2-runtime_RecognizeUtterance-request-inputStream"></a>
User input in PCM or Opus audio format or text format as described in the `requestContentType` parameter\.

## Response Syntax<a name="API_runtime_RecognizeUtterance_ResponseSyntax"></a>

```
HTTP/1.1 200
x-amz-lex-input-mode: inputMode
Content-Type: contentType
x-amz-lex-messages: messages
x-amz-lex-interpretations: interpretations
x-amz-lex-session-state: sessionState
x-amz-lex-request-attributes: requestAttributes
x-amz-lex-session-id: sessionId
x-amz-lex-input-transcript: inputTranscript

audioStream
```

## Response Elements<a name="API_runtime_RecognizeUtterance_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 200 response\.

The response returns the following HTTP headers\.

 ** [contentType](#API_runtime_RecognizeUtterance_ResponseSyntax) **   <a name="lexv2-runtime_RecognizeUtterance-response-contentType"></a>
Content type as specified in the `responseContentType` in the request\.  
Length Constraints: Minimum length of 1\.

 ** [inputMode](#API_runtime_RecognizeUtterance_ResponseSyntax) **   <a name="lexv2-runtime_RecognizeUtterance-response-inputMode"></a>
Indicates whether the input mode to the operation was text or speech\.   
Length Constraints: Minimum length of 1\.

 ** [inputTranscript](#API_runtime_RecognizeUtterance_ResponseSyntax) **   <a name="lexv2-runtime_RecognizeUtterance-response-inputTranscript"></a>
The text used to process the request\.  
If the input was an audio stream, the `inputTranscript` field contains the text extracted from the audio stream\. This is the text that is actually processed to recognize intents and slot values\. You can use this information to determine if Amazon Lex V2 is correctly processing the audio that you send\.  
The `inputTranscript` field is compressed with gzip and then base64 encoded\. Before you can use the contents of the field, you must decode and decompress the contents\. See the example for a simple function to decode and decompress the contents\.  
Length Constraints: Minimum length of 1\.

 ** [interpretations](#API_runtime_RecognizeUtterance_ResponseSyntax) **   <a name="lexv2-runtime_RecognizeUtterance-response-interpretations"></a>
A list of intents that Amazon Lex V2 determined might satisfy the user's utterance\.  
Each interpretation includes the intent, a score that indicates how confident Amazon Lex V2 is that the interpretation is the correct one, and an optional sentiment response that indicates the sentiment expressed in the utterance\.  
The `interpretations` field is compressed with gzip and then base64 encoded\. Before you can use the contents of the field, you must decode and decompress the contents\. See the example for a simple function to decode and decompress the contents\.  
Length Constraints: Minimum length of 1\.

 ** [messages](#API_runtime_RecognizeUtterance_ResponseSyntax) **   <a name="lexv2-runtime_RecognizeUtterance-response-messages"></a>
A list of messages that were last sent to the user\. The messages are ordered based on the order that you returned the messages from your Lambda function or the order that the messages are defined in the bot\.  
The `messages` field is compressed with gzip and then base64 encoded\. Before you can use the contents of the field, you must decode and decompress the contents\. See the example for a simple function to decode and decompress the contents\.  
Length Constraints: Minimum length of 1\.

 ** [requestAttributes](#API_runtime_RecognizeUtterance_ResponseSyntax) **   <a name="lexv2-runtime_RecognizeUtterance-response-requestAttributes"></a>
The attributes sent in the request\.  
The `requestAttributes` field is compressed with gzip and then base64 encoded\. Before you can use the contents of the field, you must decode and decompress the contents\.  
Length Constraints: Minimum length of 1\.

 ** [sessionId](#API_runtime_RecognizeUtterance_ResponseSyntax) **   <a name="lexv2-runtime_RecognizeUtterance-response-sessionId"></a>
The identifier of the session in use\.  
Length Constraints: Minimum length of 2\. Maximum length of 100\.  
Pattern: `[0-9a-zA-Z._:-]+` 

 ** [sessionState](#API_runtime_RecognizeUtterance_ResponseSyntax) **   <a name="lexv2-runtime_RecognizeUtterance-response-sessionState"></a>
Represents the current state of the dialog between the user and the bot\.  
Use this to determine the progress of the conversation and what the next action might be\.  
The `sessionState` field is compressed with gzip and then base64 encoded\. Before you can use the contents of the field, you must decode and decompress the contents\. See the example for a simple function to decode and decompress the contents\.  
Length Constraints: Minimum length of 1\.

The response returns the following as the HTTP body\.

 ** [audioStream](#API_runtime_RecognizeUtterance_ResponseSyntax) **   <a name="lexv2-runtime_RecognizeUtterance-response-audioStream"></a>
The prompt or statement to send to the user\. This is based on the bot configuration and context\. For example, if Amazon Lex V2 did not understand the user intent, it sends the `clarificationPrompt` configured for the bot\. If the intent requires confirmation before taking the fulfillment action, it sends the `confirmationPrompt`\. Another example: Suppose that the Lambda function successfully fulfilled the intent, and sent a message to convey to the user\. Then Amazon Lex V2 sends that message in the response\.

## Errors<a name="API_runtime_RecognizeUtterance_Errors"></a>

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

## Examples<a name="API_runtime_RecognizeUtterance_Examples"></a>

### Encode and decode a field<a name="API_runtime_RecognizeUtterance_Example_1"></a>

The following example provides two functions, one to compress a string with gzip and then base64 encode it and one to decode and decompress a string\.

#### <a name="w233aac47b7b9c20c27b3b5"></a>

```
package com.amazonaws.deepsense.util;

import com.amazonaws.deepsense.runtime.conversation.serialize.RuntimeSdkSerializer;
import com.fasterxml.jackson.annotation.JsonInclude;
import com.fasterxml.jackson.core.JsonProcessingException;
import com.fasterxml.jackson.core.type.TypeReference;
import com.fasterxml.jackson.databind.DeserializationFeature;
import com.fasterxml.jackson.databind.ObjectMapper;
import com.fasterxml.jackson.databind.SerializationFeature;
import com.google.common.base.Preconditions;

import java.io.IOException;
import java.util.Base64;

public class CompressionAndEncoding {

    private CompressionAndEncoding() {

    }

    /**
     * Given a generic object
     * 1. Serialize the object using jackson
     * 2. Compress the serialized object
     * 3. Base64 encode the compressed data
     */
    public static String compressAndEncodeBase64(Object object) {
        if (object == null) {
            return null;
        }

        String objectAsString = GsonSerializer.serialize(object);
        byte[] compressedString = Compressions.compress(objectAsString);
        return Base64.getEncoder().encodeToString(compressedString);
    }

    /**
     * Given a base64 encoded, compressed, serialized object
     * 1. Base64 decodes the data
     * 2. Decompresses the base64 decoded data
     * 3. Converts the serialized object into a proper POJO
     */
    public static <T> T decodeBase64AndDecompress(String objectAsString, TypeReference<T> typeRef) {
        if (objectAsString == null) {
            return null;
        }

        Preconditions.checkNotNull(typeRef, "Serialization class can't be null.");
        byte[] decodedBytes = Base64.getDecoder().decode(objectAsString);
        String decompressedObjectAsString = Compressions.uncompress(decodedBytes);
        try {
            return RuntimeSdkSerializer.instance().readValue(decompressedObjectAsString, typeRef);
        } catch (IOException e) {
            throw new RuntimeException(String.format("Unable to deserialize string %s", decompressedObjectAsString), e);
        }
    }

}
```

## See Also<a name="API_runtime_RecognizeUtterance_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [ AWS Command Line Interface](https://docs.aws.amazon.com/goto/aws-cli/runtime.lex.v2-2020-08-07/RecognizeUtterance) 
+  [ AWS SDK for \.NET](https://docs.aws.amazon.com/goto/DotNetSDKV3/runtime.lex.v2-2020-08-07/RecognizeUtterance) 
+  [ AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/runtime.lex.v2-2020-08-07/RecognizeUtterance) 
+  [ AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/runtime.lex.v2-2020-08-07/RecognizeUtterance) 
+  [ AWS SDK for Java V2](https://docs.aws.amazon.com/goto/SdkForJavaV2/runtime.lex.v2-2020-08-07/RecognizeUtterance) 
+  [ AWS SDK for JavaScript](https://docs.aws.amazon.com/goto/AWSJavaScriptSDK/runtime.lex.v2-2020-08-07/RecognizeUtterance) 
+  [ AWS SDK for PHP V3](https://docs.aws.amazon.com/goto/SdkForPHPV3/runtime.lex.v2-2020-08-07/RecognizeUtterance) 
+  [ AWS SDK for Python](https://docs.aws.amazon.com/goto/boto3/runtime.lex.v2-2020-08-07/RecognizeUtterance) 
+  [ AWS SDK for Ruby V3](https://docs.aws.amazon.com/goto/SdkForRubyV3/runtime.lex.v2-2020-08-07/RecognizeUtterance) 