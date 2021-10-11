---
layout: default
title: Module Metrics
parent: MetricsProxy
grand_parent: SmartClean Matrix API Docs
has_children: true
nav_order: 1
---

### 1. Module Metrics

Op name:

> scmetrics.getModuleMetrics


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

```js        
{
       "Principal": "...",
        "NS": "..."
}
```

***Request body parameters***

| Key | Description |
| --- |-------------|
| Principal  | (Required) This can be projectid, installation/subzone id or device id |
| NS | (Required) Namespace to query. For e.g., BUILDING_METRICS. |


***More example Requests/Responses:***

##### 1. Example Request:

***Body:***

```js
{
"Principal": "8865fc0a55604b6d8f96bdb4022fec00",
    "NS": "BUILDING_METRICS"
}
```

##### 1. Example Response:

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