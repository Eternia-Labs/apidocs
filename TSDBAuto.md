---
layout: default
title: TSDBAuto
parent: TSDBMetrics
grand_parent: MetricsProxy
has_children: true
nav_order: 1
---

### 1. TSDB Auto

Op name:

> scmetrics.tsdbQueryAuto

This executes TSDB metrics query without providing the aggregation interval. The aggregation interval is automatically calculated based on the start and end time.


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
| op | scmetrics.tsdbQueryAuto | (Required) Operation name  |
| pid | ... | (Required)  Project ID |


***Body:***

```js        
{
    "time": {
        "start": "...",
            "end": "..."
    },
    "metrics": [
        "..."
    ],
        "aggregations": [
        "...",
        ...
    ],
        "filter": [
        {
            "tagk": "...",
            "tagv": "..."
        },
        ...
    ],
        "postQueryOps": [
        {
            "args": [
                {
                    "value": [
                        "...",
                        ...
                    ],
                    "key": "..."
                }
            ],
            "op": "...",
            "type": "..."
        },
        {...},
        ...
    ],
        "resamplingParams": {
        "duration": "...",
            "fn": "..."
    }
}{
    "time": {
        "start": "...",
            "end": "..."
    },
    "metrics": [
        "..."
    ],
        "aggregations": [
        "...",
        ...
    ],
        "filter": [
        {
            "tagk": "...",
            "tagv": "..."
        },
        ...
    ],
        "postQueryOps": [
        {
            "args": [
                {
                    "value": [
                        "...",
                        ...
                    ],
                    "key": "..."
                }
            ],
            "op": "...",
            "type": "..."
        },
        {...},
        ...
    ],
        "resamplingParams": {
        "duration": "...",
            "fn": "..."
    }
}
```

<br>