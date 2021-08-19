# Creating custom slot types<a name="custom-slot-types"></a>

For each intent, you can specify parameters that indicate the information that the intent needs to fulfill the user's request\. These parameters, or slots, have a type\. A *slot type* is a list of values that Amazon Lex V2 uses to train the machine learning model to recognize values for a slot\. For example, you can define a slot type called "`Genres.`" Each value in the slot type is the name of a genre, "comedy," "adventure," "documentary," etc\. You can define a synonym for a slot type value\. For example, you can define the synonyms "funny" and "humorous" for the value "comedy\." 

You can configure the slot type to restrict resolution to the slot values\. The slot values will be used as an enumeration and the value entered by the user will be resolved to the slot value only if it is the same as one of the slot values or a synonym\. A synonym is resolved to the corresponding slot value\. For example, if the user enters "funny" it will resolve to the slot value "comedy\."

Alternately, you can configure the slot type to expand the values\. Slot values will be used as training data and the slot is resolved to the value provided by the user if it is similar to the slot values and synonyms\. This is the default behavior\.

Amazon Lex V2 maintains a list of possible resolutions for a slot\. Each entry in the list provides a *resolved value* that Amazon Lex V2 recognized as additional possibilities for the slot\. A resolved value is the best effort to match the slot value\. The list contains up to five values\.

When the value entered by the user is a synonym, the first entry in the list of `resolvedValues` is the slot type value\. For example, if the user enters "funny," the `originalValue` field contains "funny" and the first entry in the `resolvedValues` field is "comedy\." You configure the `valueSelectionStrategy` when you create or update a slot type with the [CreateSlotType](API_CreateSlotType.md) operation so that the slot value is filled with the first value in the resolution list\.

 If you are using a Lambda function, the input event to the function includes a resolution list called `resolvedValues`\. The following example shows the slot section of the input to a Lambda function:

```
   "slots": {
      "MovieGenre": {
         "value": {
            "originalValue": "funny",
            "interpretedValue": "comedy",
            "resolvedValues": [
               "comedy"
            ]
         }
      }
   }
```

For each slot type, you can define a maximum of 10,000 values and synonyms\. Each bot can have a total number of 50,000 slot type values and synonyms\. For example, you can have 5 slot types, each with 5,000 values and 5,000 synonyms, or you can have 10 slot types, each with 2,500 values and 2,500 synonyms\.