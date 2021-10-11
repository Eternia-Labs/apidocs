---
layout: default
title: Named TSDB
parent: TSDBMetrics
grand_parent: MetricsProxy
has_children: true
nav_order: 1
---

### 1. Named TSDB

Op name:

> scmetrics.tsdbNamedQuery


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
        "qtype": "tsdb"
}
```

***Request body parameters***

| Key | Description |
| --- |-------------|
| id  | (Required) TSDB query ID |
| params | (Required) List of param objects which contain values of variables in the query |
| qcontext | (Required) Query context. For e.g., scglobal |
| qtype | Query type. For e.g., tsdb |


***More example Requests/Responses:***

##### 1. Example Request: 

***Body:***

```js
{
"id": "pc_count_sum_30t_nh_tsdb",
    "params": [
    {
        "key": "$start",
        "value": "-24h"
    }
],
    "qcontext": "scglobal",
    "qtype": "tsdb"
}
```

<br>