---
layout: default
title: Get Thumbnails
parent: Miscellaneous
grand_parent: Grids
has_children: true
nav_order: 1
---


### 2. Get Thumbnails


Op name:

> scgrids.getThumbnails

This gets the given thumbnail


***Endpoint:***

```bash
Method: POST
Type: application/json
URL: /v1/actions
```


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Authorization | {{access_token}} | (Required) The Acccess Token or HMAC Signature |
| x-sc-identity | external | (Required) |



***Query params:***

| Key | Value | Description |
| --- | ------|-------------|
| op | scgrids.getThumbnails | (Required) Operation Name |
| org | scnoop | (Required) Organisation Name |
| pid | scnoop | (Required) Project ID |



***Body:***

```js        
{
    "URIs": [
        "{{URI}}",
         "{{URI}}"
    ]
}
```