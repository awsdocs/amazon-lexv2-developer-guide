# Step 3: Integrate Facebook Messenger with the Amazon Lex bot<a name="facebook-step-3"></a>

In this step you link your Amazon Lex bot with Facebook\.

1. Sign in to the AWS Management Console and open the Amazon Lex console at [ https://console\.aws\.amazon\.com/lexv2/ ](https://console.aws.amazon.com/https://console.aws.amazon.com/lexv2/)

1. From the list of bots, choose the Amazon Lex bot that you created in step 1\.

1. In the left menu, choose **Channel integrations** and then choose **Add channel**\.

1. In **Create channel**, do the following:

   1. For **Platform**, choose **Facebook**\.

   1. For **Identity policies**, choose the AWS KMS key to protect channel information\. The default key is provided by Amazon Lex\.

   1. For **Integration configuration**, give the channel a name and an optional description\. Choose the alias that points to the version of the bot to use, and choose the language that the channel supports\.

   1. For **Additional configuration**, enter the following:
      + **Alias** – A string that identifies the app that is calling Amazon Lex\. You can use any string\. Record this string, you enter it in the Facebook developer console\.
      + **Page access token** – The page access token that you copied from the Facebook developer console\.
      + **App secret key** – The secret key that you copied from the Facebook developer console\.

   1. Choose **Create**

   1. Amazon Lex shows the list of channels for your bot\. From the list, choose the channel that you just created\.

   1. From **Callback URL**, record the callback URL\. You enter this URL in the Facebook developer console\.

## Next step<a name="step-3-next"></a>

[Step 4: Complete Facebook integration](facebook-step-4.md)