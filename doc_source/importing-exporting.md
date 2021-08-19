# Importing and exporting bots<a name="importing-exporting"></a>

You can export a bot definition or a bot locale and then import it back to create a new bot or to overwrite an existing bot in an AWS account\. For example, you can export a bot from a test account and then create a copy of the bot in your production account\. You can also copy a bot from one AWS Region to another Region\. 

You can change the resources of the exported bot or bot locale before importing it\. For example, you can export a bot and then edit the JSON file for a slot to add or remove slot value elicitation utterances from a specific slot\. After you finish editing the definition, you can import the modified file\.

**Topics**
+ [Exporting a bot or bot locale](export.md)
+ [Importing a bot or bot locale](import.md)
+ [Using a password when importing or exporting](import-export-password.md)
+ [JSON format for importing and exporting](import-export-format.md)