# Identity\-based policy examples for Amazon Lex V2<a name="security_iam_id-based-policy-examples"></a>

By default, IAM users and roles don't have permission to create or modify Amazon Lex V2 resources\. They also can't perform tasks using the AWS Management Console, AWS CLI, or AWS API\. An IAM administrator must create IAM policies that grant users and roles permission to perform actions on the resources that they need\. The administrator must then attach those policies to the IAM users or groups that require those permissions\.

To learn how to create an IAM identity\-based policy using these example JSON policy documents, see [Creating policies on the JSON tab](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_create.html#access_policies_create-json-editor) in the *IAM User Guide*\.

**Topics**
+ [Policy best practices](#security_iam_service-with-iam-policy-best-practices)
+ [Using the Amazon Lex V2 console](#security_iam_id-based-policy-examples-console)
+ [Allow users to add functions to a bot](#security_iam-bot-role)
+ [Allow users to add channels to a bot](#security_iam-channel-role)
+ [Allow users to create and update bots](#security_iam-bot-create-update)
+ [Allow users to delete bots](#security_iam-bot-delete)
+ [Allow users to have a conversation with a bot](#security_iam-bot-conversation)
+ [Allow a specific user to manage resource\-based policies](#security_iam_id-based-policy-examples-allow-resource)
+ [Allow a user to export bots and bot locales](#security_iam_id-based-policy-examples-export)
+ [Allow a user to import bots and bot locales](#security_iam_id-based-policy-examples-import)
+ [Allow a user to migrate a bot from Amazon Lex to Amazon Lex V2](#security_iam_id-based-policy-examples-migrate)
+ [Allow users to view their own permissions](#security_iam_id-based-policy-examples-view-own-permissions)

## Policy best practices<a name="security_iam_service-with-iam-policy-best-practices"></a>

Identity\-based policies are very powerful\. They determine whether someone can create, access, or delete Amazon Lex V2 resources in your account\. These actions can incur costs for your AWS account\. When you create or edit identity\-based policies, follow these guidelines and recommendations:
+ **Get started using AWS managed policies** – To start using Amazon Lex V2 quickly, use AWS managed policies to give your employees the permissions they need\. These policies are already available in your account and are maintained and updated by AWS\. For more information, see [Get started using permissions with AWS managed policies](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html#bp-use-aws-defined-policies) in the *IAM User Guide*\.
+ **Grant least privilege** – When you create custom policies, grant only the permissions required to perform a task\. Start with a minimum set of permissions and grant additional permissions as necessary\. Doing so is more secure than starting with permissions that are too lenient and then trying to tighten them later\. For more information, see [Grant least privilege](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html#grant-least-privilege) in the *IAM User Guide*\.
+ **Enable MFA for sensitive operations** – For extra security, require IAM users to use multi\-factor authentication \(MFA\) to access sensitive resources or API operations\. For more information, see [Using multi\-factor authentication \(MFA\) in AWS](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_mfa.html) in the *IAM User Guide*\.
+ **Use policy conditions for extra security** – To the extent that it's practical, define the conditions under which your identity\-based policies allow access to a resource\. For example, you can write conditions to specify a range of allowable IP addresses that a request must come from\. You can also write conditions to allow requests only within a specified date or time range, or to require the use of SSL or MFA\. For more information, see [IAM JSON policy elements: Condition](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_elements_condition.html) in the *IAM User Guide*\.

## Using the Amazon Lex V2 console<a name="security_iam_id-based-policy-examples-console"></a>

To access the Amazon Lex V2 console, you must have a minimum set of permissions\. These permissions must allow you to list and view details about the Amazon Lex V2 resources in your AWS account\. If you create an identity\-based policy that is more restrictive than the minimum required permissions, the console won't function as intended for entities \(IAM users or roles\) with that policy\.

You don't need to allow minimum console permissions for users that are making calls only to the AWS CLI or the AWS API\. Instead, allow access to only the actions that match the API operation that you're trying to perform\.

To ensure that users and roles can still use the Amazon Lex V2 console, users need to have Console access\. For more information about creating a user with Console access, see [Creating an IAM user in your AWS account](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_users_create.html) in the *IAM User Guide*\.

## Allow users to add functions to a bot<a name="security_iam-bot-role"></a>

This example shows a policy that allows IAM users to add Amazon Comprehend, sentiment analysis and Amazon Kendra query permissions to an Amazon Lex V2 bot\.

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "Id1",
            "Effect": "Allow",
            "Action": "iam:PutRolePolicy",
            "Resource": "arn:aws:iam::*:role/aws-service-role/lexv2.amazonaws.com/AWSServiceRoleForLexV2Bots*"
        },
        {
            "Sid": "Id2",
            "Effect": "Allow",
            "Action": "iam:GetRolePolicy",
            "Resource": "arn:aws:iam::*:role/aws-service-role/lexv2.amazonaws.com/AWSServiceRoleForLexV2Bots*"
        }
    ]
}
```

## Allow users to add channels to a bot<a name="security_iam-channel-role"></a>

This example is a policy that allows IAM users to add a messaging channel to a bot\. A user must have this policy in place before they can deploy a bot on a messaging platform\.

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "Id1",
            "Effect": "Allow",
            "Action": "iam:PutRolePolicy",
            "Resource": "arn:aws:iam::*:role/aws-service-role/channels.lexv2.amazonaws.com/AWSServiceRoleForLexV2Channels*"
        },
        {
            "Sid": "Id2",
            "Effect": "Allow",
            "Action": "iam:GetRolePolicy",
            "Resource": "arn:aws:iam::*:role/aws-service-role/channels.lexv2.amazonaws.com/AWSServiceRoleForLexV2Channels*"
        }
    ]
}
```

## Allow users to create and update bots<a name="security_iam-bot-create-update"></a>

This example shows an example policy that allows IAM users to create and update any bot\. The policy includes permissions to complete this action on the console or using the AWS CLI or AWS API\.

```
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Action": [
        "lex:CreateBot",
        "lex:UpdateBot",
        "iam:PassRole"
      ],
      "Effect": "Allow",
        "Resource": [
        "arn:aws:lex:us-east-2:055970264539:bot/*"
        ]
    }
  ]
}
```

## Allow users to delete bots<a name="security_iam-bot-delete"></a>

This example shows an example policy that allows IAM users to delete any bot\. The policy includes permissions to complete this action on the console or using the AWS CLI or AWS API\.

```
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Action": [
          "lex:DeleteBot", 
          "lex:DeleteBotLocale", 
          "lex:DeleteBotAlias", 
          "lex:DeleteIntent", 
          "lex:DeleteSlot", 
          "lex:DeleteSlottype"
      ],
      "Effect": "Allow",
      "Resource": ["arn:aws:lex:Region:123412341234:bot/*", 
                   "arn:aws:lex:Region:123412341234:bot-alias/*"]
    }
  ]
}
```

## Allow users to have a conversation with a bot<a name="security_iam-bot-conversation"></a>

This example shows an example policy that allows IAM users have a conversation with any bot\. The policy includes permissions to complete this action on the console or using the AWS CLI or AWS API\.

```
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Action": [
          "lex:StartConversation", 
          "lex:RecognizeText", 
          "lex:RecognizeUtterance", 
          "lex:GetSession", 
          "lex:PutSession", 
          "lex:DeleteSession"
      ],
      "Effect": "Allow",
      "Resource": "arn:aws:lex:Region:123412341234:bot-alias/*"
    }
  ]
}
```

## Allow a specific user to manage resource\-based policies<a name="security_iam_id-based-policy-examples-allow-resource"></a>

The following example grants permission for a specific user to manage the resource\-based policies\. It allows console and API access to the policies associated with bots and bot aliases\.

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "ResourcePolicyEditor",
            "Effect": "Allow",
            "Principal": {
                "AWS": "arn:aws:iam::123456789012:role/ResourcePolicyEditor"
            },
            "Action": [
                "lex:CreateResourcePolicy",
                "lex:UpdateResourcePolicy",
                "lex:DeleteResourcePolicy",
                "lex:DescribeResourcePolicy"
            ]
        }
    ]
}
```

## Allow a user to export bots and bot locales<a name="security_iam_id-based-policy-examples-export"></a>

The following IAM permission policy enables a user to create, update, and get an export for a bot or bot locale\.

```
{
    "Version": "2012-10-17", 
    "Statement": [ 
        {
            "Action": [ 
                "lex:CreateExport", 
                "lex:UpdateExport",
                "lex:DescribeExport", 
                "lex:DescribeBot",
                "lex:DescribeBotLocale", 
                "lex:ListBotLocales",
                "lex:DescribeIntent", 
                "lex:ListIntents",
                "lex:DescribeSlotType", 
                "lex:ListSlotTypes",
                "lex:DescribeSlot", 
                "lex:ListSlots"
            ], 
            "Effect": "Allow", 
            "Resource": ["arn:aws:lex:Region:123456789012:bot/*"]
        } 
    ]
}
```

## Allow a user to import bots and bot locales<a name="security_iam_id-based-policy-examples-import"></a>

The following IAM permission policy allows a user to import a bot or bot locale and to check the status of an import\.

```
{
    "Version": "2012-10-17", 
    "Statement": [ 
        {
            "Action": [ 
                "lex:CreateUploadUrl", 
                "lex:StartImport",
                "lex:DescribeImport",
                "lex:CreateBot",
                "lex:UpdateBot", 
                "lex:DeleteBot",
                "lex:CreateBotLocale",
                "lex:UpdateBotLocale", 
                "lex:DeleteBotLocale",
                "lex:CreateIntent",
                "lex:UpdateIntent", 
                "lex:DeleteIntent",
                "lex:CreateSlotType",
                "lex:UpdateSlotType", 
                "lex:DeleteSlotType",
                "lex:CreateSlot",
                "lex:UpdateSlot", 
                "lex:DeleteSlot",
                "iam:PassRole", 
            ], 
            "Effect": "Allow", 
            "Resource": [
                "arn:aws:lex:Region:123456789012:bot/*", 
                "arn:aws:lex:Region:123456789012:bot-alias/*"
            ]
        } 
    ]
}
```

## Allow a user to migrate a bot from Amazon Lex to Amazon Lex V2<a name="security_iam_id-based-policy-examples-migrate"></a>

The following IAM permission policy allows a user to start migrating a bot from Amazon Lex to Amazon Lex V2\.

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "startMigration",
            "Effect": "Allow",
            "Action": "lex:StartMigration",
            "Resource": "arn:aws:lex:>Region<:>123456789012<:bot:*"
        },
        {
            "Sid": "passRole",
            "Effect": "Allow",
            "Action": "iam:PassRole",
            "Resource": "arn:aws:iam::>123456789012<:role/>v2 bot role<"
        },
        {
            "Sid": "allowOperations",
            "Effect": "Allow",
            "Action": [
                "lex:CreateBot",
                "lex:CreateIntent",
                "lex:UpdateSlot",
                "lex:DescribeBotLocale",
                "lex:UpdateBotAlias",
                "lex:CreateSlotType",
                "lex:DeleteBotLocale",
                "lex:DescribeBot",
                "lex:UpdateBotLocale",
                "lex:CreateSlot",
                "lex:DeleteSlot",
                "lex:UpdateBot",
                "lex:DeleteSlotType",
                "lex:DescribeBotAlias",
                "lex:CreateBotLocale",
                "lex:DeleteIntent",
                "lex:StartImport",
                "lex:UpdateSlotType",
                "lex:UpdateIntent",
                "lex:DescribeImport"
            ],
            "Resource": [
                "arn:aws:lex:>Region<:>123456789012<:bot/*",
                "arn:aws:lex:>Region<:>123456789012<:bot-alias/*/*"
            ]
        },
        {
            "Sid": "showBots",
            "Effect": "Allow",
            "Action": [
                "lex:CreateUploadUrl",
                "lex:ListBots"
            ],
            "Resource": "*"
        }
    ]
}
```

## Allow users to view their own permissions<a name="security_iam_id-based-policy-examples-view-own-permissions"></a>

This example shows how you might create a policy that allows IAM users to view the inline and managed policies that are attached to their user identity\. This policy includes permissions to complete this action on the console or programmatically using the AWS CLI or AWS API\.

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "ViewOwnUserInfo",
            "Effect": "Allow",
            "Action": [
                "iam:GetUserPolicy",
                "iam:ListGroupsForUser",
                "iam:ListAttachedUserPolicies",
                "iam:ListUserPolicies",
                "iam:GetUser"
            ],
            "Resource": ["arn:aws:iam::*:user/${aws:username}"]
        },
        {
            "Sid": "NavigateInConsole",
            "Effect": "Allow",
            "Action": [
                "iam:GetGroupPolicy",
                "iam:GetPolicyVersion",
                "iam:GetPolicy",
                "iam:ListAttachedGroupPolicies",
                "iam:ListGroupPolicies",
                "iam:ListPolicyVersions",
                "iam:ListPolicies",
                "iam:ListUsers"
            ],
            "Resource": "*"
        }
    ]
}
```
