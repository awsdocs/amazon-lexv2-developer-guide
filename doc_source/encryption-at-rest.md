# Encryption at rest<a name="encryption-at-rest"></a>

Amazon Lex encrypts user utterances and other information that it stores\. 

**Topics**
+ [Sample utterances](#at-rest-sample)
+ [Session attributes](#at-rest-session)
+ [Request attributes](#at-rest-request)

## Sample utterances<a name="at-rest-sample"></a>

When you develop a bot, you can provide sample utterances for each intent and slot\. You can also provide custom values and synonyms for slots\. This information is encrypted at rest, and it is used only to build the bot and create the customer experience\.

## Session attributes<a name="at-rest-session"></a>

Session attributes contain application\-specific information that is passed between Amazon Lex and client applications\. Amazon Lex passes session attributes to all AWS Lambda functions configured for a bot\. If a Lambda function adds or updates session attributes, Amazon Lex passes the new information back to the client application\.

Session attributes persist in an encrypted store for the duration of the session\. You can configure the session to remain active for a minimum of 1 minute and up to 24 hours after the last user utterance\. The default session duration is 5 minutes\.

## Request attributes<a name="at-rest-request"></a>

Request attributes contain request\-specific information and apply only to the current request\. A client application uses request attributes to send information to Amazon Lex at runtime\.

You use request attributes to pass information that doesn't need to persist for the entire session\. Because request attributes don't persist across requests, they aren't stored\.