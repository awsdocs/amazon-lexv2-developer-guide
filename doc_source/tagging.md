# Tagging resources<a name="tagging"></a>

To help you manage your Amazon Lex V2 bots and bot aliases, you can assign metadata to each resource as *tags*\. A tag is a label that you assign to an AWS resource\. Each tag consists of a key and a value\. 

Tags enable you to categorize your AWS resources in different ways, for example, by purpose, owner, or application\. Tags help you to:
+ Identify and organize your AWS resources\. Many AWS resources support tagging, so you can assign the same tag to resources in different services to indicate that the resources are the same\. For example, you can tag a bot and the Lambda functions that it uses with the same tag\.
+ Allocate costs\. You activate tags on the AWS Billing and Cost Management dashboard\. AWS uses the tags to categorize your costs and deliver a monthly cost allocation report to you\. For Amazon Lex V2, you can allocate costs for each alias using tags specific to the alias\. For more information, see [Use cost allocation tags](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/cost-alloc-tags.html) in the *AWS Billing and Cost Management User Guide*\.
+ Control access to your resources\. You can use tags with Amazon Lex V2 to create policies to control access to Amazon Lex V2 resources These policies can be attached to an IAM role or user to enable tag\-based access control\.

You can work with tags using the AWS Management Console, the AWS Command Line Interface, or the Amazon Lex V2 API\.

## Tagging your resources<a name="tagging-resources"></a>

If you are using the Amazon Lex V2 console, you can tag resources when you create them, or you can add the tags later\. You can also use the console to update or remove existing tags\.

If you are using the AWS CLI or Amazon Lex V2 API, you use the following operations to manage tags for your resource:
+ [CreateBot](API_CreateBot.md) and [CreateBotAlias](API_CreateBotAlias.md) – apply tags when you create a bot or a bot alias\.
+ [ListTagsForResource](API_ListTagsForResource.md) – view the tags associated with a resource\.
+ [TagResource](API_TagResource.md) – add and modify tags on an existing resource\.
+ [UntagResource](API_UntagResource.md) – remove tags from a resource\.

The following resources in Amazon Lex V2 support tagging:
+ Bots – use an Amazon Resource Name \(ARN\) like the following:
  + `arn:aws:lex:${Region}:${account}:bot/${bot-id}`
+ Bot aliases – use an ARN like the following:
  + `arn:aws:lex:${Region}:${account}:bot-alias/${bot-id}/${bot-alias-id}`

The `bot-id` and `bot-alias-id` values are capitalized alphanumeric strings 10 characters long\.

## Tag restrictions<a name="tagging-restrictions"></a>

The following basic restrictions apply to tags on Amazon Lex V2 resources:
+ Maximum number of keys – 50 using the console, 200 using the API
+ Maximum key length – 128 characters
+ Maximum value length – 256 characters
+ Valid characters for key and value – a\-z, A\-Z, 0\-9, space, and the following characters: \_\.:/=\+\- and @
+ Keys and values are case\-sensitive
+ Don't use `aws:` as a prefix for keys, it's reserved for AWS use