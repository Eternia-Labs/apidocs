---
layout: default
title: Get Tasks In T-range by Zone
parent: TaskGroup
grand_parent: Workforce
has_children: false
nav_order: 1
---


### Get Tasks In T-range by Zone

Get Tasks In T-range by Zone

***Operation name:***

> scteams.tasksInTRangeByZoneId

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
| op | scteams.tasksInTRangeByZoneId | (Required) Operation Name |
| org | <<org>> | (Required) Organisation ID |
| pid | <<pid>> | (Required) Project OR building ID |
| propid | <<prop_id>> | (Required) Property ID |


***Request Body:***

```
{
    "StartTime":1634825100,
    "EndTime":1634826900,
    "SeatId":"3b749a681d14446292b6c79b48403bbd_000",
    "zoneId":"71d899661d5645acb0b8f8030e26fc36"
}
```

|Key|Value|
|---|---|
|SeatId|seat id of task|
|EndTime|time range end time|
|StartTime|time range start time|
|zoneId|zone id of zone|