# Setting request attributes<a name="context-mgmt-request-attribs"></a>

*Request attributes* contain request\-specific information and apply only to the current request\. A client application sends this information to Amazon Lex\. Use request attributes to pass information that doesn't need to persist for the entire session\. You can create your own request attributes or you can use predefined attributes\. To send request attributes, use the `x-amz-lex-request-attributes` header in a [RecognizeUtterance](API_runtime_RecognizeUtterance.md) or the `requestAttributes` field in a [RecognizeText](API_runtime_RecognizeText.md) request\. Because request attributes don't persist across requests like session attributes do, they are not returned in `RecognizeUtterance` or `RecognizeText` responses\. 

**Note**  
To send information that persists across requests, use session attributes\.

## Setting user\-defined request attributes<a name="context-mgmt-user"></a>

A *user\-defined request attribute* is data that you send to your bot in each request\. You send the information in the `amz-lex-request-attributes` header of a `RecognizeUtterance` request or in the `requestAttributes` field of a `RecognizeText` request\. 

To send request attributes to Amazon Lex, you create a string\-to\-string map of the attributes\. The following shows how to map request attributes: 

```
{
   "attributeName": "attributeValue",
   "attributeName": "attributeValue"
}
```

For the `PostText` operation, you insert the map into the body of the request using the `requestAttributes` field, as follows:

```
"requestAttributes": {
   "attributeName": "attributeValue",
   "attributeName": "attributeValue"
}
```

For the `PostContent` operation, you base64 encode the map, and then send it as the `x-amz-lex-request-attributes` header\.

If you are sending binary or structured data in a request attribute, you must first transform the data to a simple string\. For more information, see [Setting complex attributes](context-mgmt-complex-attributes.md)\.