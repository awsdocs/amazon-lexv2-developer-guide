# Adding slot types<a name="build-slot-types"></a>

Slot types define the values that users can supply for your intent variables\. You define slot types for each language so that the values are specific to that language\. For example, for a slot type that lists paint colors, you could include the value "red" in English, "rouge" in French, and "rojo" in Spanish\.

This topic describes how to create custom slot types that provide values for your intent's slots\. You can also use built\-in slot types for standard values\. For example, you can use the built\-in slot type AMAZON\.Country for a list of countries in the world\. 

**To create a slot type**

1. Sign in to the AWS Management Console and open the Amazon Lex V2 console at [ https://console\.aws\.amazon\.com/lexv2/ ](https://console.aws.amazon.com/lexv2/)

1. From the list of bots, choose the bot that you want to add the language to, then choose **Conversation structure** and then **All languages**\.

1. Choose the language to add the slot type to, then choose **Slot types**\.

1. Choose **Add slot type**, give your slot type a name, and then choose **Add**\.

1. In the slot type editor, add the details of your slot type\.
   + **Slot value resolution** – Determines how slot values are resolved\. If you choose **Expand values**, Amazon Lex V2 uses the values as representative values for training\. If you use **Restrict to slot values** the allowed values for the slot are restricted to the ones that you provide\.
   + **Slot type values** – The values for the slot\. If you chose **Restrict to slot values**, you can add synonyms for the value\. For example, for the value "football" you can add the synonym "soccer\." If the user enters "soccer" in a conversation with your bot, the actual value of the slot is "football\."

1. Choose **Save slot type**\.