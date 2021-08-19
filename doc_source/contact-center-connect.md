# Amazon Connect<a name="contact-center-connect"></a>

Amazon Connect is an omnichannel cloud contact center\. You can set up a contact center in a new steps, add agents located anywhere, and start engaging with your customers\. For more information, see [ Get started with Amazon Connect ](https://docs.aws.amazon.com/connect/latest/adminguide/amazon-connect-get-started.html) in the *Amazon Connect administrator guide*\.

You can create personalized experiences for your customers use omnichannel communications\. For example, you can offer chat and voice contact based on customer preference and estimated wait times\. Meanwhile agents can handle all customers from just one interface\. For example, they can chat with customers, and create or respond to tasks as they are routed to them\.

You can use Amazon Connect for audio interactions with your customers, or Amazon Connect Chat for text\-only interactions\.

For more information, see the following topics in the *Amazon Connect administrator guide*\.
+ [What is Amazon Connect ](https://docs.aws.amazon.com/connect/latest/adminguide/what-is-amazon-connect.html)
+ [Add an Amazon Lex V2 bot ](https://docs.aws.amazon.com/connect/latest/adminguide/amazon-lex.html)
+ [Amazon Connect get customer input contact block](https://docs.aws.amazon.com/connect/latest/adminguide/get-customer-input.html)

When a contact center sends a request to Amazon Lex V2, it includes platform\-specific information as a request attribute to your Lambda function and conversation logs\. Use this information to determine which contact center application is sending traffic to your bot\.


**Common request attribute**  

| Attribute | Value | 
| --- | --- | 
| x\-amz\-lex:channels:platform | One of the following values: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/lexv2/latest/dg/contact-center-connect.html) | 