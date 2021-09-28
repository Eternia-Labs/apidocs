---
layout: default
title: Get Media Attachement
parent: Miscellaneous
grand_parent: Grids
has_children: true
nav_order: 1
---


### 1. Get Media Attachment


Op name:

> scgrids.getMediaAttachment

This gets the uploaded media attachment


***Endpoint:***

```bash
Method: POST
Type: application/json
URL: /v1/actions
```


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Authorization | {{access_token}} | (Required) The Access Token or HMAC Signature |
| x-sc-identity | external | (Required) |



***Query params:***

| Key | Value | Description |
| --- | ------|-------------|
| op | scgrids.getMediaAttachment | (Required) Operation Name |
| org | scnoop | (Required) Organisation Name |
| pid | scnoop | (Required) Project ID |



***Body:***

```js        
{
    "URI": "{{URI}}"

}
```


***Error codes:***

##### 400

##### Possible reasons:

###### 1. Missing op/org/pid