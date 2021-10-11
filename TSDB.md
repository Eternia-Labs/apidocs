---
layout: default
title: TSDB
parent: TSDBMetrics
grand_parent: MetricsProxy
has_children: true
nav_order: 1
---

### 1. TSDB

Op name:

> scmetrics.tsdbQuery

> scmetrics.tsdb.query (for backward compatibility).

This executes tsdb metrics query


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
| op | scmetrics.tsdbQuery | (Required) Operation name  |
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
        "aggregationInterval": "...",
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

***Request body parameters***

| Key | Description |
| --- |-------------|
| time|  (Required) Time can either be absolute or relative. When doing an absolute search provide both the start and end time for UTC timezone.For e.g., "time": ```{ "start": "2020-10-21T20:00:00+00:00", "end": "2020-10-21T22:30:00+00:00" }``` When doing a relative search provide only the start time. For e.g., "time": {"start": "-1h"}. The maximum valid time unit is h . |
| metrics | (Required) This is a list of strings for the metrics we want to query. For e.g., sg.smartclean.pplctr.raw.count. |
| aggregations | (Required) This is a list of strings for the aggregations that we want to query for the metrics. For e.g., avg. The available aggregations are avg, min, max, sum, and count. |
| aggregationInterval | (Required) This is a string value for the aggregation interval we want to query. For e.g., 15T. The available aggregation intervals are 1T, 5T, 15T, and 30T. |
| filter | (Optional) Filter the data based on a list of column name specified by tagk and column value specified by tagv. |
| postQueryOps | (Optional) This an operation to be performed on the queried data. There are two types of postQueryOps: ``` group by```: Group by groups the data based on the provided list in args.value.                    This can take a special value _field which groups data by the aggregations provided in the aggregations field. ```aggregation```: Aggregation aggregates the data by the op. Only available op right now is sum. |
| resamplingParams | (Optional) This transforms the queried result from a lower duration grouping to higher duration. |

***Note:***

```
 1. If no postQueryOps grouping is provided then by default the data is grouped by L0CLASS, L1CLASS, and L2CLASS.
  
 2. L0CLASS is the Project ID, L1CLASS is the Subzone ID and L2CLASS is the Device ID.
``` 


***More example Requests/Responses:***


##### 1. Example Request: Get multiple aggregations


***Body:***

```js        
{
    "time": {
        "start": "2020-10-21T20:00:00+00:00",
            "end": "2020-10-21T22:30:00+00:00"
    },
    "metrics": [
        "sg.smartclean.odrdtr.raw.voc"
    ],
        "aggregations": [
        "sum",
        "avg"
    ],
        "aggregationInterval": "30T",
        "filter": []
}
```

##### 1. Example Response: Get multiple aggregations
```js
{
    "type": "keyval",
        "series": [
        {
            "values": [
                {
                    "L0CLASS": "NPARKS",
                    "L1CLASS": "BLK_H_FW",
                    "L2CLASS": "190418114930CC50E38C47D8",
                    "_field": "sum",
                    "_time": "2020-10-01T00:30:00Z",
                    "_value": "1.6113629999999997"
                },
                {
                    "L0CLASS": "NPARKS",
                    "L1CLASS": "BLK_H_FW",
                    "L2CLASS": "190418114930CC50E38C47D8",
                    "_field": "avg",
                    "_time": "2020-10-01T00:30:00Z",
                    "_value": "0.057548678571428556"
                }
            ],
            "id": "0",
            "_start": "2020-10-01T00:00:00Z",
            "_end": "2020-10-01T02:30:00Z",
            "aggregationInterval": "30T"
        }
    ],
        "queryType": "tsdb"
}
```

##### 2. Example Request: Filtering

***Body:***

```js
{
    "time": {
        "start": "2020-12-06T07:00:00Z",
        "end": "2020-12-06T20:30:00Z"
    },
    "metrics": [
        "sg.smartclean.odrdtr.raw.voc"
    ],
    "aggregations": [
        "sum"
    ],
    "aggregationInterval": "30T",
    "filter": [
        {
            "tagk": "l1class",
            "tagv": "BLK_H_FW"
        }
    ]
}
```

##### 1. Example Response: Filtering

```js
{
    "type": "keyval",
    "series": [
        {
            "values": [
                {
                    "L0CLASS": "NPARKS",
                    "L1CLASS": "BLK_H_FW",
                    "L2CLASS": "190418112600CC50E38C4920",
                    "_field": "sum",
                    "_time": "2020-12-06T07:00:00Z",
                    "_value": "1"
                },
                {
                    "L0CLASS": "NPARKS",
                    "L1CLASS": "BLK_H_FW",
                    "L2CLASS": "190418112600CC50E38C4920",
                    "_field": "sum",
                    "_time": "2020-12-06T07:30:00Z",
                    "_value": "1"
                },
                {
                    "L0CLASS": "NPARKS",
                    "L1CLASS": "BLK_H_FW",
                    "L2CLASS": "190418112600CC50E38C4920",
                    "_field": "sum",
                    "_time": "2020-12-06T08:00:00Z",
                    "_value": "1"
                }
            ],
            "id": "0",
            "_start": "2020-12-06T07:00:00Z",
            "_end": "2020-12-06T08:00:00Z",
            "aggregationInterval": "30T"
        },
        {
            "values": [
                {
                    "L0CLASS": "NPARKS",
                    "L1CLASS": "BLK_H_FW",
                    "L2CLASS": "190418114930CC50E38C47D8",
                    "_field": "sum",
                    "_time": "2020-12-06T07:00:00Z",
                    "_value": "1"
                },
                {
                    "L0CLASS": "NPARKS",
                    "L1CLASS": "BLK_H_FW",
                    "L2CLASS": "190418114930CC50E38C47D8",
                    "_field": "sum",
                    "_time": "2020-12-06T07:30:00Z",
                    "_value": "1"
                },
                {
                    "L0CLASS": "NPARKS",
                    "L1CLASS": "BLK_H_FW",
                    "L2CLASS": "190418114930CC50E38C47D8",
                    "_field": "sum",
                    "_time": "2020-12-06T08:00:00Z",
                    "_value": "1"
                }
            ],
            "id": "1",
            "_start": "2020-12-06T07:00:00Z",
            "_end": "2020-12-06T08:00:00Z",
            "aggregationInterval": "30T"
        }
    ],
    "queryType": "tsdb"
}
```

<br>