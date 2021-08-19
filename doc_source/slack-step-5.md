# Step 5: Complete Slack integration<a name="slack-step-5"></a>

In this section, use the Slack API console to complete integration with the Slack application\.

**To complete Slack application integration**

1. Sign in to the Slack API console at [http://api\.slack\.com](http://api.slack.com)\. Choose the app that you created in [Step 3: Create a Slack application](slack-step-3.md)\.

1. Update the **OAuth & Permissions** feature as follows:

   1. In the left menu, choose **OAuth & Permissions**\.

   1. In the **Redirect URLs** section, add the OAuth endpoint that Amazon Lex provided in the preceding step\. Choose **Add a new Redirect URL**, and then choose **Save URLs**\.

   1. In the **Bot Token Scopes** section, add two permissions with the **Add an OAuth Scope** button\. Filter the list with the following text:
      + **chat:write**
      + **team:read**

1. Update the **Interactivity & Shortcuts** feature by updating the **Request URL** value to the endpoint that Amazon Lex provided in the preceding step\. Enter the endpoint that you saved in step 4, and then choose **Save Changes**\.

1. Subscribe to the **Event Subscriptions** feature as follows:
   + Enable events by choosing the **On** option\.
   + Set the **Request URL** value to the endpoint that Amazon Lex provided in the preceding step\. 
   + In the **Subscribe to Bot Events** section, subscribe to the `message.im` bot event to enable direct messaging between the end user and the Slack bot\.
   + Save the changes\.

1. Enable sending messages from the messages tab as follows:
   + From the left menu, choose **App Home**\.
   + In the **Show Tabs** section, choose **Allow users to send Slash commands and messages from the messages tab\.**

## Next step<a name="step-5-next"></a>

[Step 6: Test the integration](slack-step-6.md)