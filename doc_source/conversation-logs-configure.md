# Configuring conversation logs<a name="conversation-logs-configure"></a>

You enable and disable conversation logs using the console or the `conversationLogSettings` field of the `CreateBotAlias` or `UpdateBotAlias` operation\. You can turn on or turn off audio logs, text logs, or both\. Logging starts on new bot sessions\. Changes to log settings aren't reflected for active sessions\.

To store text logs, use an Amazon CloudWatch Logs log group in your AWS account\. You can use any valid log group\. The log group must be in the same region as the Amazon Lex V2 bot\. For more information about creating a CloudWatch Logs log group, see [ Working with Log Groups and Log Streams ](https://docs.aws.amazon.com/AmazonCloudWatch/latest/logs/Working-with-log-groups-and-streams.html) in the *Amazon CloudWatch Logs User Guide*\.

To store audio logs, use an Amazon S3 bucket in your AWS account\. You can use any valid S3 bucket\. The bucket must be in the same region as the Amazon Lex V2 bot\. For more information about creating an S3 bucket, see [Creating a bucket](https://docs.aws.amazon.com/AmazonS3/latest/gsg/CreatingABucket.html) in the *Amazon Simple Storage Service Getting Started Guide*\.

When you manage conversation logs using the console, the console updates your service role so that it has access to the log group and S3 bucket\. If you are not using the console, you must provide an IAM role with policies that enable Amazon Lex V2 to write to the configured log group or bucket\.

The IAM role that you use to enable conversation logs must have the `iam:PassRole` permission\. The following policy should be attached to the role\.

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": "iam:PassRole",
            "Resource": "arn:aws:iam::account:role/role"
        }
    ]
}
```

## Enabling conversation logs<a name="conversation-logs-enable"></a>

**To turn on logs using the console**

1. Open the Amazon Lex V2 console [https://console\.aws\.amazon\.com/lexv2](https://console.aws.amazon.com/lexv2)\.

1. From the list, choose a bot\.

1. From the left menu, choose **Aliases**\.

1. In the list of aliases, choose the alias for which you want to configure conversation logs\.

1. In the **Conversation logs** section, choose **Manage conversation logs**\. 

1. For text logs, choose **Enable** then enter the Amazon CloudWatch Logs log group name\.

1. For audio logs, choose **Enable** then enter the S3 bucket information\.

1. Optional\. To encrypt audio logs, choose the AWS KMS key to use for encryption\.

1. Choose **Save** to start logging conversations\. If necessary, Amazon Lex V2 will update your service role with permissions to access the CloudWatch Logs log group and selected S3 bucket\.

## Disabling conversation logs<a name="conversation-logs-disable"></a>

**To turn off logs using the console**

1. Open the Amazon Lex V2 console [https://console\.aws\.amazon\.com/lexv2](https://console.aws.amazon.com/lexv2)\.

1. From the list, choose a bot\.

1. From the left menu, choose **Aliases**\.

1. In the list of aliases, choose the alias for which you want to configure conversation logs\.

1. In the **Conversation logs** section, choose **Manage conversation logs**\.

1. Disable text logging, audio logging, or both to turn off logging\.

1. Choose **Save** to stop logging conversations\.