# Adding intents<a name="build-intents"></a>

Intents are the goals that your users want to fulfill, such as ordering flowers or booking a hotel\. Your bot needs to have at least one intent\.

By default, all bots contain a single built\-in intent, the fallback intent\. This intent is used when Amazon Lex V2 does not recognize any other intent\. For example, if a user says "I want to order flowers" to a hotel booking intent, the fallback intent is triggered\.

**To add an intent**

1. Sign in to the AWS Management Console and open the Amazon Lex V2 console at [ https://console\.aws\.amazon\.com/lexv2/ ](https://console.aws.amazon.com/lexv2/)

1. From the list of bots, choose the bot that you want to add the intent to, then from **Add languages** choose **View languages**\.

1. Choose the language to add the intent to, then choose **Intents**\.

1. Choose **Add intent**, give your intent a name, and then choose **Add**\.

1. In the intent editor, add the details of your intent\.
   + **Conversation flow** – Use the conversation flow diagram to see how a dialog with your bot might look\. You can choose different sections of the conversation to jump to that section of the intent editor\.
   + **Intent details** – Give the intent a name and description to help identify the purpose of the intent\. You can also see the unique identifier that Amazon Lex V2 assigned to the intent\.
   + **Contexts** – Set the input and output contexts for the intent\. A context is a state variable associated with an intent\. An output context is set when an intent is fulfilled\. An intent with an input context can only be recognized with the context is active\. An intent with no input contexts can always be recognized\.
   + **Sample utterances** – You should provide 10 or more phrases that you expect your users to use to trigger an intent\. Amazon Lex generalizes from these phrases to recognize that the user wants to trigger the intent\.
   + **Slots** – Define the slots, or parameters, required to fulfill the intent\. Each slot has a type that defines the values that can be entered in the slot\. You can choose from your custom slot types, or you can choose a built\-in slot type\.
   + **Confirmation prompts and declination responses** – These responses are used to end the conversation with a user and to confirm or decline fulfillment of the intent\. The confirmation prompt asks the user to review slot values\. For example, "I've booked a hotel room for Friday\. Is this correct?" The declination response is sent to the user when they decline the confirmation\.
   + **Closing responses** – Text sent to the user after the intent is fulfilled\. For example, a thank you for booking a hotel room\. Or it can prompt the user to start a different intent, such as "Thank you for booking a room, would you like to book a rental car?"
   + **Codehooks** – Indicate whether you are using an AWS Lambda function to initialize the intent, validate user input, and to fulfill the intent\. You specify the Lambda function in the alias that you use to run the bot\.

1. Choose **Save intent** to save the intent\.

## Turning off responses<a name="intent-active"></a>

While using your bot, you may find it necessary to turn off confirmation prompts and closing responses\. Responses can be turned on and off for each intent\. You can choose to turn off confirmation prompts, closing responses, or both\. 

Use the **Active** toggle to determine whether or not to use a response\.

![\[The active toggle for confirmation responses.\]](http://docs.aws.amazon.com/lexv2/latest/dg/images/prompt-toggle.png)