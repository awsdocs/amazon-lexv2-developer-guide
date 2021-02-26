# Managing sessions with the Amazon Lex API<a name="using-sessions"></a>

When a user starts a conversation with your bot, Amazon Lex creates a *session*\. The information exchanged between your application and Amazon Lex makes up the session state for the conversation\. When you make a request, the session is identified by an identifier that you specify\. For more information about the session identifier, see the `sessionId` field in the [RecognizeText](API_runtime_RecognizeText.md) or [RecognizeUtterance](API_runtime_RecognizeUtterance.md) operation\.

You can modify the session state sent between your application and your bot\. For example, you can create and modify session attributes that contain custom information about the session, and you can change the flow of the conversation by setting the dialog context to interpret the next utterance\.

There are three ways that you can update session state\. 
+ Pass the session information inline as part of a call to the `RecognizeText` or `RecognizeUtterance` operation\.
+ Use a Lambda function with the `RecognizeText` or `RecognizeUtterance` operation that is called after each turn of the conversation\. For more information, see [Using a AWS Lambda function](lambda.md)\. The other is to use the Amazon Lex runtime API in your application to make changes to the session state\. 
+ Use operations that enable you to manage session information for a conversation with your bot\. The operations are the [PutSession](API_runtime_PutSession.md) operation, the [GetSession](API_runtime_GetSession.md) operation, and the [DeleteSession](API_runtime_DeleteSession.md) operation\. You use these operations to get information about the state of your user's session with your bot, and to have fine\-grained control over the state\.

Use the `GetSession` operation when you want to get the current state of the session\. The operation returns the current state of the session, including the state of the dialog with your user, any session attributes that have been set and slot values for the current intent and any other intents that Amazon Lex has identified as possible intents that match the user's utterance\.

The `PutSession` operation enables you to directly manipulate the current session state\. You can set the session, including the type of dialog action that the bot will perform next and the messages that Amazon Lex sends to the user\. This gives you control over the flow of the conversation with the bot\. Set the dialog action `type` field to `Delegate` to have Amazon Lex determine the next action for the bot\.

You can use the `PutSession` operation to create a new session with a bot and set the intent that the bot should start with\. You can also use the `PutSession` operation to change from one intent to another\. When you create a session or change the intent you also can set session state, such as slot values and session attributes\. When the new intent is finished, you have the option of restarting the prior intent\. 

The response from the `PutSession` operation contains the same information as the `RecognizeUtterance` operation\. You can use this information to prompt the user for the next piece of information, just as you would with the response from the `RecognizeUtterance` operation\.

Use the `DeleteSession` operation to remove an existing session and start over with a new session\. For example, when you are testing your bot you can use the `DeleteSession` operation to remove test sessions from your bot\.

The session operations work with your fulfillment Lambda functions\. For example, if your Lambda function returns `Failed` as the fulfillment state you can use the `PutSession` operation to set the dialog action type to `close` and `fulfillmentState` to `ReadyForFulfillment` to retry the fulfillment step\.

Here are some things that you can do with the session operations:
+ Have the bot start a conversation instead of waiting for the user\.
+ Switch intents during a conversation\.
+ Return to a previous intent\.
+ Start or restart a conversation in the middle of the interaction\.
+ Validate slot values and have the bot re\-prompt for values that are not valid\.

Each of these are described further below\.

## Starting a new session<a name="session-start"></a>

If you want to have the bot start the conversation with your user, you can use the `PutSession` operation\. 
+ Create a welcome intent with no slots and a conclusion message that prompts the user to state an intent\. For example, "What would you like to order? You can say 'Order a drink' or 'Order a pizza\.'"
+ Call the `PutSession` operation\. Set the intent name to the name of your welcome intent and set the dialog action to `Delegate`\. 
+ Amazon Lex will respond with the prompt from your welcome intent to start the conversation with your user\.

## Switching intents<a name="session-switch"></a>

You can use the `PutSession` operation to switch from one intent to another\. You can also use it to switch back to a previous intent\. You can use the `PutSession` operation to set session attributes or slot values for the new intent\.
+ Call the `PutSession` operation\. Set the intent name to the name of the new intent and set the dialog action to `Delegate`\. You can also set any slot values or session attributes required for the new intent\.
+ Amazon Lex will start a conversation with the user using the new intent\.

## Resuming a prior intent<a name="session-return"></a>

To resume a prior intent you use the `GetSession` operation to get the state of the intent, perform the needed interaction, and then use the `PutSession` operation to set the intent to its previous dialog state\.
+ Call the `GetSession` operation\. Store the state of the intent\.
+ Perform another interaction, such as fulfilling a different intent\.
+ Using the information saved information for the previous intent, call the `PutSession` operation\. This will return the user to the previous intent in the same place in the conversation\.

In some cases it may be necessary to resume your user's conversation with your bot\. For example, say that you have created a customer service bot\. Your application determines that the user needs to talk to a customer service representative\. After talking to the user, the representative can direct the conversation back to the bot with the information that they collected\.

To resume a session, use steps similar to these:
+ Your application determines that the user needs to speak to a customer service representative\.
+ Use the `GetSession` operation to get the current dialog state of the intent\. 
+ The customer service representative talks to the user and resolves the issue\.
+ Use the `PutSession` operation to set the dialog state of the intent\. This may include setting slot values, setting session attributes, or changing the intent\.
+ The bot resumes the conversation with the user\.

## Validating slot values<a name="session-validation"></a>

You can validate responses to your bot using your client application\. If the response isn't valid, you can use the `PutSession` operation to get a new response from your user\. For example, suppose that your flower ordering bot can only sell tulips, roses, and lilies\. If the user orders carnations, your application can do the following:
+ Examine the slot value returned from the `PostText` or `PostContent` response\.
+ If the slot value is not valid, call the `PutSession` operation\. Your application should clear the slot value, set the `slotToElicit` field, and set the `dialogAction.type` value to `elicitSlot`\. Optionally, you can set the `message` and `messageFormat` fields if you want to change the message that Amazon Lex uses to elicit the slot value\.