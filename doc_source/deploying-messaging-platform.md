# Integrating an Amazon Lex V2 bot with a messaging platform<a name="deploying-messaging-platform"></a>

This section explains how to integrate Amazon Lex V2 bots with the Facebook, Slack, and Twilio messaging platforms\.

**Note**  
When storing your Facebook, Slack, or Twilio configurations, Amazon Lex V2 uses AWS Key Management Service sustomer master keys \(CMK\) to encrypt information\. The first time that you create a channel to one of these messaging platforms, Amazon Lex V2 creates a default CMK \(`aws/lex`\) in your AWS account or you can select your own CMK\. Amazon Lex V2 supports only symmetric keys\.

When a messaging platform sends a request to Amazon Lex V2 it includes platform\-specific information as a request attribute to you Lambda function\. Use this attribute to customize the way that your bot behaves\. For more information, see [Setting request attributes](context-mgmt-request-attribs.md)\.


**Common request attribute**  

| Attribute | Description | 
| --- | --- | 
| x\-amz\-lex:channels:platform | One of the following values: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/lexv2/latest/dg/deploying-messaging-platform.html) | 