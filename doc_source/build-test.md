# Testing a bot using the console<a name="build-test"></a>

The Amazon Lex console contains a test window that you can use to test the interaction with your bot\. You use the test window to have a test conversation with your bot and to see the responses that your application receives from the bot\.

There are two types of testing that you can perform with your bot\. The first, express testing, enables you to test your bot with the exact phrases that you used for creating the bot\. For example, if you added the utterance "I want to pick up flowers" to your intent, you can test the bot using that exact phrase\.

The second type, complete testing, enables you to test your bot using phrases related to the utterances that you configured\. For example, you can use the phrase "Can I order flowers" to start a conversation with your bot\.

You test a bot using a specific alias and language\. If you are testing the development version of the bot, you use the `TestBotAlias` alias for testing\.

**To open the test window**

1. Sign in to the AWS Management Console and open the Amazon Lex console at [ https://console\.aws\.amazon\.com/lexv2/ ](https://console.aws.amazon.com/lexv2/)

1. Choose the bot to test from the list of bots\.

1. From the left menu, choose **Aliases**\.

1. From the list of aliases, choose the alias to test\.

1. From **Languages**, choose the radio button of the language to test, and then choose **Test**\.

After you choose **Test**, the test window opens in the console\. You can use the test window to interact with your bot, as shown in the following graphic\.

![\[The test window showing a conversation with an order flowers bot.\]](http://docs.aws.amazon.com/lexv2/latest/dg/images/test-example-1.png)

In addition to the conversation, you can also choose **Inspect** in the test window to see the responses returned from the bot\. The first view shows you a summary of the information returned from your bot to the test window\.

![\[The test window showing the summary view of a conversation with a bot.\]](http://docs.aws.amazon.com/lexv2/latest/dg/images/test-example-2.png)

You can also use the test inspection window to see the JSON structures that are sent between the bot and the test window\. You can see both the request from the test window and the response from Amazon Lex\.

![\[The test window showing the JSON structures used in a conversation with a bot.\]](http://docs.aws.amazon.com/lexv2/latest/dg/images/test-example-3.png)