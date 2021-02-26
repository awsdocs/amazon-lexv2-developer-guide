# AMAZON\.Time<a name="built-in-slot-time"></a>

Converts words that represent times into time values\. Includes resolutions for ambiguous times\. When a user enters an ambiguous time, Amazon Lex uses the `slots` attribute of a Lambda event to pass resolutions for the ambiguous times to your Lambda function\. For example, if your bot prompts the user for a delivery time, the user can respond by saying "10 o'clock\." This time is ambiguous\. It means either 10:00 AM or 10:00 PM\. In this case, the value in the `interpretedValue` field is `null`, and the `resolvedValues` field contains the two possible resolutions of the time\. Amazon Lex inputs the following into the Lambda function:

```
"slots": {
   "deliveryTime": {
      "value": {
         "originalValue": "10 o'clock",
         "interpretedValue": null,
         "resolvedValues": [
            "10:00", "22:00"
         ]
      }
   }
}
```

When the user responds with an unambiguous time, Amazon Lex sends the time to your Lambda function in the `interpretedValue` field of the `slots` attribute of the Lambda event\. For example, if your user responds to the prompt for a delivery time with "10:00 AM," Amazon Lex inputs the following into the Lambda function:

```
"slots": {
   "deliveryTime": {
      "value": {
         "originalValue": "10 AM",
         "interpretedValue": 10:00,
         "resolvedValues": [
            "10:00"
         ]
      }
   }
}
```

For more information about the data sent from Amazon Lex to a Lambda function, see \.