# Adding a language<a name="build-language"></a>

You add one or more languages and locales to your bot to enable it to communicate with users in their languages\. You define the intents, slots, and slot types separately for each language so that the utterances, prompts, and slot values are specific to the language\.

Your bot must contain at least one language\.

**To add a language to your bot**

1. In the **New language** section, choose the language that you want to use\. You can add a description to help identify the language in lists\.

1. If your bot supports voice interaction, in the **Voice interaction** section, choose the Amazon Polly voice that Amazon Lex V2 uses to communicate with the user\. If your bot doesn't support voice, choose **None**\.

1. For the **Intent classification confidence score threshold**, set the value that Amazon Lex V2 uses to determine whether an intent is the correct intent\. You can adjust this value after testing your bot\.

1. Choose **Add**\.