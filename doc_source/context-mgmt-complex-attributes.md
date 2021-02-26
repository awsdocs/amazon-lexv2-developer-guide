# Setting complex attributes<a name="context-mgmt-complex-attributes"></a>

Session and request attributes are string\-to\-string maps of attributes and values\. In many cases, you can use the string map to transfer attribute values between your client application and a bot\. In some cases, however, you might need to transfer binary data or a complex structure that can't be easily converted to a string map\. For example, the following JSON object represents an array of the three most populous cities in the United States:

```
{
   "cities": [
      {
         "city": {
            "name": "New York",
            "state": "New York",
            "pop": "8537673"
         }
      },
      {
         "city": {
            "name": "Los Angeles",
            "state": "California",
            "pop": "3976322"
         }
      },
      {
         "city": {
            "name": "Chicago",
            "state": "Illinois",
            "pop": "2704958"
         }
      }
   ]
}
```

This array of data doesn't translate well to a string\-to\-string map\. In such a case, you can transform an object to a simple string so that you can send it to your bot with the [RecognizeText](API_runtime_RecognizeText.md) and [RecognizeUtterance](API_runtime_RecognizeUtterance.md) operations\. 

For example, if you are using JavaScript, you can use the `JSON.stringify` operation to convert an object to JSON, and the `JSON.parse` operation to convert JSON text to a JavaScript object:

```
// To convert an object to a string.
var jsonString = JSON.stringify(object, null, 2);
// To convert a string to an object.
var obj = JSON.parse(JSON string);
```

To send attributes with the `RecognizeUtterance` operation, you must base64 encode the attributes before you add them to the request header, as shown in the following JavaScript code:

```
var encodedAttributes = new Buffer(attributeString).toString("base64");
```

You can send binary data to the `RecognizeText` and `RecognizeUtterance` operations by first converting the data to a base64\-encoded string, and then sending the string as the value in the session attributes:

```
"sessionAttributes" : {
   "binaryData": "base64 encoded data"
}
```