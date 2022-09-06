---
layout: default
title: Get Tasks in T-range for Building
parent: TaskGroup
grand_parent: Workforce
has_children: false
nav_order: 1
---


### Get Tasks in T-range for Building

Get Tasks in T-range for Building

***Operation name:***

> scteams.getTaskGroupInTRangeForID

***Endpoint:***

```
Method: POST
Type: application/json
URL: /v1/actions
```

***Headers:***

Basic authorization:

|Key|Value|
|---|---|
|Authorization|<<access_token>>|
|x-sc-identity|external|

HMAC based authorization:

|Key|Value|
|---|---|
|Authorization|SCHMAC_V1;<<tenant_access_key>>;<<HMAC_signature>>|

Federated Token based authorization:

|Key|Value|
|---|---|
|Authorization|Bearer <<user_JWT_token>>|

***Query params:***

| Key | Value | Description |
| --- | ------|-------------|
| op | scteams.getTaskGroupInTRangeForID | (Required) Operation Name |
| org | <<org>> | (Required) Organisation ID |
| pid | <<pid>> | (Required) Project OR building ID |
| propid | <<prop_id>> | (Required) Property ID |


***Request Body:***


```
{
    "Type":"TASK",
    "EndTime": 1634826900,
    "StartTime":0
}
```

|Key|Value|
|---|---|
|Type|task type (optional)|
|EndTime|time range end time|
|StartTime|time range start time|