# Creating a bot<a name="build-create"></a>

Start creating your bot by defining the name, description and some basic information\.

**To create a bot**

1. Sign in to the AWS Management Console and open the Amazon Lex V2 console at [ https://console\.aws\.amazon\.com/lexv2/home ](https://console.aws.amazon.com/lexv2/home)

1. Choose **Create bot**\.

1. In the **Creation method** section, choose **Create**\.

1. In the **Bot configuration** section, give the bot a name and an optional description\.

1. In the **IAM permissions** section, choose an AWS Identity and Access Management \(IAM\) role that provides Amazon Lex V2 permission to access other AWS services, such as Amazon CloudWatch\. You can have Amazon Lex V2 create the role, or you can choose an existing role with CloudWatch permissions\. 

1. In the **Children's Online Privacy Protection Act \(COPPA\)** section, choose the appropriate response\.

1. In the **Idle session timeout** section, choose the duration that Amazon Lex V2 keeps a session with a user open\. Amazon Lex V2 maintains session variables for the duration of the session so that your bot can resume a conversation with the same variables\.

1. In the **Advanced settings** section add tags that help identify the bot, and can be used to control access and monitor resources\.

1. Choose **Next** to create the bot and move to adding a language\.