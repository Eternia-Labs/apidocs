---
layout: default
title: Realtime data gateway API
parent: Matrix API offerings
grand_parent: SmartClean Matrix API Docs
has_children: false
nav_order: 2
---

[comment]: <> (IMPORTANT: The Request details below are temporary stubs. 
Obtain the actual details and update the details below)

### Matrix Realtime data gateway API
This API allows you to enable access to realtime data.

Request Path:

> apis.smartclean.rtdatagateway


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


***Body:***

```json
{
  "Attribute1": "Attribute 1 Value",
  "Attribute2": "Attribute 2 Value"
}
```

***Request body parameters***

| Key | Description |
| --- |-------------|
| Attribute 1 | (Required) Description for attribute 1 |
| Attribute 2 | (Required) Description for attribute 2 |


***More example Requests/Responses:***

##### 1. Example Request:

***Body:***

```json
{
  "Attribute1": "Attribute 1 Example Value",
  "Attribute2": "Attribute 2 Example Value"
}
```

##### 1. Example Response:

```json
{
  "responseAttribute1": "ValueOfResponseAttribute1"
}
```



