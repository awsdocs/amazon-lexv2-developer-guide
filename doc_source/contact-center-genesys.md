# Genesys Cloud<a name="contact-center-genesys"></a>

Genesys Cloud is a suite of cloud services for enterprise communication, collaboration, and contact center management\. Genesys Cloud is built on top of AWS and uses a distributed cloud environment that provides secure access to organizations around the work\.

For more information, see the following pages on the Genesys Cloud website\.
+ [ About Genesys Cloud contact center ](https://help.mypurecloud.com/articles/about-genesys-cloud-contact-center/)
+ [ About the Amazon Lex V2 integration ](https://help.mypurecloud.com/articles/about-the-amazon-lex-v2-integration/)

When a contact center sends a request to Amazon Lex V2 it includes platform\-specific information as a request attribute to your Lambda function and conversation logs\. Use this information to determine which contact center application is sending traffic to your bot\.


**Common request attribute**  

| Attribute | Value | 
| --- | --- | 
| x\-amz\-lex:channels:platform |  [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/lexv2/latest/dg/contact-center-genesys.html) | 

*Learn more*
+ [Power your contact center with Amazon Lex and Genesys Cloud](https://aws.amazon.com/blogs/machine-learning/enhancing-customer-service-experiences-using-conversational-ai-power-your-contact-center-with-amazon-lex-and-genesys-cloud/)