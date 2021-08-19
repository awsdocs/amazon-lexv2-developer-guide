# Amazon Lex V1 to V2 migration guide<a name="migration"></a>

The Amazon Lex V2 console and APIs make it easier to build and manage bots\. Use this guide to learn about the improvements in the Amazon Lex V2 API as you migrate bots\.

You migrate a bot using the Amazon Lex console or API\. For more information see [ Migrating a bot ](https://docs.aws.amazon.com/lex/latest/dg/migrate.html) in the *Amazon Lex developer guide*\.

## Amazon Lex V2 overview<a name="migration-improvements"></a>

Multiple languages can be added to a bot so you can manage them as a single resource\. A simplified information architecture lets you efficiently manage your bot versions\. Capabilities such as a 'conversation flow', partial saving of bot configuration and bulk upload of utterances give you more flexibility\.

### Multiple languages in a bot<a name="migration-languages"></a>

You can add multiple languages with the Amazon Lex V2 API\. You add, modify, and build each language independently\. Resources such as slot types are scoped at the language level\. You can quickly move between different languages to compare and refine the conversations\. You can use one dashboard in the console to review utterances for all languages for faster analysis and iterations\. A bot operator can manage permissions and logging operations for all languages with one bot configuration\. You must provide a language as a runtime parameter to converse with a Amazon Lex V2 bot\. For more information, see [Languages and locales supported by Amazon Lex V2](how-languages.md)\.

### Simplified information architecture<a name="migration-isolated"></a>

The Amazon Lex V2 API follows a simplified information architecture \(IA\) with intent and slot types scoped to a language\. You version at the bot level so that resources such as intents and slot types aren't versioned individually\. By default, a bot is created with a *Draft* version that is mutable and used for testing changes\. You can create numbered snapshots from the draft version\. You choose the languages to include in a version\. All resources within the bot \(languages, intents, slot types\) are archived as part of creating a bot version\. For more information, see [Creating versions](versions.md)\.

### Improved builder productivity<a name="migration-other"></a>

You have additional builder productivity tools and capabilities that give you more flexibility and control of your bot design process\.

#### Save partial configuration<a name="other-partial"></a>

The Amazon Lex V2 API enables you to save partial changes during development\. For example, you can save a slot that references a deleted slot type\. This flexibility enables you to save your work and return to it later\. You can resolve these changes before building the bot\. In Amazon Lex V2 the partial save can be applied to slots, versions, and aliases\.

#### Renaming resources<a name="other-rename"></a>

With Amazon Lex V2 you can rename a resource after it's created\. Use a resource name to associate user\-friendly metadata with each resource\. The Amazon Lex V2 API assigns every resource a unique 10\-character resource ID\. All resources have a resource name\. You can rename the following resources:
+ Bot
+ Intent
+ Slot type
+ Slot
+ Alias

You can use resource IDs to read and modify your resources\. If you are using the AWS Command Line Interface or the Amazon Lex V2 API to work with Amazon Lex V2, resource IDs are required for certain commands\.

#### Simplified management of Lambda functions<a name="other-lambda"></a>

In the Amazon Lex V2 API you define one Lambda function per language instead of a function for each intent\. The Lambda function is configured in the alias for the language and is used for both the dialog and fulfillment code hook\. You can still choose to enable or disable the dialog and fulfillment code hooks independently for each intent\. For more information, see [Using an AWS Lambda function](lambda.md)\.

#### Granular settings<a name="other-settings"></a>

The Amazon Lex V2 API moves the voice and intent classification confidence score threshold from the bot to the language scope\. The sentiment analysis flag moves from bot scope to alias scope\. Session time out and privacy settings at the bot scope, and conversation logs at the alias scope, remain unchanged\.

#### Default fallback intent<a name="other-fallback"></a>

The Amazon Lex V2 API adds a default fallback intent when you create a language\. Use it to configure error handling for your bot instead of specific error\-handling prompts\.

#### Optimized session variable update<a name="other-variables"></a>

With the Amazon Lex V2 API you can update session state directly with the [RecognizeText](API_runtime_RecognizeText.md) and [RecognizeUtterance](API_runtime_RecognizeUtterance.md) operations without any dependency on session APIs\.