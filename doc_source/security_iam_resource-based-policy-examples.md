# Resource\-based policy examples for Amazon Lex V2<a name="security_iam_resource-based-policy-examples"></a>

A *resource\-based policy* is attached to a resource, such as a bot or a bot alias\. With a resource\-based policy you can specify who has access to the resource and the actions that they can perform on it\. For example, you can add resource\-based policies that enable a user to modify a specific bot, or to allow a user to use runtime operations on a specific bot alias\.

When you use a resource\-based policy you can allow other AWS services to access resources in your account\. For example, you can allow Amazon Connect to access an Amazon Lex bot\.

To learn how to create a bot or bot alias, see [Building bots](building-bots.md)\.

**Topics**
+ [Use the console to specify a resource\-based policy](#security_iam_resource-based-policy-examples-console)
+ [Use the API to specify a resource\-based policy](#security_iam_resource-based-policy-examples-api)
+ [Allow an IAM role to update a bot and list bot aliases](#security_iam_resource-based-policy-examples-allow-lex-models)
+ [Allow a user to have a conversation with a bot](#security_iam_resource-based-policy-examples-allow-lex-runtime)
+ [Allow an AWS service to use a specific Amazon Lex V2 bot](#security_iam_resource-based-policy-examples-allow-lex-connect)

## Use the console to specify a resource\-based policy<a name="security_iam_resource-based-policy-examples-console"></a>

You can use the Amazon Lex console to manage the resource\-based policies for your bots and bot aliases\. You enter the JSON structure of a policy and the console associates it with the resource\. If there is a policy already associated with a resource, you can use the console to view and modify the policy\.

When you save a policy with the policy editor, the console checks the syntax of the policy\. If the policy contains errors, such as a non\-existent user or an action that is not supported by the resource, it returns an error and doesn't save the policy\. 

The following shows the resource\-based policy editor for a bot in the console\. The policy editor for a bot alias is similar\.

![\[\]](http://docs.aws.amazon.com/lexv2/latest/dg/images/resource-policy-editor.png)

**To open the policy editor for a bot**

1. Sign in to the AWS Management Console and open the Amazon Lex console at [https://console\.aws\.amazon\.com/lex/](https://console.aws.amazon.com/lex/)\.

1. From the **Bots** list, choose the bot whose policy you want to edit\.

1. In the **Resource\-based policy** section, choose **Edit**\.

**To open the policy editor for a bot alias**

1. Sign in to the AWS Management Console and open the Amazon Lex console at [https://console\.aws\.amazon\.com/lex/](https://console.aws.amazon.com/lex/)\.

1. From the **Bots** list, choose the bot that contains the alias that you want to edit\.

1. From the left menu, choose **Aliases**, then choose the alias to edit\.

1. In the **Resource\-based policy** section, choose **Edit**\.

## Use the API to specify a resource\-based policy<a name="security_iam_resource-based-policy-examples-api"></a>

You can use API operations to manage the resource\-based policies for your bots and bot aliases\. There are operations to create, update and delete policies\.

[CreateResourcePolicy](API_CreateResourcePolicy.md)  
Adds a new resource policy with the specified policy statements to a bot or bot alias\.

[CreateResourcePolicyStatement](API_CreateResourcePolicyStatement.md)  
Adds a new resource policy statement to a bot or bot alias\.

[DeleteResourcePolicy](API_DeleteResourcePolicy.md)  
Removes a resource policy from a bot or bot alias\.

[DeleteResourcePolicyStatement](API_DeleteResourcePolicyStatement.md)  
Removes a resource policy statement from a bot or bot alias\.

[DescribeResourcePolicy](API_DescribeResourcePolicy.md)  
Gets a resource policy and the policy revision\.

[UpdateResourcePolicy](API_UpdateResourcePolicy.md)  
Replaces the existing resource policy for a bot or bot alias with a new one\.

### Examples<a name="collapsible-api-example"></a>

------
#### [ Java ]

The following example shows how to use the resource\-based policy operations to manage a resource\-based policy\.

```
        /*
         * Create a new policy for the specified bot alias 
         * that allows a role to invoke lex:UpdateBotAlias on it.
         * The created policy will have revision id 1.
         */
        
        CreateResourcePolicyRequest createPolicyRequest =
                CreateResourcePolicyRequest.builder()
                        .resourceArn("arn:aws:lex:Region:123456789012:bot-alias/MYBOTALIAS/TSTALIASID")
                        .policy("{\"Version\": \"2012-10-17\",\"Statement\": [{\"Sid\": \"BotAliasEditor\",\"Effect\": \"Allow\",\"Principal\": {\"AWS\": \"arn:aws:iam::123456789012:role/BotAliasEditor\"},\"Action\": [\"lex:UpdateBotAlias\"],\"Resource\":[\"arn:aws:lex:Region:123456789012:bot-alias/MYBOTALIAS/TSTALIASID\"]]}")

        lexmodelsv2Client.createResourcePolicy(createPolicyRequest);
        
        /*
         * Overwrite the policy for the specified bot alias with a new policy.
         * Since no expectedRevisionId is provided, this request overwrites the current revision.
         * After this update, the revision id for the policy is 2.
         */
        UpdateResourcePolicyRequest updatePolicyRequest =
        UpdateResourcePolicyRequest.builder()
                        .resourceArn("arn:aws:lex:Region:123456789012:bot-alias/MYBOTALIAS/TSTALIASID")
                        .policy("{\"Version\": \"2012-10-17\",\"Statement\": [{\"Sid\": \"BotAliasEditor\",\"Effect\": \"Deny\",\"Principal\": {\"AWS\": \"arn:aws:iam::123456789012:role/BotAliasEditor\"},\"Action\": [\"lex:UpdateBotAlias\"],\"Resource\":[\"arn:aws:lex:Region:123456789012:bot-alias/MYBOTALIAS/TSTALIASID\"]]}")

        lexmodelsv2Client.updateResourcePolicy(updatePolicyRequest);
        
        /*
         * Creates a statement in an existing policy for the specified bot alias 
         * that allows a role to invoke lex:RecognizeText on it.
         * This request expects to update revision 2 of the policy. The request will fail
         * if the current revision of the policy is no longer revision 2.
         * After this request, the revision id for this policy will be 3.
         */
        
        CreateResourcePolicyStatementRequest createStatementRequest =
                CreateResourcePolicyStatementRequest.builder()
                        .resourceArn("arn:aws:lex:Region:123456789012:bot-alias/MYBOTALIAS/TSTALIASID")
                        .effect("Allow")
                        .principal(Principal.builder().arn("arn:aws:iam::123456789012:role/BotRunner").build())
                        .action("lex:RecognizeText")
                        .statementId("BotRunnerStatement")
                        .expectedRevisionId(2)
                        .build();

        lexmodelsv2Client.createResourcePolicyStatement(createStatementRequest);

        /*
         * Deletes a statement from an existing policy for the specified bot alias by statementId.
         * Since no expectedRevisionId is supplied, the request will remove the statement from
         * the current revision of the policy for the bot alias. 
         * After this request, the revision id for this policy will be 4.
         */
        DeleteResourcePolicyRequest deleteStatementRequest =
                DeleteResourcePolicyRequest.builder()
                        .resourceArn("arn:aws:lex:Region:123456789012:bot-alias/MYBOTALIAS/TSTALIASID")
                        .statementId("BotRunnerStatement")                        
                        .build();

        lexmodelsv2Client.deleteResourcePolicy(deleteStatementRequest);
        
        /*
         * Describe the current policy for the specified bot alias
         * It always returns the current revision.
         */
        DescribeResourcePolicyRequest describePolicyRequest =
                DescribeResourcePolicyRequest.builder()
                        .resourceArn("arn:aws:lex:Region:123456789012:bot-alias/MYBOTALIAS/TSTALIASID")
                        .build();

        lexmodelsv2Client.describeResourcePolicy(describePolicyRequest);
        
        
        /*
         * Delete the current policy for the specified bot alias
         * This request expects to delete revision 3 of the policy. Since the revision id for 
         * this policy is already at 4, this request will fail.
         */
        DeleteResourcePolicyRequest deletePolicyRequest =
                DeleteResourcePolicyRequest.builder()
                        .resourceArn("arn:aws:lex:Region:123456789012:bot-alias/MYBOTALIAS/TSTALIASID")
                        .expectedRevisionId(3);
                        .build();

        lexmodelsv2Client.deleteResourcePolicy(deletePolicyRequest);
```

------

## Allow an IAM role to update a bot and list bot aliases<a name="security_iam_resource-based-policy-examples-allow-lex-models"></a>

The following example grants permissions for a specific IAM role to call Amazon Lex V2 model building API operations to modify an existing bot\. The user can list aliases for a bot and update the bot, but can't delete the bot or bot aliases\. 

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "botBuilders",
            "Effect": "Allow",
            "Principal": {
                "AWS": "arn:aws:iam::123456789012:role/BotBuilder"
            },
            "Action": [
                "lex:ListBotAliases",
                "lex:UpdateBot"
            ],
            "Resource": [
                "arn:aws:lex:Region:123456789012:bot/MYBOT"
            ]
        }
    ]
}
```

## Allow a user to have a conversation with a bot<a name="security_iam_resource-based-policy-examples-allow-lex-runtime"></a>

The following example grants permission for a specific user to call Amazon Lex V2 runtime API operations on a single alias of a bot\.

The user is specifically denied permission to update or delete the bot alias\.

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "botRunners",
            "Effect": "Allow",
            "Principal": {
                "AWS": "arn:aws:iam::123456789012:user/botRunner"
            },
            "Action": [
                "lex:RecognizeText",
                "lex:RecognizeUtterance",
                "lex:StartConversaion",
                "lex:DeleteSession",
                "lex:GetSession",
                "lex:PutSession"
            ],
            "Resource": [
                "arn:aws:lex:Region:123456789012:bot-alias/MYBOT/MYBOTALIAS"
            ]
        },
        {
            "Sid": "botRunners",
            "Effect": "Deny",
            "Principal": {
                "AWS": "arn:aws:iam::123456789012:user/botRunner"
            },
            "Action": [
                "lex:UpdateBotAlias",
                "lex:DeleteBotAlias"
            ],
            "Resource": [
                "arn:aws:lex:Region:123456789012:bot-alias/MYBOT/MYBOTALIAS"
            ]
        }
    ]
}
```

## Allow an AWS service to use a specific Amazon Lex V2 bot<a name="security_iam_resource-based-policy-examples-allow-lex-connect"></a>

The following example grants permission for AWS Lambda and Amazon Connect to call Amazon Lex V2 runtime API operations\.

The condition block is required for service principals, and must use the global context keys `AWS:SourceAccount` and `AWS:SourceArn`\. 

The `AWS:SourceAccount` is the account ID that is calling the Amazon Lex V2 bot\.

The `AWS:SourceArn` is the resource ARN of the Amazon Connect service instance or Lambda function that the call to the Amazon Lex V2 bot alias originates from\.

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "connect-bot-alias",
            "Effect": "Allow",
            "Principal": {
                "Service": [
                    "connect.amazonaws.com"
                ]
            },
            "Action": [
                "lex:RecognizeText",
                "lex:StartConversation"
            ],
            "Resource": [
                "arn:aws:lex:Region:123456789012:bot-alias/MYBOT/MYBOTALIAS"
            ],
            "Condition": {
                "StringEquals": {
                    "AWS:SourceAccount": "123456789012"
                },
                "ArnEquals": {
                    "AWS:SourceArn": "arn:aws:connect:Region:123456789012:instance/instance-id"
                }
            }
        },
        {
            "Sid": "lambda-function",
            "Effect": "Allow",
            "Principal": {
                "Service": [
                    "lambda.amazonaws.com"
                ]
            },
            "Action": [
                "lex:RecognizeText",
                "lex:StartConversation"
            ],
            "Resource": [
                "arn:aws:lex:Region:123456789012:bot-alias/MYBOT/MYBOTALIAS"
            ],
            "Condition": {
                "StringEquals": {
                    "AWS:SourceAccount": "123456789012"
                },
                "ArnEquals": {
                    "AWS:SourceArn": "arn:aws:lambda:Region:123456789012:function/function-name"
                }
            }
        }
    ]
}
```