# Built\-in intents<a name="howitworks-builtins-intents"></a>

For common actions, you can use the standard built\-in intents library\. To create an intent from a built\-in intent, choose a built\-intent in the console, and give it a new name\. The new intent has the configuration of the base intent, such as the sample utterances\. 

In the current implementation, you can't do the following: 
+ Add or remove sample utterances from the base intent
+ Configure slots for built\-in intents

**To add a built\-in intent to a bot**

1. Sign in to the AWS Management Console and open the Amazon Lex V2 console at [ https://console\.aws\.amazon\.com/lexv2/ ](https://console.aws.amazon.com/https://console.aws.amazon.com/lexv2/)

1. Choose the bot to add the built\-in intent to\.

1. In the left menu, choose the language and then choose **Intents**\.

1. Choose **Add intent**, and then choose **Use built\-in intent**\.

1. In **Built\-in intent**, choose the intent to use\.

1. Give the intent a name, and then choose **Add**\.

1. Use the intent editor to configure the intent as required for your bot\.

**Topics**
+ [AMAZON\.CancelIntent](built-in-intent-cancel.md)
+ [AMAZON\.FallbackIntent](built-in-intent-fallback.md)
+ [AMAZON\.HelpIntent](built-in-intent-help.md)
+ [AMAZON\.KendraSearchIntent](built-in-intent-kendra-search.md)
+ [AMAZON\.PauseIntent](built-in-intent-pause.md)
+ [AMAZON\.RepeatIntent](built-in-intent-repeat.md)
+ [AMAZON\.ResumeIntent](built-in-intent-resume.md)
+ [AMAZON\.StartOverIntent](built-in-intent-start-over.md)
+ [AMAZON\.StopIntent](built-in-intent-stop.md)