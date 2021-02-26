# Amazon Lex V1 to V2 migration guide<a name="migration"></a>

The Amazon Lex V2 console and APIs make it easier to build and manage bots\. Use this guide to learn about the improvements in the Amazon Lex V2 API as you migrate bots\.

## Amazon Lex V2 overview<a name="migration-improvements"></a>

Multiple languages can be added to a bot so you can manage them as a single resource\. A simplified information architecture lets you efficiently manage your bot versions\. Capabilities such as a 'conversation flow', partial saving of bot configuration and bulk upload of utterances give you more flexibility\.

### Multiple languages in a bot<a name="migration-languages"></a>

You can add multiple languages with the Amazon Lex V2 API\. You add, modify, and build each language independently\. Resources such as slot types are scoped at the language level\. You can quickly move between different languages to compare and refine the conversations\. You can use one dashboard in the console to review utterances for all languages for faster analysis and iterations\. A bot operator can manage permissions and logging operations for all languages with one bot configuration\. You must provide a language as a runtime parameter to converse with a Amazon Lex V2 bot\. For more information, see [Languages and locales supported by Amazon Lex](how-languages.md)\.

### Simplified information architecture<a name="migration-isolated"></a>

The Amazon Lex V2 API follows a simplified information architecture \(IA\) with intent and slot types scoped to a language\. You version at the bot level so that resources such as intents and slot types aren't versioned individually\. By default, a bot is created with a *Draft* version that is mutable and used for testing changes\. You can create numbered snapshots from the draft version\. You choose the languages to include in a version\. All resources within the bot \(languages, intents, slot types\) are archived as part of creating a bot version\. For more information, see [Creating versions](versions.md)\.

### Improved builder productivity<a name="migration-other"></a>

You have additional builder productivity tools and capabilities that give you more flexibility and control of your bot design process\.

#### Save partial configuration<a name="other-partial"></a>

The Amazon Lex V2 API enables you to save partial changes during development\. For example, you can save a slot that references a deleted slot type\. This flexibility enables you to save your work and return to it later\. You can resolve these changes before building the bot\. In Amazon Lex the partial save can be applied to slots, versions, and aliases\.

#### Renaming resources<a name="other-rename"></a>

With Amazon Lex V2 you can rename a resource after it's created\. Use a resource name to associate user\-friendly metadata with each resource\. The Amazon Lex V2 API assigns every resource a unique 10\-character resource ID\. All resources have a resource name\. You can rename the following resources:
+ Bot
+ Intent
+ Slot type
+ Slot
+ Alias

You can use resource IDs to read and modify your resources\. If you are using the AWS Command Line Interface or the Amazon Lex V2 API to work with Amazon Lex, resource IDs are required for certain commands\.

#### Simplified management of Lambda functions<a name="other-lambda"></a>

In the Amazon Lex V2 API you define one Lambda function per language instead of a function for each intent\. The Lambda function is configured in the alias for the language and is used for both the dialog and fulfillment code hook\. You can still choose to enable or disable the dialog and fulfillment code hooks independently for each intent\. For more information, see [Using a AWS Lambda function](lambda.md)\.

#### Granular settings<a name="other-settings"></a>

The Amazon Lex V2 API moves the voice and intent classification confidence score threshold from the bot to the language scope\. The sentiment analysis flag moves from bot scope to alias scope\. Session time out and privacy settings at the bot scope, and conversation logs at the alias scope, remain unchanged\.

#### Default fallback intent<a name="other-fallback"></a>

The Amazon Lex V2 API adds a default fallback intent when you create a language\. Use it to configure error handling for your bot instead of specific error\-handling prompts\.

#### Optimized session variable update<a name="other-variables"></a>

With the Amazon Lex V2 API you can update session state directly with the [RecognizeText](API_runtime_RecognizeText.md) and [RecognizeUtterance](API_runtime_RecognizeUtterance.md) operations without any dependency on session APIs\.

## How to migrate a bot<a name="migrate"></a>

The Amazon Lex V2 API uses an updated information architecture that enables simplified resource versioning and support for multiple languages in a bot\. To use these new features, you need to recreate your bot with Amazon Lex V2\.

You create a new bot that duplicates the functionality of your existing bot using the console or by using the Amazon Lex V2 API\.

### Step 1 – Create a new bot using the Amazon Lex V2 console<a name="migrate-step-1"></a>

