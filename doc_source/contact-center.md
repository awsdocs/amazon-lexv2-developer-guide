# Integrating an Amazon Lex V2 bot with a contact center<a name="contact-center"></a>

You can integrate Amazon Lex V2 bots with your contact centers to enable self\-service use\-cases using the Amazon Lex V2 streaming API\. Use these bots as interactive voice response \(IVR\) agents on telephony or as a text\-based chatbot integrated into your contact center\. For more information about the streaming APIs, see [Streaming to an Amazon Lex V2 bot](streaming.md)\.

With streaming APIs, you can enable the following features:
+ **Interruptions** \("barge\-in"\) – Callers can interrupt the bot and answer a question before the prompt is complete\. For more information, see [Enabling your bot to be interrupted by your user](interrupt-bot.md)\.
+ **Wait and continue** – Callers can instruct the bot to wait if they need time for retrieving additional information during a call, such as a credit card number or a booking ID\. For more information, see [Enabling the bot to wait for the user to provide additional information](wait-and-continue.md)\.
+ **DTMF support** – Callers can provide information via speech or DTMF interchangeably\.
+ **SSML support** – You can configure Amazon Lex V2 bot prompts using SSML tags for greater control over speech generation from text\. For more information, see [ Generating speech from SSML documents ](https://docs.aws.amazon.com/polly/latest/dg/ssml.html) in the *Amazon Polly developer guide*\.
+ **Configurable timeouts** – You can configure how long to wait for customers to finish speaking before Amazon Lex V2 collects their speech input, such as answering a yes or no question, or providing a date or credit card number\. For more information, see [Configuring timeouts for capturing user input](session-attribs-speech.md)\.