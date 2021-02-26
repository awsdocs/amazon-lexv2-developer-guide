# Using a Java application to interact with an Amazon Lex bot<a name="deploy-java"></a>

The AWS SDK for Java provides an interface that you can use from your Java applications to interact with your bots\. Use the SDK for Java to build client applications for users\. 

The following application interacts with the OrderFlowers bot that you created in [Exercise 1: Create a bot from an example](exercise-1.md)\. It uses the `LexRuntimeV2Client` from the SDK for Java to call the [RecognizeText](API_runtime_RecognizeText.md) operation to conduct a conversation with the bot\. 

The output from the conversation looks like this:

```
User : I would like to order flowers
Bot  : What type of flowers would you like to order?
User : 1 dozen roses
Bot  : What day do you want the dozen roses to be picked up?
User : Next Monday
Bot  : At what time do you want the dozen roses to be picked up?
User : 5 in the evening
Bot  : Okay, your dozen roses will be ready for pickup by 17:00 on 2021-01-04.  Does this sound okay?
User : Yes
Bot  : Thanks.
```

For the JSON structures that are sent between the client application and the Amazon Lex bot, see [Exercise 2: Review the conversation flow](exercise-2.md)\.

To run the application, you must provide the following information:
+ botId – The identifier assigned to the bot when you created it\. You can see the bot ID in the Amazon Lex console on the bot **Settings** page\.
+ botAliasId – The identifier assigned to the bot alias when you created it\. You can see the bot alias ID in the Amazon Lex console on the **Aliases** page\. If you can't see the alias ID in the list, choose the gear icon on the upper right and turn on **Alias ID**\.
+ localeId – The identifier of the locale that you used for your bot\. For a list of locales, see [Languages and locales supported by Amazon Lex](how-languages.md)\.
+ accessKey and secretKey – The authentication keys for your account\. If you don't have a set of keys, create them using the AWS Identity and Access Management console\.
+ sessionId – An identifier for the session with the Amazon Lex bot\. In this case, the code uses a random UUID\.
+ region – If your bot is not in the US East \(N\. Virginia\) Region, make sure that you change the Region\.

The applications uses a function called `getRecognizeTextRequest` to create individual requests to the bot\. The function builds a request with the required parameters to send to Amazon Lex\.

```
package com.lex.recognizetext.sample;

import software.amazon.awssdk.auth.credentials.AwsBasicCredentials;
import software.amazon.awssdk.auth.credentials.AwsCredentialsProvider;
import software.amazon.awssdk.auth.credentials.StaticCredentialsProvider;
import software.amazon.awssdk.regions.Region;
import software.amazon.awssdk.services.lexruntimev2.LexRuntimeV2Client;
import software.amazon.awssdk.services.lexruntimev2.model.RecognizeTextRequest;
import software.amazon.awssdk.services.lexruntimev2.model.RecognizeTextResponse;

import java.net.URISyntaxException;
import java.util.UUID;


/**
 * This is a sample application to interact with a bot using RecognizeText API.
 */
public class OrderFlowersSampleApplication {

    public static void main(String[] args) throws URISyntaxException, InterruptedException {
        String botId = "";
        String botAliasId = "";
        String localeId = "en_US";
        String accessKey = "";
        String secretKey = "";
        String sessionId = UUID.randomUUID().toString();
        Region region = Region.US_EAST_1; // pick an appropriate region

        AwsBasicCredentials awsCreds = AwsBasicCredentials.create(accessKey, secretKey);
        AwsCredentialsProvider awsCredentialsProvider = StaticCredentialsProvider.create(awsCreds);

        LexRuntimeV2Client lexV2Client = LexRuntimeV2Client
                .builder()
                .credentialsProvider(awsCredentialsProvider)
                .region(region)
                .build();

        // utterance 1
        String userInput = "I would like to order flowers";
        RecognizeTextRequest recognizeTextRequest = getRecognizeTextRequest(botId, botAliasId, localeId, sessionId, userInput);
        RecognizeTextResponse recognizeTextResponse = lexV2Client.recognizeText(recognizeTextRequest);

        System.out.println("User : " + userInput);
        recognizeTextResponse.messages().forEach(message -> {
            System.out.println("Bot : " + message.content());
        });

        // utterance 2
        userInput = "1 dozen roses";
        recognizeTextRequest = getRecognizeTextRequest(botId, botAliasId, localeId, sessionId, userInput);
        recognizeTextResponse = lexV2Client.recognizeText(recognizeTextRequest);

        System.out.println("User : " + userInput);
        recognizeTextResponse.messages().forEach(message -> {
            System.out.println("Bot : " + message.content());
        });

        // utterance 3
        userInput = "next monday";
        recognizeTextRequest = getRecognizeTextRequest(botId, botAliasId, localeId, sessionId, userInput);
        recognizeTextResponse = lexV2Client.recognizeText(recognizeTextRequest);

        System.out.println("User : " + userInput);
        recognizeTextResponse.messages().forEach(message -> {
            System.out.println("Bot : " + message.content());
        });

        // utterance 4
        userInput = "5 in evening";
        recognizeTextRequest = getRecognizeTextRequest(botId, botAliasId, localeId, sessionId, userInput);
        recognizeTextResponse = lexV2Client.recognizeText(recognizeTextRequest);

        System.out.println("User : " + userInput);
        recognizeTextResponse.messages().forEach(message -> {
            System.out.println("Bot : " + message.content());
        });

        // utterance 5
        userInput = "Yes";
        recognizeTextRequest = getRecognizeTextRequest(botId, botAliasId, localeId, sessionId, userInput);
        recognizeTextResponse = lexV2Client.recognizeText(recognizeTextRequest);

        System.out.println("User : " + userInput);
        recognizeTextResponse.messages().forEach(message -> {
            System.out.println("Bot : " + message.content());
        });
    }

    private static RecognizeTextRequest getRecognizeTextRequest(String botId, String botAliasId, String localeId, String sessionId, String userInput) {
        RecognizeTextRequest recognizeTextRequest = RecognizeTextRequest.builder()
                .botAliasId(botAliasId)
                .botId(botId)
                .localeId(localeId)
                .sessionId(sessionId)
                .text(userInput)
                .build();
        return recognizeTextRequest;
    }
}
```