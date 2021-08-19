# Importing a bot \(console\)<a name="import-console"></a>

**To import a bot using the console**

1. Sign in to the AWS Management Console and open the Amazon Lex console at [https://console\.aws\.amazon\.com/lex/](https://console.aws.amazon.com/lex/)\.

1. From **Action**, choose **Import**\.

1. In **Input file**, give the bot a name and then choose the \.zip file that contains the JSON files that define the bot\.

1. If the \.zip file is password protected, enter the password for the \.zip file\. Password protecting the archive is optional, but it helps protect the contents\.

1. Create or enter the IAM role that defines permissions for your bot\.

1. Indicate whether your bot is subject to the Children's Online Privacy Protection Act \(COPPA\)\.

1. Provide an idle timeout setting for your bot\. If you don't provide a value, the value from the zip file is used\. If the \.zip file does not contain a timeout setting, Amazon Lex uses the default of 300 seconds \(five minutes\)\.

1. \(Optional\) Add tags for your bot\.

1. Choose whether to warn about overwriting existing bots with the same name\. If you enable warnings, if the bot you are importing would overwrite an existing bot, you receive a warning and the bot is not imported\. If you disable warnings, the imported bot replaces the existing bot with the same name\.

1. Choose **Import**\.

After you start the import, you return to the list of bots\. To monitor the progress of the import, use the **Import/export history** list\. When the status of the import is **Complete**, you can choose the bot from the list of bots to modify or build the bot\. 

**To import a bot language**

1. Sign in to the AWS Management Console and open the Amazon Lex console at [https://console\.aws\.amazon\.com/lex/](https://console.aws.amazon.com/lex/)\.

1. From the list of bots, choose the bot to which you want to import a language\.

1. From **Add languages**, choose **View languages**\.

1. From **Action**, choose **import**\.

1. In **Input file**, choose the file that contains the language to import\. If you protected the \.zip file, provide the password in **Password**\.

1. In **Language**, choose the language to import as\. The language doesn't have to match the language in the import file\. You can copy the intents from one language to another\.

1. In **Voice**, choose the Amazon Polly voice to use for voice interaction, or choose **None** for a text\-only bot\.

1. In **Confidence score threshold**, enter the threshold where Amazon Lex inserts the `AMAZON.FallbackIntent`, the `AMAZON.KendraSearchIntent`, or both when returning alternative intents\.

1. Choose whether to warn about overwriting an existing language\. If you enable warnings, if the language you are importing would overwrite an existing language, you receive a warning and the language is not imported\. If you disable warnings, the imported language replaces the existing language\.

1. Choose **Import** to start importing the language\.

After you start the import, you return to the list of languages\. To monitor the progress of the import, use the **Import/export history** list\. When the status of the import is **Complete**, you can choose the language from the list of bots to modify or build the bot\. 