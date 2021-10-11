---
layout: default
title: Named Query
parent: MetricsProxy
grand_parent: SmartClean Matrix API Docs
has_children: true
nav_order: 1
---

### 1. Named Query

Op name:

> scmetrics.executeNamedQuery


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
| op | scmetrics.tsdbNamedQuery | (Required) Operation name  |
| org | ... | (Required) Organisation ID | 
| pid | ... | (Required)  Project ID |


***Body:***

```js        
{
    "id": "...",
        "params": [
        {
            "key": "...",
            "value": ".."
        }
        ...
    ],
        "qcontext": "...",
        "qtype": ".."
}
```

***Request body parameters***

| Key | Description |
| --- |-------------|
| id  | (Required) Named query ID |
| params | (Required) List of param objects which contain values of variables in the query |
| qcontext | (Required) Query context. For e.g., scglobal |
| qtype | Query type. For e.g., ml |


***More example Requests/Responses:***

##### 1. Example Request:

***Body:***

```js
{
"id": "total_people_count_by_location_by_hour_for_dom_v2",
    "params": [
    {
        "key": "$month",
        "value": "default"
    },
    {
        "key": "$dom",
        "value": "default"
    },
    {
        "key": "$hour",
        "value": "default"
    },
    {
        "key": "expid",
        "value": "randomexpid"
    }
],
    "qcontext": "scglobal",
    "qtype": "ml"
}
```

<br>



