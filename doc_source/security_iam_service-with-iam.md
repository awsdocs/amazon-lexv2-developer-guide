# How Amazon Lex V2 works with IAM<a name="security_iam_service-with-iam"></a>

Before you use IAM to manage access to Amazon Lex V2, learn what IAM features are available to use with Amazon Lex V2\.






**IAM features you can use with Amazon Lex V2**  

| IAM feature | Amazon Lex V2 support | 
| --- | --- | 
|  [Identity\-based policies](#security_iam_service-with-iam-id-based-policies)  |  Yes  | 
|  [Resource\-based policies](#security_iam_service-with-iam-resource-based-policies)  |  Yes  | 
|  [Policy actions](#security_iam_service-with-iam-id-based-policies-actions)  |  Yes  | 
|  [Policy resources](#security_iam_service-with-iam-id-based-policies-resources)  |  Yes  | 
|  [Policy condition keys](#security_iam_service-with-iam-id-based-policies-conditionkeys)  |  No   | 
|  [ACLs](#security_iam_service-with-iam-acls)  |  No   | 
|  [ABAC \(tags in policies\)](#security_iam_service-with-iam-tags)  |  Yes  | 
|  [Temporary credentials](#security_iam_service-with-iam-roles-tempcreds)  |  No   | 
|  [Principal permissions](#security_iam_service-with-iam-principal-permissions)  |  Yes  | 
|  [Service roles](#security_iam_service-with-iam-roles-service)  |  Yes  | 
|  [Service\-linked roles](#security_iam_service-with-iam-roles-service-linked)  |  Partial  | 

To get a high\-level view of how Amazon Lex V2 and other AWS services work with most IAM features, see [AWS services that work with IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_aws-services-that-work-with-iam.html) in the *IAM User Guide*\.

## Identity\-based policies for Amazon Lex V2<a name="security_iam_service-with-iam-id-based-policies"></a>


|  |  | 
| --- |--- |
|  Supports identity\-based policies  |  Yes  | 

Identity\-based policies are JSON permissions policy documents that you can attach to an identity, such as an IAM user, group of users, or role\. These policies control what actions users and roles can perform, on which resources, and under what conditions\. To learn how to create an identity\-based policy, see [Creating IAM policies](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_create.html) in the *IAM User Guide*\.

With IAM identity\-based policies, you can specify allowed or denied actions and resources as well as the conditions under which actions are allowed or denied\. You can't specify the principal in an identity\-based policy because it applies to the user or role to which it is attached\. To learn about all of the elements that you can use in a JSON policy, see [IAM JSON policy elements reference](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_elements.html) in the *IAM User Guide*\.

### Identity\-based policy examples for Amazon Lex V2<a name="security_iam_service-with-iam-id-based-policies-examples"></a>



To view examples of Amazon Lex V2 identity\-based policies, see [Identity\-based policy examples for Amazon Lex V2](security_iam_id-based-policy-examples.md)\.

## Resource\-based policies within Amazon Lex V2<a name="security_iam_service-with-iam-resource-based-policies"></a>


|  |  | 
| --- |--- |
|  Supports resource\-based policies  |  Yes  | 

Resource\-based policies are JSON policy documents that you attach to a resource\. Examples of resource\-based policies are IAM role trust policies and Amazon S3 bucket policies\. In services that support resource\-based policies, service administrators can use them to control access to a specific resource\. For the resource where the policy is attached, the policy defines what actions a specified principal can perform on that resource and under what conditions\. You must [specify a principal](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_elements_principal.html) in a resource\-based policy\. Principals can include users, roles, federated users, or AWS services\.

You can't use cross\-account or cross\-region policies with Amazon Lex\. If you create a policy for a resource with a cross\-account or cross\-region ARN, Amazon Lex returns an error\.

The Amazon Lex service supports resource\-based policies called a *bot policy* and a *bot alias* policy, which are attached to a bot or a bot alias\. These policies define which principals can perform actions on the bot or bot alias\. 

Actions can only be used on specific resources\. For example, the `UpdateBot` action can only be used on bot resources, the `UpdateBotAlias` action can only be used on bot alias resources\. If you specify an action in a policy that can't be used on the resource specified in the policy, Amazon Lex returns an error\. For the list of actions and the resources that they can be used with, see the following table\.


| Action | Supports resource\-based policy | Resource | 
| --- | --- | --- | 
| BuildBotLocale | Supported | BotId | 
| CreateBot | No |   | 
| CreateBotAlias | No |   | 
| CreateBotChannel \[permission only\] | Supported | BotId | 
| CreateBotLocale | Supported | BotId | 
| CreateBotVersion | Supported | BotId | 
| CreateExport | Supported | BotId | 
| CreateIntent | Supported | BotId | 
| CreateResourcePolicy | Supported | BotId, BotAliasId | 
| CreateSlot | Supported | BotId | 
| CreateSlotType | Supported | BotId | 
| CreateUploadUrl | No |   | 
| DeleteBot | Supported | BotId, BotAliasId | 
| DeleteBotAlias | Supported | BotAliasId | 
| DeleteBotChannel \[permission only\] | Supported | BotId | 
| DeleteBotLocale | Supported | BotId | 
| DeleteBotVersion | Supported | BotId | 
| DeleteExport | Supported | BotId | 
| DeleteImport | Supported | BotId | 
| DeleteIntent | Supported | BotId | 
| DeleteResourcePolicy | Supported | BotId, BotAliasId | 
| DeleteSession | Supported | BotAliasId | 
| DeleteSlot | Supported | BotId | 
| DeleteSlotType | Supported | BotId | 
| DescribeBot | Supported | BotId | 
| DescribeBotAlias | Supported | BotAliasId | 
| DescribeBotChannel \[permission only\] | Supported | BotId | 
| DescribeBotLocale | Supported | BotId | 
| DescribeBotVersion | Supported | BotId | 
| DescribeExport | Supported | BotId | 
| DescribeImport | Supported | BotId | 
| DescribeIntent | Supported | BotId | 
| DescribeResourcePolicy | Supported | BotId, BotAliasId | 
| DescribeSlot | Supported | BotId | 
| DescribeSlotType | Supported | BotId | 
| GetSession | Supported | BotAliasId | 
| ListBotAliases | Supported | BotAliasId | 
| ListBotChannels \[permission only\] | Supported | BotId | 
| ListBotLocales | Supported | BotId | 
| ListBots | No |   | 
| ListBotVersions | Supported | BotId | 
| ListBuiltInIntents | No |   | 
| ListBuiltIntSlotTypes | No |   | 
| ListExports | No |   | 
| ListImports | No |   | 
| ListIntents | Supported | BotId | 
| ListSlots | Supported | BotId | 
| ListSlotTypes | Supported | BotId | 
| PutSession | Supported | BotAliasId | 
| RecognizeText | Supported | BotAliasId | 
| RecognizeUtterance | Supported | BotAliasId | 
| StartConversation | Supported | BotAliasId | 
| StartImport | Supported | BotId, BotAliasId | 
| TagResource | No |   | 
| UpdateBot | Supported | BotId | 
| UpdateBotAlias | Supported | BotAliasId | 
| UpdateBotLocale | Supported | BotId | 
| UpdateBotVersion | Supported | BotId | 
| UpdateExport | Supported | BotId | 
| UpdateIntent | Supported | BotId | 
| UpdateResourcePolicy | Supported | BotId, BotAliasId | 
| UpdateSlot | Supported | BotId | 
| UpdateSlotType | Supported | BotId | 
| UntagResource | No |   | 

To learn how to attach a resource\-based policy to a bot or bot alias, see [Resource\-based policy examples for Amazon Lex V2](security_iam_resource-based-policy-examples.md)\.

### Resource\-based policy examples within Amazon Lex V2<a name="security_iam_service-with-iam-resource-based-policies-examples"></a>



To view examples of Amazon Lex V2 resource\-based policies, see [Resource\-based policy examples for Amazon Lex V2](security_iam_resource-based-policy-examples.md)\.

## Policy actions for Amazon Lex V2<a name="security_iam_service-with-iam-id-based-policies-actions"></a>


|  |  | 
| --- |--- |
|  Supports policy actions  |  Yes  | 

Administrators can use AWS JSON policies to specify who has access to what\. That is, which **principal** can perform **actions** on what **resources**, and under what **conditions**\.

The `Action` element of a JSON policy describes the actions that you can use to allow or deny access in a policy\. Policy actions usually have the same name as the associated AWS API operation\. There are some exceptions, such as *permission\-only actions* that don't have a matching API operation\. There are also some operations that require multiple actions in a policy\. These additional actions are called *dependent actions*\.

Include actions in a policy to grant permissions to perform the associated operation\.



To see a list of Amazon Lex V2 actions, see [Actions defined by Amazon Lex V2](https://docs.aws.amazon.com/service-authorization/latest/reference/list_amazonlexv2.html#awskeymanagementservice-actions-as-permissions) in the *Service Authorization Reference*\.

Policy actions in Amazon Lex V2 use the following prefix before the action:

```
lex
```

To specify multiple actions in a single statement, separate them with commas\.

```
"Action": [
      "lex:action1",
      "lex:action2"
         ]
```





To view examples of Amazon Lex V2 identity\-based policies, see [Identity\-based policy examples for Amazon Lex V2](security_iam_id-based-policy-examples.md)\.

## Policy resources for Amazon Lex V2<a name="security_iam_service-with-iam-id-based-policies-resources"></a>


|  |  | 
| --- |--- |
|  Supports policy resources  |  Yes  | 

Administrators can use AWS JSON policies to specify who has access to what\. That is, which **principal** can perform **actions** on what **resources**, and under what **conditions**\.

The `Resource` JSON policy element specifies the object or objects to which the action applies\. Statements must include either a `Resource` or a `NotResource` element\. As a best practice, specify a resource using its [Amazon Resource Name \(ARN\)](https://docs.aws.amazon.com/general/latest/gr/aws-arns-and-namespaces.html)\. You can do this for actions that support a specific resource type, known as *resource\-level permissions*\.

For actions that don't support resource\-level permissions, such as listing operations, use a wildcard \(\*\) to indicate that the statement applies to all resources\.

```
"Resource": "*"
```

To see a list of Amazon Lex V2 resource types and their ARNs, see [Resources defined by Amazon Lex V2](https://docs.aws.amazon.com/service-authorization/latest/reference/list_amazonlexv2.html#awskeymanagementservice-resources-for-iam-policies) in the *Service Authorization Reference*\. To learn with which actions you can specify the ARN of each resource, see [Actions defined by Amazon Lex V2](https://docs.aws.amazon.com/service-authorization/latest/reference/list_amazonlexv2.html#awskeymanagementservice-actions-as-permissions)\.





To view examples of Amazon Lex V2 identity\-based policies, see [Identity\-based policy examples for Amazon Lex V2](security_iam_id-based-policy-examples.md)\.

## Policy condition keys for Amazon Lex V2<a name="security_iam_service-with-iam-id-based-policies-conditionkeys"></a>


|  |  | 
| --- |--- |
|  Supports policy condition keys  |  No   | 

Administrators can use AWS JSON policies to specify who has access to what\. That is, which **principal** can perform **actions** on what **resources**, and under what **conditions**\.

The `Condition` element \(or `Condition` *block*\) lets you specify conditions in which a statement is in effect\. The `Condition` element is optional\. You can create conditional expressions that use [condition operators](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_elements_condition_operators.html), such as equals or less than, to match the condition in the policy with values in the request\. 

If you specify multiple `Condition` elements in a statement, or multiple keys in a single `Condition` element, AWS evaluates them using a logical `AND` operation\. If you specify multiple values for a single condition key, AWS evaluates the condition using a logical `OR` operation\. All of the conditions must be met before the statement's permissions are granted\.

 You can also use placeholder variables when you specify conditions\. For example, you can grant an IAM user permission to access a resource only if it is tagged with their IAM user name\. For more information, see [IAM policy elements: variables and tags](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_variables.html) in the *IAM User Guide*\. 

AWS supports global condition keys and service\-specific condition keys\. To see all AWS global condition keys, see [AWS global condition context keys](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_condition-keys.html) in the *IAM User Guide*\.

To see a list of Amazon Lex V2 condition keys, see [Condition keys for Amazon Lex V2](https://docs.aws.amazon.com/service-authorization/latest/reference/list_amazonlexv2.html#awskeymanagementservice-policy-keys) in the *Service Authorization Reference*\. To learn with which actions and resources you can use a condition key, see [Actions defined by Amazon Lex V2](https://docs.aws.amazon.com/service-authorization/latest/reference/list_amazonlexv2.html#awskeymanagementservice-actions-as-permissions)\.

To view examples of Amazon Lex V2 identity\-based policies, see [Identity\-based policy examples for Amazon Lex V2](security_iam_id-based-policy-examples.md)\.

## Access control lists \(ACLs\) in Amazon Lex V2<a name="security_iam_service-with-iam-acls"></a>


|  |  | 
| --- |--- |
|  Supports ACLs  |  No   | 

Access control lists \(ACLs\) control which principals \(account members, users, or roles\) have permissions to access a resource\. ACLs are similar to resource\-based policies, although they do not use the JSON policy document format\.

## Attribute\-based access control \(ABAC\) with Amazon Lex V2<a name="security_iam_service-with-iam-tags"></a>


|  |  | 
| --- |--- |
|  Supports ABAC \(tags in policies\)  |  Yes  | 

Attribute\-based access control \(ABAC\) is an authorization strategy that defines permissions based on attributes\. In AWS, these attributes are called *tags*\. You can attach tags to IAM entities \(users or roles\) and to many AWS resources\. Tagging entities and resources is the first step of ABAC\. Then you design ABAC policies to allow operations when the principal's tag matches the tag on the resource that they are trying to access\.

ABAC is helpful in environments that are growing rapidly and helps with situations where policy management becomes cumbersome\.

To control access based on tags, you provide tag information in the [condition element](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_elements_condition.html) of a policy using the `aws:ResourceTag/key-name`, `aws:RequestTag/key-name`, or `aws:TagKeys` condition keys\.

For more information about ABAC, see [What is ABAC?](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction_attribute-based-access-control.html) in the *IAM User Guide*\. To view a tutorial with steps for setting up ABAC, see [Use attribute\-based access control \(ABAC\)](https://docs.aws.amazon.com/IAM/latest/UserGuide/tutorial_attribute-based-access-control.html) in the *IAM User Guide*\.

## Using Temporary credentials with Amazon Lex V2<a name="security_iam_service-with-iam-roles-tempcreds"></a>


|  |  | 
| --- |--- |
|  Supports temporary credentials  |  No   | 

Some AWS services don't work when you sign in using temporary credentials\. For additional information, including which AWS services work with temporary credentials, see [AWS services that work with IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_aws-services-that-work-with-iam.html) in the *IAM User Guide*\.

You are using temporary credentials if you sign in to the AWS Management Console using any method except a user name and password\. For example, when you access AWS using your company's single sign\-on \(SSO\) link, that process automatically creates temporary credentials\. You also automatically create temporary credentials when you sign in to the console as a user and then switch roles\. For more information about switching roles, see [Switching to a role \(console\)](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_use_switch-role-console.html) in the *IAM User Guide*\.

You can manually create temporary credentials using the AWS CLI or AWS API\. You can then use those temporary credentials to access AWS\. AWS recommends that you dynamically generate temporary credentials instead of using long\-term access keys\. For more information, see [Temporary security credentials in IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_temp.html)\.

## Cross\-service principal permissions for Amazon Lex V2<a name="security_iam_service-with-iam-principal-permissions"></a>


|  |  | 
| --- |--- |
|  Supports principal permissions  |  Yes  | 

  When you use an IAM user or role to perform actions in AWS, you are considered a principal\. Policies grant permissions to a principal\. When you use some services, you might perform an action that then triggers another action in a different service\. In this case, you must have permissions to perform both actions\. To see whether an action requires additional dependent actions in a policy, see [Actions, resources, and condition keys for Amazon Lex V2](https://docs.aws.amazon.com/service-authorization/latest/reference/list_amazonlexv2.html) in the *Service Authorization Reference*\. 

## Service roles for Amazon Lex V2<a name="security_iam_service-with-iam-roles-service"></a>


|  |  | 
| --- |--- |
|  Supports service roles  |  Yes  | 

  A service role is an [IAM role](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles.html) that a service assumes to perform actions on your behalf\. Service roles provide access only within your account and cannot be used to grant access to services in other accounts\. An IAM administrator can create, modify, and delete a service role from within IAM\. For more information, see [Creating a role to delegate permissions to an AWS service](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_create_for-service.html) in the *IAM User Guide*\. 

**Warning**  
Changing the permissions for a service role might break Amazon Lex V2 functionality\. Edit service roles only when Amazon Lex V2 provides guidance to do so\.

## Service\-linked roles for Amazon Lex V2<a name="security_iam_service-with-iam-roles-service-linked"></a>


|  |  | 
| --- |--- |
|  Supports service\-linked roles  |  Partial  | 

  A service\-linked role is a type of service role that is linked to an AWS service\. The service can assume the role to perform an action on your behalf\. Service\-linked roles appear in your IAM account and are owned by the service\. An IAM administrator can view, but not edit the permissions for service\-linked roles\. 

For details about creating or managing service\-linked roles, see [AWS services that work with IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_aws-services-that-work-with-iam.html)\. Find a service in the table that includes a `Yes` in the **Service\-linked role** column\. Choose the **Yes** link to view the service\-linked role documentation for that service\.