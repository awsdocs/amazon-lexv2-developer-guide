# AMAZON\.FallbackIntent<a name="built-in-intent-fallback"></a>

When a user's input to an intent isn't what a bot expects, you can configure Amazon Lex to invoke a *fallback intent*\. For example, if the user input "I'd like to order candy" doesn't match an intent in your `OrderFlowers` bot, Amazon Lex invokes the fallback intent to handle the response\.

The built\-in `AMAZON.FallbackIntent` intent type is added to your bot automatically when you create a bot using the console, when you use the API you can specify the intent using the [CreateBot](API_CreateBot.md) operation\. 

Invoking a fallback intent uses two steps\. In the first step the fallback intent is matched based on the input from the user\. When the fallback intent is matched, the way the bot behaves depends on the number of retries configured for a prompt\. 

Amazon Lex matches the fallback intent in these situations: 
+ The user's input to an intent doesn't match the input that the bot expects
+ Audio input is noise, or text input isn't recognized as words\.
+ The user's input is ambiguous and Amazon Lex can't determine which intent to invoke\.

The fallback intent is invoked when:
+ The bot doesn't recognize the user input as an intent after the configured number of tries for clarification when the conversation is started\.
+ An intent doesn't recognize the user input as a slot value after the configured number of tries\.
+ An intent doesn't recognize the user input as a response to a confirmation prompt after the configured number of tries\.

You can't add the following to a fallback intent:
+ Utterances
+ Slots
+ A confirmation prompt

## Using a Lambda Function with a Fallback Intent<a name="invoke-fallback"></a>

When a fallback intent is invoked, the response depends on the setting of the `fulfillmentCodeHook` parameter to the [CreateIntent](API_CreateIntent.md) operation\. The bot does one of the following:
+ Returns the intent information to the client application\.
+ Calls the aliases's validation and fulfillment Lambda function\. It calls the function with the session variables that are set for the session\.

For more information about setting the response when a fallback intent is invoked, see the `fulfillmentCodeHook` parameter of the [CreateIntent](API_CreateIntent.md) operation\. 

If you use the Lambda function with your fallback intent, you can use this function to call another intent or to perform some form of communication with the user, such as collecting a callback number or opening a session with a customer service representative\.

A fallback intent can be invoked multiple times in the same session\. For example, suppose that your Lambda function uses the `ElicitIntent` dialog action to prompt the user for a different intent\. If Amazon Lex can't infer the user's intent after the configured number of tries, it invokes the fallback intent again\. It also invokes the fallback intent when the user doesn't respond with a valid slot value after the configured number of tries\.

You can configure your Lambda function to keep track of the number of times that the fallback intent is called using a session variable\. Your Lambda function can take a different action if it is called more times than the threshold that you set in your Lambda function\. For more information about session variables, see [Setting session attributes](context-mgmt-session-attribs.md)\.