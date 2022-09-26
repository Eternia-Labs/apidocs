---
layout: default
title: Translate API
parent: Matrix API offerings
grand_parent: SmartClean Matrix API Docs
has_children: false
nav_order: 1
---

# Matrix Translate API
This API allows you to translate given texts in a desired language.

---
## Request: Translate text

### Complete Endpoint:

GET

`https://console.smartclean.io/_gapi/apis/apis.smartclean.translate/v1/_translate?op=apis.translateString
&propid=<Property ID>&q=<Text to Translate>&s=<Source Language>&t=<Desired Language>`

Where,
- **Method:** `GET`

- **Base URL:** `https://console.smartclean.io`

- **Path:** `/_gapi/apis/apis.smartclean.translate/v1/_translate`

- **Query String:** `?op=apis.translateString&propid=<Property ID>&q=<Text to Translate>&s=<Source Language>&t=<Desired Language>`

### Parameters in query string:
1. Text in the URL after "?" character is the query string that contains parameters to pass to the request.
2. Set the operation name (_"op"_ as "_apis.translateString_")
   1. i.e., `op=apis.translateString`
   2. This is a constant, for our service to identify the request.
3. The following are variable query parameters, that you must specify:
   1. `propid=<Property ID>`: ID of your SmartClean enabled Property
   2. `q=<string to translate>`: Provide the text to translate
   3. `s=<source language code>`: Enter language code (ISO-639-2) of the text you have provided (`For example: "en" for English`)
   4. `t=<target language code>`: Enter language code (ISO-639-2) of the desired text (`For example: "es" for Spanish`)
4. See the complete list of ISO-639 languages codes supported at: https://www.smartclean.io/matrix/assets/common/json/languages_2022_08_25.json
   1. Find out the ISO-639 code for your language here: https://www.loc.gov/standards/iso639-2/php/code_list.php

### Headers:

| Key | Value | Description |
| --- | ------|-------------|
| `Authorization` | Your SmartClean Access Token | (Required) Basic Auth / Access Token / SC-HMAC-V4 Signature (based on authentication type)|
| `x-sc-auth` | Your SmartClean Application ID | (Optional) If you have registered your application with us for federated access|

### Body:
No additional data / body required for this request.


### Example Request:

#### URL:

`https://console.smartclean.io/_gapi/apis/apis.smartclean.translate/v1/_translate?op=apis.translateString
&propid=DemoProperty&q=hello&s=en&t=es`

Where,
following are values of the variable query parameters:
1. `propid=DemoProperty`
2. `q=Hello`
3. `s=en`
4. `t=es`


#### Response Body:

```json
{
    "data": {
        "translations": [
            {
                "translatedText": "Hola"
            }
        ]
    }
}
```
