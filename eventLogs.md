---
layout: default
title: Event Logs
parent: MetricsProxy
grand_parent: SmartClean Matrix API Docs
has_children: true
nav_order: 1
---

### 1. Module Time series Metrics

Op name:

> scmetrics.getEventLogs


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
        "Module": "...",
        "Start": "...",
        "End": "...",
        "LastKey": "..."
}
```

***Request body parameters***

| Key | Description |
| --- |-------------|
| Principal  | (Required) This can be projectid, installation/subzone id or device id |
| Module | (Required) The module name to show events for. For e.g., workorders |
| Start | (Required) Start time in unix timestamp seconds |
| End | (Required) End time unix timestamp seconds | 
| LastKey | This is used for pagination. If the lastKey in response is empty then there is no more information to return |


***More example Requests/Responses:***

##### 1. Example Request:

***Body:***

```js
{
"Principal": "BuildingId1",
    "Module": "sctasks",
    "Start": "1610013100",
    "End": "1610013130"
}
```

##### 1. Example Response:

```js
{
    "type": "json",
        "queryType": "eventsTSDB",
        "series": {
        "values": [
            {
                "ATTR": "TASK_COMPLETED#PropId1#BuildingId1#uuid1",
                "Description": "John Doe has completed TASK_0001 in Zone 1.",
                "Event": "TASK_COMPLETED",
                "ID": "sctasks",
                "Principal": "BuildingId1",
                "Status": "NORMAL",
                "Time": "1610013124"
            },
            {
                "ATTR": "TASK_COMPLETED#PropId1#BuildingId1#uuid3",
                "Description": "John Doe has completed TASK_0003 in Zone 1.",
                "Event": "TASK_COMPLETED",
                "ID": "sctasks",
                "Principal": "BuildingId1",
                "Status": "NORMAL",
                "Time": "1610013124"
            },
            {
                "ATTR": "TASK_COMPLETED#PropId1#BuildingId1#uuid2",
                "Description": "John Doe has completed TASK_0002 in Zone 1.",
                "Event": "TASK_COMPLETED",
                "ID": "sctasks",
                "Principal": "BuildingId1",
                "Status": "NORMAL",
                "Time": "1610013130"
            }
        ],
            "start": "1610013100",
            "end": "1610013130"
    }
}
```

<br>