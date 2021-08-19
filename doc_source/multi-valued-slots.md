# Using multiple values in a slot<a name="multi-valued-slots"></a>

**Note**  
Multiple value slots are only supported in the English \(US\) language\.

For some intents, you might want to capture multiple values for a single slot\. For example, a pizza ordering bot might have an intent with the following utterance:

```
I want a pizza with {toppings}
```

The intent expects that the `{toppings}` slot contains a list of the toppings that the customer wants on their pizza, for example "pepperoni and pineapple"\.

To configure a slot to capture multiple values, you set the `allowMultipleValues` field on the slot to true\. You can set the field using the console or with the [CreateSlot](API_CreateSlot.md) or [UpdateSlot](API_UpdateSlot.md) operation\.

You can only mark slots with custom slot types as multi\-value slots\.

For a multi\-value slot, Amazon Lex V2 returns a list of slot values in the response to the [RecognizeText](API_runtime_RecognizeText.md) or [RecognizeUtterance](API_runtime_RecognizeUtterance.md) operation\. The following is the slot information returned for the utterance "I want a pizza with pepperoni and pineapple" from the OrderPizza bot\.

```
    "slots": {
        "toppings": {
            "shape": "List",
            "value": {
                "interpretedValue": "pepperoni and pineapple",
                "originalValue": "pepperoni and pineapple",
                "resolvedValues": [
                    "pepperoni and pineapple"
                ]
            },
            "values": [
                {
                    "shape": "Scalar",
                    "value": {
                        "interpretedValue": "pepperoni",
                        "originalValue": "pepperoni",
                        "resolvedValues": [
                            "pepperoni"
                        ]
                    }
                },
                {
                    "shape": "Scalar",
                    "value:": {
                        "interpretedValue": "pineapple",
                        "originalValue": "pineapple",
                        "resolvedValues": [
                            "pineapple"
                        ]
                    }
                }
            ]
        }
    }
```

Multi\-valued slots always return a list of values\. When the utterance only contains one value, the list of values returned only contains one response\. 

Amazon Lex V2 recognizes multiple values separated by spaces, commas \(,\), and the conjunction "and"\. Multi\-value slots work with both text and voice input\.

You can use multi\-valued slots in prompts\. For example, you can set the confirmation prompt for an intent to

```
Would you like me to order your {toppings} pizza?
```

When Amazon Lex V2 sends the prompt to the user, it sends "Would you like me to order your pepperoni and pineapple pizza?"

Multi\-valued slots support default values\. For more information, see [Using default slot values](context-mgmt-default.md)\.

You can use slot obfuscation to mask the values of a multi\-value slot in conversation logs\. When you obfuscate slot values, the value of each of the slot values is replaced with the name of the slot\. For more information, see [Obscuring slot values in logs](monitoring-obfuscate.md)\.