From the Amazon Lex V1 console, choose the bot that you want to migrate\. Choose **Settings**, and then choose **General\.**

![\[The portion of the bot configuration section of the Amazon Lex V2 Amazon Lex V1 console.\]](http://docs.aws.amazon.com/lexv2/latest/dg/images/migration-bot-config-v1.png)

In the Amazon Lex V2 console, choose **Create bot**\. Transfer the settings from the Amazon Lex V2 console to the Amazon Lex V2 console\. For more information, see [Creating a bot](build-create.md)\.

![\[The bot configuration section of the Amazon Lex V2 console.\]](http://docs.aws.amazon.com/lexv2/latest/dg/images/migration-bot-config-v2.png)

### Step 2 – Add languages<a name="migrate-step-2"></a>

The Amazon Lex V2 API supports multiple languages in a single bot\. You can consolidate languages that were in multiple bots into one bot in Amazon Lex V2\. You can find the language information for your Amazon Lex V1 bots by choosing **Settings** and then choosing **General**\. 

![\[The Amazon Lex V1 console showing the location of the language setting for a bot.\]](http://docs.aws.amazon.com/lexv2/latest/dg/images/migration-language-v1.png)

The Amazon Lex V2 console prompts you to add a language to your bot\. You can add multiple languages now, or you can add additional languages after you create the bot\. Choose the language from the dropdown in the console\.

Amazon Lex V2 moves the confidence score settings from the bot to the language, so if you are using confidence scores set them here\.

For more information, see [Adding a language](build-language.md)\.

![\[The Amazon Lex V2 console showing the details of a language.\]](http://docs.aws.amazon.com/lexv2/latest/dg/images/migration-language-details.png)

### Step 3 – Create intents in your new bot<a name="migrate-step-3"></a>

In the Amazon Lex V1 console, open the editor to see the intents for the bot\. In the console, choose **Editor**, and then choose an intent from the left menu\.

![\[The Amazon Lex V1 console showing the details of an intent.\]](http://docs.aws.amazon.com/lexv2/latest/dg/images/migration-intent-create.png)

You now add intents to your bot\. For each language, create the intents in that language\. For more information, see [Adding intents](build-intents.md)\.

![\[The Amazon Lex V2 console showing the details of an intent.\]](http://docs.aws.amazon.com/lexv2/latest/dg/images/migration-intent-details.png)

### Step 4 – Add sample utterances to the intents<a name="migrate-step-4"></a>

After the intents are created, copy the sample utterances to the new intents\. The sample utterances used to train intents for Amazon Lex V1 and Amazon Lex V2 are the same\. You can copy the sample utterances from your existing bot to the new one\.

From the Amazon Lex V1 console, copy a sample utterance\.

![\[The Amazon Lex V1 console showing utterances.\]](http://docs.aws.amazon.com/lexv2/latest/dg/images/migration-utterances-v1.png)

In the Amazon Lex V2 **Intent editor**, scroll to the **Sample utterances** section\. Paste the sample utterance into the new intent\.

![\[The Amazon Lex V2 console showing utterances.\]](http://docs.aws.amazon.com/lexv2/latest/dg/images/migration-utterances-v2.png)

### Step 5 – Create slot types<a name="migrate-step-5"></a>

Next, create the slot types that you need for each language and copy the slot type values\.

For more information about creating custom slot types, see [Adding slot types](build-slot-types.md)\.

From the left menu, choose the slot that to migrate\. Copy the information from the existing slot type\.

![\[The Amazon Lex V1 console showing the slot type editor.\]](http://docs.aws.amazon.com/lexv2/latest/dg/images/migration-slot-type-v1.png)

Open the Amazon Lex V2 slot type editor by choosing ** Slot types ** from the left menu\. Choose **Add slot type** and then add the slot type details\.

![\[The Amazon Lex V2 console showing the slot type editor.\]](http://docs.aws.amazon.com/lexv2/latest/dg/images/migration-slot-type-v2.png)

### Step 6 – Create slots<a name="migrate-step-6"></a>

Next, create slots in the intents and configure the slot elicitation prompts\. Select a slot type from the dropdown\. 

If you're using a built\-in slot type, Amazon Lex V2 supports a curated list of built\-in slot types\. For more information about built\-in slot types, see [Built\-in slot types](howitworks-builtins-slots.md)\.

In the Amazon Lex V1 console, copy the name, slot type, and prompt for each slot in the intent\.

![\[Using the Amazon Lex V1 console to configure slots.\]](http://docs.aws.amazon.com/lexv2/latest/dg/images/migration-slot-add-v1.png)

In the Amazon Lex V2 console, choose the intent to add the slots to and then scroll to the **Slots** section of the intent editor\. Add the information that you copied from the Amazon Lex V1 bot\.

![\[Using the Amazon Lex V2 console to configure slots.\]](http://docs.aws.amazon.com/lexv2/latest/dg/images/migration-slot-add-v2.png)

### Step 7 – Configure closing responses<a name="migrate-step-7"></a>

You can create optional confirmation and closing responses for your bot\. The responses are the same for both Amazon Lex V1 and Amazon Lex V2\.

In the intent editor, copy the contents of the **Confirmation prompt** and **Response** sections\.

![\[Using the Amazon Lex V1 console to add confirmation and closing responses to a bot.\]](http://docs.aws.amazon.com/lexv2/latest/dg/images/migration-closing-v1.png)

Add the responses to the intent\. Add the confirmation prompts to the **Confirmation and declination prompts** section\. Add the closing responses to the **Closing responses** section\.

![\[Using the Amazon Lex V2 console to add confirmation and closing responses to a bot.\]](http://docs.aws.amazon.com/lexv2/latest/dg/images/migration-closing-v2.png)

### Step 8 – Configure the fallback intent for each language<a name="migrate-step-8"></a>

Amazon Lex V2 adds a fallback intent for each language\. The fallback intent is used when Amazon Lex V2 doesn't understand user input\. You can copy the clarification prompts from an Amazon Lex V1 bot for the fallback intent responses\.

For more information about the fallback intent, see [AMAZON\.FallbackIntent](built-in-intent-fallback.md)\.

In the Amazon Lex V1 console, choose the bot's fallback intent from the list of intents\. Copy the prompts from the intent\.

![\[The Amazon Lex V1 console showing the intent editor for the fallback intent.\]](http://docs.aws.amazon.com/lexv2/latest/dg/images/migration-fallback-v1.png)

To configure the fallback intent in the Amazon Lex V2 console, choose it from the list of intents\. 

![\[The Amazon Lex V2 console showing the intent editor for the fallback intent.\]](http://docs.aws.amazon.com/lexv2/latest/dg/images/migration-fallback-v2.png)

### Step 9 – Create and configure Lambda functions for validation and fulfillment<a name="migrate-step-9"></a>

In Amazon Lex V2, AWS Lambda functions are scoped to a specific locale within an alias\. You can use the Lambda function for slot validation and intent fulfillment\. All intents in a locale use the same Lambda function\. In Amazon Lex V1, a Lambda function was scoped to a specific intent\. The business logic for the Lambda function remain the same, the request and response parameters for the Lambda function are different\.

For more information about using Lambda functions with Amazon Lex V2, see [Using a AWS Lambda function](lambda.md)\.

Enable Lambda function code hooks for each intent that uses the Lambda function\. From the left menu, choose **Intents** and then scroll to the **Code hooks** section\. Choose whether to use a initialization and validation code hook, a fulfillment code hook, or both\.

![\[The Amazon Lex V2 console showing the choices for intent code hooks.\]](http://docs.aws.amazon.com/lexv2/latest/dg/images/migration-code-hook.png)

After you have enabled code hooks for an intent, you specify the Lambda function in the alias for the bot\. From the left menu, choose **Aliases**, then choose an alias\. For testing, you can use the `TestBotAlias` alias\.

From the alias editor, in the **Languages** section, choose the language for the Lambda function\. Choose the Lambda function and version then save the changes\.

![\[The Amazon Lex V2 console showing the Lambda function chooser for an alias.\]](http://docs.aws.amazon.com/lexv2/latest/dg/images/migration-code-hook-lambda.png)

### Step 10 – Build and test your bot<a name="migrate-step-10"></a>

You build and test each language supported by your bot separately\. From the left menu, choose that language that you want to build\. From the language editor, choose the language to build, then choose **Build**\.

![\[The Amazon Lex V2 console showing the build and test choices in the alias editor.\]](http://docs.aws.amazon.com/lexv2/latest/dg/images/migration-alias-build.png)

After the language builds, you can choose **Test** to open a test window that you can use to interact with your bot\.

![\[The Amazon Lex V2 console showing the test window for a bot.\]](http://docs.aws.amazon.com/lexv2/latest/dg/images/migration-bot-test.png)