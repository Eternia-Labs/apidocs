---
layout: default
title: Get Tasks in T-range For Seat
parent: TaskGroup
grand_parent: Workforce
has_children: false
nav_order: 1
---


### Get Tasks in T-range For Seat

Get Tasks in T-range For Seat

***Operation name:***

> scteams.getTaskGroupInTRangeForSeatID

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
| op | scteams.getTaskGroupInTRangeForSeatID | (Required) Operation Name |
| org | <<org>> | (Required) Organisation ID |
| pid | <<pid>> | (Required) Project OR building ID |
| propid | <<prop_id>> | (Required) Property ID |


***Request Body:***

```
{
    "SeatId": "3b749a681d14446292b6c79b48403bbd_003",
    "Type":"TASK",
    "EndTime": 1634826900,
    "StartTime": 1634825100
}
```

|Key|Value|
|---|---|
|SeatId|seat id of task|
|Type|task type (optional)|
|EndTime|time range end time|
|StartTime|time range start time|