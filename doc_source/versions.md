# Creating versions<a name="versions"></a>

Amazon Lex supports publishing versions of bots so that you can control the implementation that your client applications use\. A *version* is a numbered snapshot of your work that you can publish for use in different parts of your workflow, such as development, beta deployment, and production\.

## The Draft version<a name="versioning-intro-create-function"></a>

When you create an Amazon Lex bot there is only one version, the `Draft` version\. 

`Draft` is the working copy of your bot\. You can update only the `Draft` version and until you publish your first version, `Draft` is the only version of the bot that you have\. 

The `Draft` version of your bot is associated with the `TestBotAlias`\. The `TestBotAlias` should only be used for manual testing\. Amazon Lex limits the number of runtime requests that you can make to the `TestBotAlias` alias of the bot\.

## Creating a version<a name="versioning-intro-creating"></a>

When you version an Amazon Lex bot you create a numbered snapshot of the bot so that you can use the bot as it existed when the version was made\. Once you've created a numeric version it will stay the same while you continue to work on the draft version of your application\.

When you create a version, you can choose the locales to include in the version\. You don't need to choose all of the locales in a bot\. Also, when you create a version you can choose a locale from a previous version\. For example, if you have three versions of a bot, you can choose one locale from the `Draft` version and one from version two when you create version four\.

If you delete a lcoale from the `Draft` version, it is not deleted from a numbered version\.

If a bot version is not used for six months, Amazon Lex will mark the version inactive\. When a version is inactive, you can't use runtime operations with the bot\. To make the bot active, rebuild all the languages associated with the version\.

## Updating an Amazon Lex bot<a name="versioning-intro-updating-function-code"></a>

You can update only the `Draft` version of an Amazon Lex bot\. Versions can't be changed\. You can publish a new version any time after you update a resource in the console or with the [CreateBotVersion](API_CreateBotVersion.md) operation\.

## Deleting an Amazon Lex bot or version<a name="versioning-intro-deleting-function-versions"></a>

Amazon Lex supports deleting a bot or version using the console or one of the API operations:
+  [DeleteBot](API_DeleteBot.md) 
+  [DeleteBotVersion](API_DeleteBotVersion.md) 