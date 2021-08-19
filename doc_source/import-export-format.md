# JSON format for importing and exporting<a name="import-export-format"></a>

You import and export bots and bot locales from Amazon Lex V2 using a \.zip file that contains JSON structures that describe the parts of the bot or alias\. When you export a bot, Amazon Lex V2 creates the \.zip file and makes it available to you using an Amazon S3 pre\-signed URL\. When you import a bot, you must create a \.zip file that contains the JSON structures and upload it to an S3 pre\-signed URL\. 

Amazon Lex creates the following directory structure in the \.zip file when you export a bot\.

```
BotName_BotVersion_ExportID_LexJson.zip
            -or-
BotName_BotVersion_LocaleId_ExportId_LEX_JSON.zip
        --> manifest.json
        --> BotName
        ----> Bot.json
        ----> BotLocales
        ------> Locale_A
        --------> BotLocale.json
        --------> Intents
        ----------> Intent_A
        ------------> Intent.json
        ------------> Slots
        --------------> Slot_A
        ----------------> Slot.json
        --------------> Slot_B
        ----------------> Slot.json
        ----------> Intent_B
                       ...
        -------->SlotTypes
        ----------> SlotType_A
        ------------> SlotType.json
        ----------> SlotType_B
                        ...
        ------> Locale_B
                        ...
```

## Manifest file structure<a name="json-manifest"></a>

The manifest file contains metadata for the export file\.

```
{ 
    "metadata": {
        "schemaVersion": "1.0", 
        "fileFormat": "LexJson", 
        "resourceType": "Bot | BotLocale"
    }
}
```

## Bot file structure<a name="json-bot"></a>

The bot file contains the configuration information for the bot\.

```
{
    "name": "BotName",
    "identifier": "identifier",
    "version": "number",
    "description": "description",
    "dataPrivacy": {
        "childDirected": true | false
    },
    "idleSessionTTLInSeconds": seconds
}
```

## Bot locale file structure<a name="json-bot-locale"></a>

The bot locale file contains a description of the locale or language of a bot\. When you export a bot, there can be more than one bot locale file in the \.zip file\. When you export a bot locale, there is only one locale in the zip file\.

```
{
    "name": "locale name",
    "identifier": "locale ID",
    "version": "number",
    "description": "description",
    "voiceSettings": {
        "voiceId": "voice"
    },
    "nluConfidenceThreshold": number
}
```

## Intent file structure<a name="json-intent"></a>

The intent file contains the configuration information for an intent\. There is one intent file in the \.zip file for each intent in a specific locale\.

The following is an example of a JSON structure for the BookCar intent in the sample BookTrip bot\. For a complete example of the JSON structure for an intent, see the [CreateIntent](API_CreateIntent.md) operation\.

```
{
    "name": "BookCar",
    "identifier": "891RWHHICO",
    "description": "Intent to book a car.",
    "parentIntentSignature": null,
    "sampleUtterances": [
        {
            "utterance": "Book a car"
        },
        {
            "utterance": "Reserve a car"
        },
        {
            "utterance": "Make a car reservation"
        }
    ],
    "intentConfirmationSetting": {
        "confirmationPrompt": {
            "messageGroupList": [
                {
                    "message": {
                        "plainTextMessage": {
                            "value": "OK, I have you down for a {CarType} hire in {PickUpCity} from {PickUpDate} to {ReturnDate}.  Should I book the reservation?"
                        },
                        "ssmlMessage": null,
                        "customPayload": null,
                        "imageResponseCard": null
                    },
                    "variations": null
                }
            ],
            "maxRetries": 2
        },
        "declinationResponse": {
            "messageGroupList": [
                {
                    "message": {
                        "plainTextMessage": {
                            "value": "OK, I have cancelled your reservation in progress."
                        },
                        "ssmlMessage": null,
                        "customPayload": null,
                        "imageResponseCard": null
                    },
                    "variations": null
                }
            ]
        }
    },
    "intentClosingSetting": null,
    "inputContexts": null,
    "outputContexts": null,
    "kendraConfiguration": null,
    "dialogCodeHook": null,
    "fulfillmentCodeHook": null,
    "slotPriorities": [
        {
            "slotName": "DriverAge",
            "priority": 4
        },
        {
            "slotName": "PickUpDate",
            "priority": 2
        },
        {
            "slotName": "ReturnDate",
            "priority": 3
        },
        {
            "slotName": "PickUpCity",
            "priority": 1
        },
        {
            "slotName": "CarType",
            "priority": 5
        }
    ]
}
```

## Slot file structure<a name="json-slot"></a>

The slot file contains the configuration information for a slot in an intent\. There is one slot file in the \.zip file for each slot defined for an intent in a specific locale\.

The following example is the JSON structure of a slot that enables the customer to choose the type of car they wish to rent in the BookCar intent in the BookTrip example bot\. For a complete example of the JSON structure for an slot, see the [CreateSlot](API_CreateSlot.md) operation\.

```
{
    "name": "CarType",
    "identifier": "KDHJWNGZGC",
    "description": "Type of car being reserved.",
    "multipleValuesSetting": {
        "allowMutlipleValues": false
    },
    "slotTypeName": "CarTypeValues",
    "obfuscationSetting": null,
    "slotConstraint": "Required",
    "defaultValueSpec": null,
    "slotValueElicitationSetting": {
        "promptSpecification": {
            "messageGroupList": [
                {
                    "message": {
                        "plainTextMessage": {
                            "value": "What type of car would you like to rent?  Our most popular options are economy, midsize, and luxury"
                        },
                        "ssmlMessage": null,
                        "customPayload": null,
                        "imageResponseCard": null
                    },
                    "variations": null
                }
            ],
            "maxRetries": 2
        },
        "sampleValueElicitingUtterances": null,
        "waitAndContinueSpecification": null,
    }
}
```

## Slot type file structure<a name="json-slot-type"></a>

The slot type file contains the configuration information for a custom slot type used in a language or locale\. There is one slot type file in the \.zip file for each custom slot type in a specific locale\.

The following is the JSON structure for the slot type that lists the types of cars available in the BookTrip example bot\. For a complete example of the JSON structure for a slot type, see the [CreateSlotType](API_CreateSlotType.md) operation\.

```
{
    "name": "CarTypeValues",
    "identifier": "BROZ1QFWSH",
    "description": "Enumeration representing possible types of cars available for rental",
    "slotTypeValues": [
        {
            "sampleValue": {
                "value": "economy"
            },
            "synonyms": null
        },
        {
            "sampleValue": {
                "value": "standard"
            },
            "synonyms": null
        },
        {
            "sampleValue": {
                "value": "midsize"
            },
            "synonyms": null
        },
        {
            "sampleValue": {
                "value": "full size"
            },
            "synonyms": null
        },
        {
            "sampleValue": {
                "value": "luxury"
            },
            "synonyms": null
        },
        {
            "sampleValue": {
                "value": "minivan"
            },
            "synonyms": null
        }
    ],
    "parentSlotTypeSignature": null,
    "slotTypeConfiguration": null,
    "valueSelectionStrategy": "ORIGINAL_VALUE"
}
```