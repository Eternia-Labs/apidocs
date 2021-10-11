---
layout: default
title: Module Time series Batch Metrics
parent: MetricsProxy
grand_parent: SmartClean Matrix API Docs
has_children: true
nav_order: 1
---

### 1. Module Time series Metrics

Op name:

> scmetrics.getModuleTSMetricsBatch


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
 [
    {
        "Principal": "...",
        "NS": "...",
        "Start": "...",
        "End": "...",
        "HideEmptyBuckets": ...
    },
    {...},
    ...
]
```

***Request body parameters***

| Key | Description |
| --- |-------------|
| Principal  | (Required) This can be projectid, installation/subzone id or device id |
| NS | (Required) Namespace to query. For e.g., VCS_WO_DAILY_COUNT_BY_TYPE |
| Start | (Required) Start time in unix timestamp seconds |
| End | (Required) End time unix timestamp seconds | 
| HideEmptyBuckets | (Optional) Do not return empty buckets in the response. Defaults to false |


***More example Requests/Responses:***

##### 1. Example Request:

***Body:***

```js
[
{
    "Principal": "c7139e602ed443e3ab5d56ea7ef08ab8",
    "NS": "VCS_WO_DAILY_COUNT_BY_TYPE",
    "Start": "20210105",
    "End": "20210106",
    "HideEmptyBuckets": true
},
{
    "Principal": "c7139e602ed443e3ab5d56ea7ef08ab8",
    "NS": "VCS_WO_DAILY_COUNT_BY_TYPE",
    "Start": "20210105",
    "End": "20210107",
    "HideEmptyBuckets": true
}
]
```

##### 1. Example Response:

```js
{
    "type": "json",
        "queryType": "moduleTSDB",
        "series": [
        [
            {
                "Bucket": "20210105",
                "Data": {
                    "WorkOrderCount:PT": 3
                }
            },
            {
                "Bucket": "20210106",
                "Data": {
                    "WorkOrderCount:MO": 5,
                    "WorkOrderCount:PT": 4,
                    "WorkOrderCount:WD": 5
                }
            }
        ],
        [
            {
                "Bucket": "20210105",
                "Data": {
                    "WorkOrderCount:PT": 3
                }
            },
            {
                "Bucket": "20210106",
                "Data": {
                    "WorkOrderCount:MO": 5,
                    "WorkOrderCount:PT": 4,
                    "WorkOrderCount:WD": 5
                }
            },
            {
                "Bucket": "20210107",
                "Data": {
                    "WorkOrderCount:PT": 5,
                    "WorkOrderCount:WD": 7
                }
            }
        ]
    ]
}
```

<br>