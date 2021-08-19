# Guidelines and quotas<a name="quotas"></a>

**Topics**
+ [Regions](#regions)
+ [General guidelines](#guidelines)
+ [Quotas](#quotas-service)

## Regions<a name="regions"></a>

For a list of AWS Regions where Amazon Lex V2 is available, see [ AWS regions and endpoints ](https://docs.aws.amazon.com/general/latest/gr/lex.html) in the *AWS general reference*\.

## General guidelines<a name="guidelines"></a>

This topic describes general guidelines when using Amazon Lex V2\.
+ **Signing requests** – All Amazon Lex V2 model\-building and runtime requests in the [API reference](API_Reference.md) use signature V4 for authenticating requests\. For more information about authenticating requests, see [ Signature Version 4 signing process ](https://docs.aws.amazon.com/general/latest/gr/signature-version-4.html) in the *Amazon Web Services general reference*\.
+ Note the following about how Amazon Lex V2 captures slot values from user utterances:

  Amazon Lex V2 uses the enumeration values that you provide in a slot type definition to train its machine learning models\. Suppose that you define an intent called `GetPredictionIntent` with the following sample utterance:

  ```
  "Tell me the prediction for {sign}"
  ```

  where \{sign\} is a slot with the custom type `ZodiacSign`\. It has 12 enumeration values, `Aries` through `Pisces`\. From the user utterance "Tell me the prediction for \.\.\." Amazon Lex V2 understands that the following is a zodiac sign\.

  When the `valueSelectionStrategy` field is set to `OriginalValue` using the [CreateSlotType](API_CreateSlotType.md) operation, or if **Expand values** is selected in the console, if the user says "Tell me the prediction for earth", Amazon Lex V2 infers that "earth" is a `ZodiacSign` value and passes it to your client application or Lambda function\. You must check that slot values are valid values before using them in your fulfillment activity\.

  If you set the `valueSelectionStrategy` field to `TopResolution` using the `CreateSlotType` operation or if **Restrict to slot values and synonyms** is selected in the console, the values that are returned are limited to the values that you defined for the slot type\. For example, if the user says "Tell me the prediction for earth", the value would not be recognized because it is not one of the values defined for the slot type\. When you define synonyms for slot values, they are recognized the same as a slot value, however, the slot value is returned instead of the synonym\.

  When Amazon Lex V2 calls a Lambda function or returns the result of a speech interaction with your client, the case of the slot values is not guaranteed\. In text interactions, the case of the slot values matches the text entered or the slot value, depending on the value of the `valueResolutionStrategy` field\.
+ When defining slot values that contain acronyms, use the following patterns:
  + Capital letters separated by periods \(D\.V\.D\.\)
  + Capital letters separated by spaces \(D V D\)
+ The [AMAZON\.Date](built-in-slot-date.md) and [AMAZON\.Time](built-in-slot-time.md) built\-on slot types capture both absolute and relative dates and times\. Relative dates and times are resolved in the region where Amazon Lex V2 is processing the request\.

  For the `AMAZON.Time` built\-in slot type, if the user doesn't specify that a time is before or after noon, the time is ambiguous and Amazon Lex V2 will prompt the user again\. We recommend prompts that elicit an absolute time\. For example, use a prompt such as "When do you want your pizza delivered? You can say 6 PM or 6 in the evening\."
+ Providing confusable training data in your bot reduces the ability of Amazon Lex V2 to understand user input\. Consider these examples:

  Suppose you have two intents \(`OrderPizza` and `OrderDrink`\) in your bot and both are configured with an "I want to order" utterance\. This utterance does not map to a specific intent that Amazon Lex V2 can learn from while building the language model for the bot at build time\. As a result, when a user inputs this utterance at runtime, Amazon Lex V2 can't pick an intent with a high degree of confidence\.

  When you have two intents with the same utterance, use input contexts to help Amazon Lex distinguish between the two intents at runtime\. For more information, see [ Setting intent context ](https://docs.aws.amazon.com/lexv2/latest/dg/context-mgmt-active-context.html)\.
+ When you use the TSTALIASID alias, keep in mind the following:
  + The TSTALIASID alias of your bot points to the Draft version and should only be used for manual testing\. Amazon Lex limits the number of runtime requests that you can make to the TSTALIASID alias of the bot\.
  + When you update the Draft version of the bot, Amazon Lex terminates any in\-progress conversations for any client application using the TSTALIASID alias of the bot\. Generally, you should not use the TSTALIASID alias of a bot in production because the Draft version can be updated\. You should publish a version and an alias and use them instead\.
  + When you update an alias, Amazon Lex takes a few minutes to pick up the changes\. When you modify the Draft version of the bot, the change is picked up by the TSTALIASID alias immediately\.
+ The runtime API operations [RecognizeText](API_runtime_RecognizeText.md) and [RecognizeUtterance](API_runtime_RecognizeUtterance.md) take a session ID as a required parameter\. Developers can set this to any value that meets the constraints described in the API\. We recommend that you don't use this parameter to send any confidential information such as user logins, emails, or social security numbers\. This ID is primarily used to uniquely identify a conversation with a bot\.

## Quotas<a name="quotas-service"></a>

Service quotas, also referred to as limits, are the maximum number of service resources for you AWS account\. For more information, see [ AWS service quotas ](https://docs.aws.amazon.com/general/latest/gr/aws_service_limits.html) in the *AWS general reference*\.

Service quotas can be adjusted or increased\. Contact AWS customer support to increase a quota\. It can take a few days to increase a service quota\. If you're increasing your quota as part of a larger project, be sure to add this time to your plan\.

### Build\-time quotas<a name="quota-build-time"></a>

The following maximum quotas are enforced when you are creating a bot\.


| Description | Default | 
| --- | --- | 
| Bots per AWS account | 100 | 
| Bot channel associations per AWS account | 5,000 | 
| Versions per bot | 100 | 
| Intents per locale in each bot |  [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/lexv2/latest/dg/quotas.html) | 
| Slots per locale in each bot | [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/lexv2/latest/dg/quotas.html) | 
| Custom slot types per bot locale | [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/lexv2/latest/dg/quotas.html)  | 
| Custom slot type values and synonyms per locale in each bot | 50,000 | 
| Total characters in sample utterances per locale in each bot | [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/lexv2/latest/dg/quotas.html) | 
| Channel associations per bot alias | 10 | 
| Slots per intent | 100 | 
| Sample utterances per intent | 1,500 | 
| Characters per sample utterance | 500 | 
| Text response length | 4,000 | 
| Sample utterances per slot | 10 | 
| Characters per sample slot utterance | 500 | 
| Prompts per slot | 30 | 
| Values and synonyms per custom slot type | 10,000 | 
| Characters per custom slot type value | 500 | 
| Characters in a channel association name | 100 | 

### Runtime quotas<a name="quota-runtime"></a>

The following maximum quotas are enforced at runtime\.


| Description | Default | 
| --- | --- | 
| Input text size for [RecognizeText](API_runtime_RecognizeText.md) and [RecognizeUtterance](API_runtime_RecognizeUtterance.md) | 1024 Unicode characters | 
| Speech input length for RecognizeUtterance operation | 15 seconds | 
| Size of RecognizeUtterance headers | 16 KB | 
| Size of combined request and session headers for RecognizeUtterance | 12 KB | 
| Maximum number of concurrent conversations for RecognizeText, RecognizeUtterance, or StartConversation for the TestBotAlias | 2 | 
| Maximum number of concurrent conversations for RecognizeText, RecognizeUtterance, or StartConversation for other aliases | 25 | 
| Maximum number of concurrent session management operations \(PutSession, GetSession, or DeleteSession\) when using the TestBotAlias | 2 | 
| Maximum number of concurrent session management operations \(PutSession, GetSession, or DeleteSession\) when using other aliases | 25 | 
| Maximum input size to a Lambda function | 12 KB | 
| Maximum output size of a Lambda function | 25 KB | 
| Maximum size of session attributes in Lambda function output | 12 KB | 