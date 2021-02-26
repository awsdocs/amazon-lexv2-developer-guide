# Using service\-linked roles for Amazon Lex<a name="using-service-linked-roles"></a>

Amazon Lex uses AWS Identity and Access Management \(IAM\)[ service\-linked roles](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_terms-and-concepts.html#iam-term-service-linked-role)\. A service\-linked role is a unique type of IAM role that is linked directly to Amazon Lex\. Service\-linked roles are predefined by Amazon Lex and include all the permissions that the service requires to call other AWS services on your behalf\. 

A service\-linked role makes setting up Amazon Lex easier because you don’t have to manually add the necessary permissions\. Amazon Lex defines the permissions of its service\-linked roles, and unless defined otherwise, only Amazon Lex can assume its roles\. The defined permissions include the trust policy and the permissions policy, and that permissions policy cannot be attached to any other IAM entity\.

You can delete a service\-linked role only after first deleting their related resources\. This protects your Amazon Lex resources because you can't inadvertently remove permission to access the resources\.

For information about other services that support service\-linked roles, see [AWS Services That Work with IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_aws-services-that-work-with-iam.html) and look for the services that have **Yes **in the **Service\-Linked Role** column\. Choose a **Yes** with a link to view the service\-linked role documentation for that service\.

## Service\-linked role permissions for Amazon Lex<a name="slr-permissions"></a>

Amazon Lex uses these service\-linked roles\.
+ **AWSServiceRoleForLexV2Bots\_** – Gives permission to connect your bot to other required services\.\.
+ **AWSServiceRoleForLexV2Channels\_** – Gives permission to list bots in an account and to call conversation APIs for a bot\.\.

The AWSServiceRoleForLexV2Bots\_ service\-linked role trusts the following service to assume the role:
+ `lexv2.amazonaws.com`

The AWSServiceRoleForLexV2Channels\_ service linked role trusts the following service to assume the role:
+ `channels.lexv2.amazonaws.com`

The AWSServiceRoleForLexV2Bots\_ role allows Amazon Lex to complete the following actions on the specified resources:
+ Action: Use Amazon Polly to synthesize speech on all Amazon Lex resources that the action supports\.
+ Action: If a bot is configured to use Amazon Comprehend sentiment analysis, detect sentiment on all Amazon Lex resources that the action supports\.
+ Action: If a bot is configured to store audio logs in an S3 bucket, put object in a specified bucket\.
+ Action: If a bot is configured to store audio and text logs, create a log stream in and put logs into a specified log group\.
+ Action: If a bot is configured to use a AWS KMS key to encrypt data, generate a specific data key\.
+ Action: If a bot is configured to use the `KendraSearchIntent` intent, query access to a specified Amazon Kendra index\.

If a bot is configured to use a channel to communicate with a messaging service, the AWSServiceRoleForLexV2Channels\_ role permissions policy allows Amazon Lex to complete the following actions on the specified resources:
+ Action: List permissions on all bots in an account\.
+ Action: Recognize text, get session and put session permissions on a specified bot alias\.

You must configure permissions to allow an IAM entity \(such as a user, group, or role\) to create, edit, or delete a service\-linked role\. For more information, see [Service\-Linked Role Permissions](https://docs.aws.amazon.com/IAM/latest/UserGuide/using-service-linked-roles.html#service-linked-role-permissions) in the *IAM User Guide*\.

## Creating a service\-linked role for Amazon Lex<a name="create-slr"></a>

You don't need to manually create a service\-linked role\. When you create or modify or bot, or create a channel integration with a messaging service in the AWS Management Console, the AWS CLI, or the AWS API, Amazon Lex creates the service\-linked role for you\. 

Amazon Lex creates a new service\-linked role in your account for each bot\. When you create a channel integration to deploy a bot on a messaging platform, Amazon Lex creates a new service\-linked role in your account for each channel\.

If you delete this service\-linked role, and then need to create one again, you can use the same process to create a new role in your account\. When you create or modify or bot, or create a channel integration with a messaging service, Amazon Lex creates the service\-linked role with a new random suffix\. 

## Editing a service\-linked role for Amazon Lex<a name="edit-slr"></a>

Amazon Lex does not allow you to edit the AWSServiceRoleForLexV2Bots\_ or AWSServiceRoleForLexV2Channels\_ service\-linked roles\. After you create a service\-linked role, you cannot change the name of the role because various entities might reference the role\. For AWSServiceRoleForLexV2Bots\_, Amazon Lex modifies the role when you add additional capabilities to a bot\. For example, if you add Amazon Comprehend sentiment analysis to a bot, Amazon Lex adds permission for the `DetectSentiment` action to AWSServiceRoleForLexV2Bots\_ You can edit the description of either role using IAM\. For more information, see [Editing a Service\-Linked Role](https://docs.aws.amazon.com/IAM/latest/UserGuide/using-service-linked-roles.html#edit-service-linked-role) in the *IAM User Guide*\.

## Deleting a service\-linked role for Amazon Lex<a name="delete-slr"></a>

If you no longer need to use a feature or service that requires a service\-linked role, we recommend that you delete that role\. That way you don’t have an unused entity that is not actively monitored or maintained\. However, you must clean up the resources for your service\-linked role before you can manually delete it\.

**Note**  
If the Amazon Lex service is using the role when you try to delete the resources, then the deletion might fail\. If that happens, wait for a few minutes and try the operation again\.

**To delete Amazon Lex resources used by AWSServiceRoleForLexV2Bots\_**

1. Sign in to the AWS Management Console and open the Amazon Lex console at [ https://console\.aws\.amazon\.com/lexv2/ ](https://console.aws.amazon.com/https://console.aws.amazon.com/lexv2/)

1. Choose to bot to delete\. 

1. From the left menu, choose **Settings**\.

1. From **IAM permissions**, record the **Runtime role** identifier\.

1. From the left menu, choose **Bots**\.

1. From the list of bots, choose the radio button next to the bot to delete\.

1. From the **Action**, choose **Delete**\.

**To delete Amazon Lex resources used by AWSServiceRoleForLexV2Channels\_**

1. Sign in to the AWS Management Console and open the Amazon Lex console at [ https://console\.aws\.amazon\.com/lexv2/ ](https://console.aws.amazon.com/https://console.aws.amazon.com/lexv2/)

1. Choose to bot to delete\. 

1. From the left menu, choose **Bot versions**, then choose **Channel integrations**\.

1. Choose the channel to delete\.

1. From **General configuration**, choose the choose the role name\. The IAM management console opens in a new tab with the role chosen\.

1. In the Amazon Lex console, choose **Delete**, then choose **Delete** again to delete the channel\.

1. In the IAM management console, choose **DeleteRole** to remove the channel integration role\.

**To manually delete the service\-linked role using IAM**

Use the IAM console, the AWS CLI, or the AWS API to delete the AWSServiceRoleForLexV2Bots\_ or AWSServiceRoleForLexV2Channels\_ service\-linked role\. For more information, see [Deleting a Service\-Linked Role](https://docs.aws.amazon.com/IAM/latest/UserGuide/using-service-linked-roles.html#delete-service-linked-role) in the *IAM User Guide*\.

## Supported regions for Amazon Lex service\-linked roles<a name="slr-regions"></a>

Amazon Lex supports using service\-linked roles in all of the regions where the service is available\. For more information, see [AWS Regions and Endpoints](https://docs.aws.amazon.com/general/latest/gr/rande.html)\.