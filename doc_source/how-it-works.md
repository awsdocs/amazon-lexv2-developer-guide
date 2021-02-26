# How it works<a name="how-it-works"></a>

Amazon Lex enables you to build applications using a text or speech interface for a conversation with a user\. Following are the typical steps for working with Amazon Lex:

1. Create a bot and add one or more languages\. Configure the bot so that it understands the user's goal, engages in conversation with the user to elicit information, and fulfills the user's intent\.

1. Test the bot\. You can use the test window client provided by the Amazon Lex console\.

1. Publish a version and create an alias\.

1. Deploy the bot\. You can deploy the bot on your own applications or messaging platforms such as Facebook Messenger or Slack

Before you get started, familiarize yourself with the following Amazon Lex core concepts and terminology:
+ **Bot** – A bot performs automated tasks such as ordering a pizza, booking a hotel, ordering flowers, and so on\. An Amazon Lex bot is powered by automatic speech recognition \(ASR\) and natural language understanding \(NLU\) capabilities\.

  Amazon Lex bots can understand user input provided with text or speech and converse natural language\.
+ **Language** – An Amazon Lex bot can converse in one or more languages\. Each language is independent of the others, you can configure Amazon Lex to converse with a user using native words and phrases\. For more information, see [Languages and locales supported by Amazon Lex](how-languages.md)\.
+ **Intent** – An intent represents an action that the user wants to perform\. You create a bot to support one or more related intents\. For example, you might create an intent that orders pizzas and drinks\. For each intent, you provide the following required information:
  + **Intent name** – A descriptive name for the intent\. For example, **OrderPizza**\.
  + **Sample utterances** – How a user might convey the intent\. For example, a user might say "Can I order a pizza" or "I want to order a pizza\."
  + **How to fulfill the intent** – How you want to fulfill the intent after the user provides the necessary information\. We recommend that you create a Lambda function to fulfill the intent\.

    You can optionally configure the intent so Amazon Lex returns the information back to the client application for the necessary fulfillment\.

  In addition to custom intents, Amazon Lex provides built\-in intents to quickly set up your bot\. For more information, see [Built\-in intents and slot types](built-in.md)\.

  Amazon Lex always includes a fallback intent for each bot\. The fallback intent is used whenever Amazon Lex can't deduce the user's intent\. For more information, see [AMAZON\.FallbackIntent](built-in-intent-fallback.md)\.
+ **Slot** – An intent can require zero or more slots, or parameters\. You add slots as part of the intent configuration\. At runtime, Amazon Lex prompts the user for specific slot values\. The user must provide values for all required slots before Amazon Lex can fulfill the intent\.

  For example the `OrderPizza` intent requires slots such as size, crust type, and number of pizzas\. For each slot, you provide the slot type and one or more prompts that Amazon Lex sends to the client to elicit values from the user\. A user can reply with a slot value that contains additional words, such as "large pizza please" or "let's stick with small\." Amazon Lex still understands the slot value\.
+ **Slot type** – Each slot has a type\. You can create your own slot type, or you can use built\-in slot types\. For example, you might create and use the following slot types for the `OrderPizza` intent:
  + Size – With enumeration values `Small`, `Medium`, and `Large`\.
  + Crust – With enumeration values `Thick` and `Thin`\.

  Amazon Lex also provides built\-in slot types\. For example, `AMAZON.Number` is a built\-in slot type that you can use for the number of pizzas ordered\. For more information, see [Built\-in intents and slot types](built-in.md)\.
+ **Version** – A version is a numbered snapshot of your work that you can publish for use in different parts of your workflow, such as development, beta deployment, and production\. Once you create a version, you can use a bot as it existed when the version was made\. After you create a version, it stays the same while you continue to work on your application\.
+ **Alias** – An alias is a pointer to a specific version of a bot\. With an alias, you can update the version the your client applications are using\. For example, you can point an alias to version 1 of your bot\. When you are ready to update the bot, you publish version 2 and change the alias to point to the new version\. Because your applications use the alias instead of a specific version, all of your clients get the new functionality without needing to be updated\.

For a list of the AWS Regions where Amazon Lex is available, see [ AWS Regions and endpoints ](https://docs.aws.amazon.com/latest/gr/rande.html#lex_region) in the *Amazon Web Services General Reference*\.