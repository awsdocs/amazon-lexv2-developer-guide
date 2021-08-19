# Importing a bot or bot locale<a name="import"></a>

To use the console to import a previously exported bot or bot locale, you provide the file location on your local computer and the optional password to unlock the file\. For an example, see [Importing a bot \(console\)](import-console.md)\.

When you use the API, importing a bot or bot locale is a three step process:

1. Create an upload URL using the `CreateUploadUrl` operation\. You don't need to create an upload URL when you are using the console\.

1. Upload the \.zip file that contains the bot or bot locale definition\.

1. Start the import with the `StartImport` operation\.

The upload URL is a pre\-signed Amazon S3 URL with write permission\. The URL is available for five minutes after it is generated\. If you password protect the \.zip file, you must provide the password when you start the import\. For more information, see [Using a password when importing or exporting](import-export-password.md)\.

An import is an asynchronous process\. You can monitor the progress of an import using the console or the `DescribeImport` operation\. 

When you import a bot or bot locale, there may be conflicts between resource names in the import file and existing resource names in Amazon Lex V2\. Amazon Lex V2 can handle the conflict in two ways:
+ **Fail on conflict** – The import stops and no resources are imported from the import \.zip file\.
+ **Overwrite** – Amazon Lex V2 imports all of the resources from the import \.zip file, replacing any existing resource with the definition from the import file\.

You can see a list of the imports to a bot or bot locale using the console or the `ListImports` operation\. Imports remain in the list for seven days\. You can use the console or the `DescribeImport` operation to see details about a specific import\.

You can also remove an import and the associated \.zip file using the console or the `DeleteImport` operation\.

For an example of importing a bot using the console, see [Importing a bot \(console\)](import-console.md)\.

## IAM permissions required to import<a name="import-permissions"></a>

To import bots and bot locales, the user running the import must have the following IAM permissions\. 


| API | Required IAM actions | Resource | 
| --- | --- | --- | 
| [CreateUploadUrl](API_CreateUploadUrl.md) | [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/lexv2/latest/dg/import.html) | \* | 
| [StartImport](API_StartImport.md) | [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/lexv2/latest/dg/import.html) | [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/lexv2/latest/dg/import.html) | 
| [DescribeImport](API_DescribeImport.md) | [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/lexv2/latest/dg/import.html) | Bot | 
| [DeleteImport](API_DeleteImport.md) | [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/lexv2/latest/dg/import.html) | Bot | 
| [ListImports](API_ListImports.md) | [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/lexv2/latest/dg/import.html) | \* | 

For an example IAM policy, see [ Allow a user to import bots and bot locales ](security_iam_id-based-policy-examples.md#security_iam_id-based-policy-examples-import)\.