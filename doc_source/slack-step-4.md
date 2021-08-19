# Step 4: Integrate the Slack application with the Amazon Lex V2 bot<a name="slack-step-4"></a>

**To integrate the Slack application with your Amazon Lex V2 bot**

1. Sign in to the AWS Management Console and open the Amazon Lex V2 console at [ https://console\.aws\.amazon\.com/lexv2/ ](https://console.aws.amazon.com/https://console.aws.amazon.com/lexv2/)

1. From the list of bots, choose the Amazon Lex V2 bot that you created in step 1\.

1. In the left menu, choose **Channel integrations** and then choose **Add channel**\.

1. In **Create channel**, do the following:

   1. For **Platform**, choose **Slack**\.

   1. For **Identity policies**, choose the AWS KMS key to protect channel information\. The default key is provided by Amazon Lex V2\.

   1. For **Integration configuration**, give the channel a name and an optional description\. Choose the alias that points to the version of the bot to use, and choose the language that the channel supports\.

   1. For **Additional configuration**, enter the following:
      + **Client ID** – enter the client ID from Slack\. 
      + **Client secret** – enter the client secret from Slack\. 
      + **Verification token** – enter the verification token from Slack\.
      + **Success page URL** – The URL of the page that Slack should open when the user is authenticated\. Typically you leave this blank\.

1. Choose **Create** to create the channel\.

1. Amazon Lex V2 shows the list of channels for your bot\. From the list, choose the channel that you just created\.

1. From **Callback URL**, record the endpoint and the OAuth endpoint\.

## Next step<a name="step-4-next"></a>

[Step 5: Complete Slack integration](slack-step-5.md)