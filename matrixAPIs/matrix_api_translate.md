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

**Complete Endpoint:**

GET

`https://console.smartclean.io/_gapi/apis/apis.smartclean.translate/v1/_translate?op=apis.translateString
&propid=<Property ID>&q=<Text to Translate>&s=<Source Language>&t=<Desired Language>`

Where,
- Method: `GET`

- Base URL: `https://console.smartclean.io`

- Path: `/_gapi/apis/apis.smartclean.translate/v1/_translate`

- Query String: `?op=apis.translateString&propid=<Property ID>&q=<Text to Translate>&s=<Source Language>&t=<Desired Language>`

**Description of query string:**
1. Text in the URL after "?" character is the query string that contains parameters to pass to the request.
2. Set the operation name (_"op"_ as "_apis.translateString_")
   1. i.e., `op=apis.translateString`
   2. This is a constant, for our service to identify the request.
3. The following are variable query parameters, that you must specify:
   1. `propid=<Property ID>`: ID of your SmartClean enabled Property
   2. `q=<string to translate>`: Provide the text to translate
   3. `s=<source language>`: Enter language code of the text you have provided (`For example: "en" for English`)
   4. `t=<target language>`: Enter language code of the desired text (`For example: "es" for Spanish`)
4. To see the complete set of languages codes supported,
   1. Refer to the document at link: https://www.smartclean.io/matrix/assets/common/json/languages_2022_08_25.json
   2. Valid values of all language codes are given here. 

***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Authorization | {{access_token}} | (Required) Basic Auth / Access Token / SC-v4 HMAC Signature (based on authentication type)|
| x-sc-auth | external | (Optional) |

***Body:***
No additional data required for this request.


***Examples:***

_Request URL:_

`https://console.smartclean.io/_gapi/apis/apis.smartclean.translate/v1/_translate?op=apis.translateString
&propid=DemoProperty&q=hello&s=en&t=es`

Where,
following are values of the variable query parameters:
1. `propid=DemoProperty`
2. `q=Hello`
3. `s=en`
4. `t=es`


_Response Body:_

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
