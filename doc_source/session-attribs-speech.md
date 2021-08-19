# Configuring timeouts for capturing user input<a name="session-attribs-speech"></a>

The Amazon Lex V2 streaming API enables a bot to automatically detect utterances in user input\. When you create an intent or a slot, you can configure aspects of an utterance, such as maximum duration of an utterance, timeout while waiting for user input, or the end character for DTMF input\. This enables you to customize a bot's behavior for your use case\. For example, you can limit the number of digits for a credit card number to 16\.

You can also configure timeouts through session attributes when starting a conversation with a bot, and overwrite them in your Lambda function if necessary\.

The configuration keys for an attribute use the following syntax:

```
x-amz-lex:<InputType>:<BehaviorName>:<IntentName>:<SlotName>
```

`InputType` can be **audio**, **dtmf**, or **text**\.

You can configure default settings for all intents or slots in a bot by specifying **\*** as the intent or slot name\. Any intent\- or slot\-specific settings take precedence over default settings\.

Amazon Lex V2 provides predefined session attributes for managing the way the [StartConversation](API_runtime_StartConversation.md) operations works with text, voice, or DTMF input to your bot\. All predefined attributes are in the `x-amz-lex` namespace\.

**Topics**
+ [Timeouts for voice input](#voice-input-time-out)
+ [Timeouts for text input](#text-input-attribs)
+ [Configuration for DTMF input](#session-attribs-dtmf)

## Timeouts for voice input<a name="voice-input-time-out"></a>

You can set time\-out values for voice interaction with your bot using session attributes\. The attributes are defined by Amazon Lex V2\. These attributes enable you to specify how long Amazon Lex V2 waits for a customer to finish speaking before collecting input speech\.

All of these attributes are in the `x-amz-lex:audio` namespace\.

### Maximum utterance length<a name="max-utterance-length"></a>

```
x-amz-lex:audio:max-length-ms:<intentName>:<slotName>
```

Defines how long Amazon Lex V2 waits before speech input is truncated and the speech is returned to your application\. You can increase the length of the input when you expect long responses, or if you want to give customers more time to provide information\.

**Default:** 13000 milliseconds \(13 seconds\)\. The maximum value is 15000 milliseconds \(15 seconds\)

If you set the `max-length-ms` attribute to more than 150000 milliseconds, an error is returned\.

### Voice timeout<a name="voice-timeout"></a>

```
x-amz-lex:audio:start-timeout-ms:<intentName>:<slotName>
```

How long a bot waits before assuming that the customer isn't going to speak\. You can increase the time in situations where the customer may need more time to find or recall information before speaking\. For example, you might want to give customers time to get out their credit card so they can enter the number\.

**Default:** 4000 milliseconds \(0\.4 seconds\)

### Silence timeout<a name="silence-timeout"></a>

```
x-amz-lex:audio:end-timeout-ms:<intentName>:<slotName>
```

How long a bot waits after the customer stops speaking to assume the utterance is finished\. You can increase the time in situations where periods of silence are expected while providing input\.

**Default:** 6000 milliseconds \(0\.6 seconds\)

## Timeouts for text input<a name="text-input-attribs"></a>

Use the following session attribute to specify how your bot behaves with the text conversation mode\.

This attribute is in the `x-amz-lex:text` namespace\.

### Start timeout threshold<a name="start-timeout-threshold"></a>

```
x-amz-lex:text:start-timeout-ms:<intentName>:<slotName>
```

How long the bot waits before re\-prompting a customer for text input\. You can increase the time in situations where you’d like to allow the customer more time to find or recall information before providing text input\. For example, you might want to give customers more time to find details on their order\. Alternatively, you may reduce the threshold to prompt customers earlier\.

**Default:** 30000 milliseconds \(30 seconds\)

## Configuration for DTMF input<a name="session-attribs-dtmf"></a>

Use the following session attributes to specify how your Amazon Lex V2 bot responds to DTMF input when using an audio conversation\.

All of these attributes are in the `x-amz-lex:dtmf` namespace\.

### Deletion character<a name="deletion-character"></a>

```
x-amz-lex:dtmf:deletion-character:<intentName>:<slotName>
```

The DTMF character that clears the accumulated DTMF digits and immediately ends the input\.

**Default:** \*

### End character<a name="end-character"></a>

```
x-amz-lex:dtmf:end-character:<intentName>:<slotName>
```

The DTMF character that immediately ends input\. If the user does not press this character, the input ends after the end timeout\.

**Default:** \#

### End timeout<a name="end-timeout"></a>

```
x-amz-lex:dtmf:end-timeout-ms:<intentName>:<slotName>
```

How long the bot should wait from the last DTMF character input before assuming that the input has concluded\.

**Default:** 5000 milliseconds \(5 seconds\)

### Maximum number of DTMF digits per utterance<a name="max-length"></a>

```
x-amz-lex:dtmf:max-length:<intentName>:<slotName>
```

The maximum number of DTMF digits allowed in an utterance\. For example, you could set this value to 16 to limit the number of characters that can be input for a credit card number\. This value can't be increased\.

**Default:** 1024 characters