# Enabling the bot to wait for the user to provide additional information<a name="wait-and-continue"></a>

When you start a bidirectional stream from an Amazon Lex bot to your application, you can configure the bot to wait for the user to provide additional information\. There are circumstances when a user might not be ready to respond to a prompt\. For example, a user might not be ready to provide their credit card information because their wallet is in another room\.

By using the *Wait and continue* behavior of the Amazon Lex bot, users can say phrases such as "hold on a second" to make the bot wait for them to find the information and provide it\. When you enable this behavior, the bot sends periodic reminders to the user to provide the information\. It does not send back transcript events because there are no user utterances for it to transcribe\.

The Amazon Lex bot automatically manages a streaming conversation\. You don't have to write any additional code to enable this functionality\. When a bot is prompted to wait by the user, the `state` of the `Intent` is `Waiting` and the `type` of the `DialogAction` is `ElicitSlot`\. You can use this information to help customize your application for your needs\. For example, you can configure your application to play music when the user is looking for their credit card\.

You enable the wait and continue behavior for an individual slot\. To learn more about slots, see [How it works](how-it-works.md)\.

**To enable wait and continue**

1. Sign in to AWS Management Console and open the Amazon Lex console at [Amazon Lex console](https://console.aws.amazon.com/lexv2/)\.

1. Under **Bots**, select a bot\.

1. Under **Language**, select the language of the bot\.

1. Choose **View intents**\.

1. Choose the intent\.

1. Under **Slots**, choose a slot\.

1. Under **Advanced options**, choose **Wait and continue**\.

1. Under **Wait and continue** specify the following fields:
   + **Response when user wants the bot to wait** – This is how the bot responds when the user asks it to wait for the additional information\.
   + **Response if the user needs the bot to continue waiting** – This is the response the bot sends to remind the user that it's still waiting for the information\. You can change how frequently the bot reminds the user\.
   + **Response when the user wants to continue** – this is the bot's response when the user has the requested information\.

For every bot prompt, you can give multiple variations of the prompt, and one is presented to the user at random\. You can also choose whether these prompts can be interrupted by the user\.

To test the wait and continue functionality, configure your bot to wait for user input and start a stream to an Amazon Lex bot\. For information on streaming to a bot, see [Using the API to start a streaming conversation](using-streaming-api.md)\.