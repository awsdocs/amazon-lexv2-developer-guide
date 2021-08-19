# Step 3: Integrate the Twilio message service endpoint with the Amazon Lex V2 bot<a name="twilio-step-3"></a>

1. Sign in to the AWS Management Console and open the Amazon Lex V2 console at [ https://console\.aws\.amazon\.com/lexv2/ ](https://console.aws.amazon.com/https://console.aws.amazon.com/lexv2/)

1. From the list of bots, choose the Amazon Lex V2 bot that you created in step 1\.

1. In the left menu, choose **Channel integrations** and then choose **Add channel**\.

1. In **Create channel**, do the following:

   1. For **Platform**, choose **Twilio**\.

   1. For **Identity policies**, choose the AWS KMS key to protect channel information\. The default key is provided by Amazon Lex V2\.

   1. For **Integration configuration**, give the channel a name and an optional description\. Choose the alias that points to the version of the bot to use, and choose the language that the channel supports\.

   1. For **Additional configuration**, enter the account SID and authentication token from the Twilio dashboard\.

1. Choose **Create**\.

1. From the list of channels, choose the channel that you just created\.

1. Copy the **Callback URL**\.

## Next step<a name="step-3-next"></a>

[Step 4: Complete Twilio integration](twilio-step-4.md)