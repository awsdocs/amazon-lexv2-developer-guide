# Aliases<a name="aliases"></a>

Amazon Lex V2 bots support aliases\. An *alias* is a pointer to a specific version of a bot\. With an alias, you can easily update the version that your client applications are using\. For example, you can point an alias to version 1 of your bot\. When you are ready to update the bot, you publish version 2 and change the alias to point to the new version\. Because your applications use the alias instead of a specific version, all of your clients get the new functionality without needing to be updated\.

An alias is a pointer to a specific version of an Amazon Lex V2 bot\. Use an alias to allow client applications to use a specific version of the bot without requiring the application to track which version that is\.

When you create a bot, Amazon Lex V2 creates an alias called `TestBotAlias` that you can use for testing your bot\. The `TestBotAlias` alias is always associated with the `Draft` version of your bot\. You should only use the `TestBotAlias` alias for testing, Amazon Lex V2 limits the number of runtime requests that you can make to the alias\.

The following example shows two versions of an Amazon Lex V2 bot, version version 1 and version 2\. Each of these bot versions has an associated alias, BETA and PROD, respectively\. Client applications use the PROD alias to access the bot\.

![\[Point a client application to a version by using an alias.\]](http://docs.aws.amazon.com/lexv2/latest/dg/images/lex-publish-alias-bot.png) 

When you create a second version of the bot, you can update the alias to point to the new version of the bot using the console or the [UpdateBotAlias](API_UpdateBotAlias.md) operation\. When you change the alias, all of your client applications use the new version\. If there is a problem with the new version, you can roll back to the previous version by simply changing the alias to point to that version\.

![\[Updating an alias changes the version used by client applications.\]](http://docs.aws.amazon.com/lexv2/latest/dg/images/lex-publish-alias-bot-v2.png) 

**Note**  
Although you can test the `Draft` version of a bot in the console, we recommend that when you integrate a bot with your client application, you first publish a version and create an alias that points to that version\. Use the alias in your client application for the reasons explained in this section\. When you update an alias, Amazon Lex V2 will use the current version for all in\-progress sessions\. New sessions use the new version\.