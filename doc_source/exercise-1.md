# Exercise 1: Create a bot from an example<a name="exercise-1"></a>

In this exercise, you create your first Amazon Lex bot and test it in the Amazon Lex console\. For this exercise, you use the **OrderFlowers** example\.

## Example overview<a name="example-overview"></a>

You use the **OrderFlowers** example to create an Amazon Lex bot\. For more information about the structure of a bot, see [How it works](how-it-works.md)\.
+ **Intent** – OrderFlowers
+ **Slot types** – One custom slot type called `FlowerTypes` with enumeration values: `roses`, `lilies`, and `tulips`\.
+ **Slots** – The intent requires the following information \(that is, slots\) before the bot can fulfill the intent\.
  + `PickupTime` \(AMAZON\.TIME built\-in type\)
  + `FlowerType` \(FlowerTypes custom type\)
  + `PickupDate` \(AMAZON\.DATE built\-in type\)
+ **Utterance** – The following sample utterances indicate the user's intent:
  + "I would like to pick up flowers\."
  + "I would like to order some flowers\."
+ **Prompts** – After the bot identifies the intent, it uses the following prompts to fill the slots:
  + Prompt for the `FlowerType` slot – "What type of flowers would you like to order?"
  + Prompt for the `PickupDate` slot – "What day do you want the \{FlowerType\} to be picked up?"
  + Prompt for the `PickupTime` slot – "At what time do you want the \{FlowerType\} to be picked up?"
  + Confirmation statement – "Okay, your \{FlowerType\} will be ready for pickup by \{PickupTime\} on \{PickupDate\}\. Does this sound okay?" 

**To create an Amazon Lex bot \(Console\)**

1. Sign in to the AWS Management Console and open the Amazon Lex console at [ https://console\.aws\.amazon\.com/lexv2/ ](https://console.aws.amazon.com/https://console.aws.amazon.com/lexv2/)

1. Choose **Create bot**\.

1. For the **Creation method**, choose **Start with an example**\.

1. In the **Example bots** section, choose **OrderFlowers** from the list\.

1. In the **Bot configuration** section give the bot a name and a description\. The name must be unique in your account\.

1. In the **Permissions** section, choose **Create a new role with basic Amazon Lex permissions**\. This will create an AWS Identity and Access Management \(IAM\) role with the permissions that Amazon Lex needs to run your bot\.

1. In the **Children's Online Privacy Protection Act \(COPPA\)** section, make the appropriate choice\.

1. In the **Session timeout** and **Advanced settings** sections, leave the defaults\.

1. Choose **Next**\. Amazon Lex creates your bot\.

After you create your bot, you must add one or more languages that the bot supports\. A language contains the intents, slot types, and slots that the bot uses to converse with users\.

**To add a language to a bot**

1. In the **Language** section, choose a supported language, and add a description\.

1. Leave the **Voice interaction** and **Intent classification confidence score threshold** fields with their defaults\.

1. Choose **Add language** to add the language to the bot\.

1. After the language is added, choose **Done** to continue\.

After you choose **Done**, the console opens the intent editor\. You can use the intent editor to examine the intents used by the bot\. When you are done examining the bot, you can test to bot\.

**To test the OrderFlowers bot**

1. From the bottom menu, choose **Build**\. Wait for the bot to build\.

1. When the build is complete, choose **Test** to open the test window\.

1. Test the bot\. Start the conversation with one of the sample utterances, such as "I would like to pick up flowers\."

## Next steps<a name="getting-started-next-steps"></a>

Now that you've created you first bot using a template, you can use the console to create your own bot\. For instruction on creating a custom bot, and for more information about creating bots, see [Building bots](building-bots.md)\.