---
layout: default
title: Module Time series Metrics 
parent: MetricsProxy
grand_parent: SmartClean Matrix API Docs
has_children: true
nav_order: 1
---

### 1. Module Time series Metrics

Op name:

> scmetrics.getModuleTSMetrics


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
        "NS": "...",
        "Start": "...",
        "End": "...",
        "HideEmptyBuckets": ...
}
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

##### 1. Example Request(With empty buckets):

***Body:***

```js
{
    "Principal": "c7139e602ed443e3ab5d56ea7ef08ab8",
    "NS": "VCS_WO_DAILY_COUNT_BY_TYPE",
    "Start": "20210105",
    "End": "20210120"
}
```

##### 1. Example Response(With empty buckets):

```js
{
    "type": "json",
        "queryType": "moduleTSDB",
        "series": {
        "values": [
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
            },
            {
                "Bucket": "20210108",
                "Data": {
                    "WorkOrderCount:PT": 5,
                    "WorkOrderCount:TO": 3,
                    "WorkOrderCount:WD": 6
                }
            },
            {
                "Bucket": "20210109",
                "Data": {
                    "WorkOrderCount:PT": 4,
                    "WorkOrderCount:TO": 5,
                    "WorkOrderCount:WD": 3
                }
            },
            {
                "Bucket": "20210110",
                "Data": {
                    "WorkOrderCount:AS": 7,
                    "WorkOrderCount:CT": 7,
                    "WorkOrderCount:GF": 300,
                    "WorkOrderCount:MB": 7,
                    "WorkOrderCount:OT": 7,
                    "WorkOrderCount:PT": 5,
                    "WorkOrderCount:QW": 7,
                    "WorkOrderCount:TO": 2,
                    "WorkOrderCount:WD": 7,
                    "WorkOrderCount:WE": 7
                }
            },
            {
                "Bucket": "20210111",
                "Data": {
                    "WorkOrderCount:PT": 5,
                    "WorkOrderCount:TO": 2,
                    "WorkOrderCount:WD": 7
                }
            },
            {
                "Bucket": "20210112",
                "Data": {
                    "WorkOrderCount:PT": 5,
                    "WorkOrderCount:TO": 2,
                    "WorkOrderCount:WD": 7
                }
            },
            {
                "Bucket": "20210113",
                "Data": {
                    "WorkOrderCount:PT": 5,
                    "WorkOrderCount:TO": 2,
                    "WorkOrderCount:WD": 7
                }
            },
            {
                "Bucket": "20210114",
                "Data": {
                    "WorkOrderCount:PT": 5,
                    "WorkOrderCount:TO": 2,
                    "WorkOrderCount:WD": 0
                }
            },
            {
                "Bucket": "20210115",
                "Data": {
                    "WorkOrderCount:PT": 5,
                    "WorkOrderCount:TO": 2,
                    "WorkOrderCount:WD": 3
                }
            },
            {
                "Bucket": "20210116",
                "Data": {
                    "WorkOrderCount:PT": 5,
                    "WorkOrderCount:TO": 1,
                    "WorkOrderCount:WD": 2
                }
            },
            {
                "Bucket": "20210117",
                "Data": {
                    "WorkOrderCount:PT": 1,
                    "WorkOrderCount:TO": 2,
                    "WorkOrderCount:WD": 5
                }
            },
            {
                "Bucket": "20210118",
                "Data": {}
            },
            {
                "Bucket": "20210119",
                "Data": {}
            },
            {
                "Bucket": "20210120",
                "Data": {}
            }
        ],
            "start": "20210105",
            "end": "20210120"
    }
}
```

##### 1. Example Request(With empty buckets hidden):

***Body:***

```js
{
    "Principal": "c7139e602ed443e3ab5d56ea7ef08ab8",
    "NS": "VCS_WO_DAILY_COUNT_BY_TYPE",
    "Start": "20210105",
    "End": "20210120",
    "HideEmptyBuckets": true
}
```

##### 1. Example Response(With empty buckets hidden):

```js
{
    "type": "json",
    "queryType": "moduleTSDB",
    "series": {
        "values": [
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
            },
            {
                "Bucket": "20210108",
                "Data": {
                    "WorkOrderCount:PT": 5,
                    "WorkOrderCount:TO": 3,
                    "WorkOrderCount:WD": 6
                }
            },
            {
                "Bucket": "20210109",
                "Data": {
                    "WorkOrderCount:PT": 4,
                    "WorkOrderCount:TO": 5,
                    "WorkOrderCount:WD": 3
                }
            },
            {
                "Bucket": "20210110",
                "Data": {
                    "WorkOrderCount:AS": 7,
                    "WorkOrderCount:CT": 7,
                    "WorkOrderCount:GF": 300,
                    "WorkOrderCount:MB": 7,
                    "WorkOrderCount:OT": 7,
                    "WorkOrderCount:PT": 5,
                    "WorkOrderCount:QW": 7,
                    "WorkOrderCount:TO": 2,
                    "WorkOrderCount:WD": 7,
                    "WorkOrderCount:WE": 7
                }
            },
            {
                "Bucket": "20210111",
                "Data": {
                    "WorkOrderCount:PT": 5,
                    "WorkOrderCount:TO": 2,
                    "WorkOrderCount:WD": 7
                }
            },
            {
                "Bucket": "20210112",
                "Data": {
                    "WorkOrderCount:PT": 5,
                    "WorkOrderCount:TO": 2,
                    "WorkOrderCount:WD": 7
                }
            },
            {
                "Bucket": "20210113",
                "Data": {
                    "WorkOrderCount:PT": 5,
                    "WorkOrderCount:TO": 2,
                    "WorkOrderCount:WD": 7
                }
            },
            {
                "Bucket": "20210114",
                "Data": {
                    "WorkOrderCount:PT": 5,
                    "WorkOrderCount:TO": 2,
                    "WorkOrderCount:WD": 0
                }
            },
            {
                "Bucket": "20210115",
                "Data": {
                    "WorkOrderCount:PT": 5,
                    "WorkOrderCount:TO": 2,
                    "WorkOrderCount:WD": 3
                }
            },
            {
                "Bucket": "20210116",
                "Data": {
                    "WorkOrderCount:PT": 5,
                    "WorkOrderCount:TO": 1,
                    "WorkOrderCount:WD": 2
                }
            },
            {
                "Bucket": "20210117",
                "Data": {
                    "WorkOrderCount:PT": 1,
                    "WorkOrderCount:TO": 2,
                    "WorkOrderCount:WD": 5
                }
            }
        ],
        "start": "20210105",
        "end": "20210120"
    }
}
```


<br>