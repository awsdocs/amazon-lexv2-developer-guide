# Building bots<a name="building-bots"></a>

You create an Amazon Lex V2 bot to interact with your users to elicit information to accomplish a task\. For example, you can create a bot that gathers the information needed to order a bouquet of flowers or book a hotel room\.

To build a bot, you need the following information:

1. The language that the bot uses to interact with the customer\. You can choose one or more languages, each language contains independent intents, slots, and slot types\.

1. The intents, or goals, that the bot will help the user fulfill\. A bot can contain one or more intents, such as ordering flowers, or booking a hotel and rental car\. You need to decide which statements, or utterances, that the user makes to trigger the intent\.

1. The information, or slots, that you need to gather from the user to fulfill an intent\. For example, you might need to get the type of flowers from the user or the start date of a hotel reservation\. You need to define one or more prompts that Amazon Lex V2 uses to elicit the slot value from the user\.

1. The type of the slots that you need from the user\. You may need to create a custom slot type, such as a list of flowers that a user can order, or you can use a built\-in slot type, such as using the AMAZON\.Date slot type for the start date of a reservation\.

1. The interactions between user and intents\. Amazon Lex V2 manages the interactions; you can create an AWS Lambda function to validate and fulfill the intent\.

**Topics**
+ [Creating a bot](build-create.md)
+ [Adding a language](build-language.md)
+ [Adding intents](build-intents.md)
+ [Adding slot types](build-slot-types.md)
+ [Testing a bot using the console](build-test.md)
+ [Creating versions](versions.md)
+ [Built\-in intents and slot types](built-in.md)
+ [Creating custom slot types](custom-slot-types.md)
+ [Using multiple values in a slot](multi-valued-slots.md)
+ [Using an AWS Lambda function](lambda.md)