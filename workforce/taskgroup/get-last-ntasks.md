---
layout: default
title: Get Last N-Tasks
parent: TaskGroup
grand_parent: Workforce
has_children: false
nav_order: 1
---


### Get Last N-Tasks

Get Last N-Tasks by building or property or seat or zone.

***Operation name:***

> scteams.getLastNTasks

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
| op | scteams.getLastNTasks | (Required) Operation Name |
| org | <<org>> | (Required) Organisation ID |
| pid | <<pid>> | (Required) Project OR building ID |
| propid | <<prop_id>> | (Required) Property ID |


***Request Body:***

```
{
    "StartTime":1634825100,
    "EndTime":1654825100,
    "Limit":-5,
    "TasksFor":"PROP",
    "SeatId":"3b749a681d14446292b6c79b48403bbd_002",
    "zoneId": "71d899661d5645acb0b8f8030e26fc35"
}
```

|Key|Value|
|----|----|
|StartTime|time range start time|
|EndTime|time range end time|
|Limit|max number of tasks, by default: 1|
|TasksFor|get tasks for (ID or PROP od ZONE or SEAT)|
|SeatId|seat id (optional if TasksFor is SEAT)|
|zoneId|zone id (optional if TasksFor is ZONE)|