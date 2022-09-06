---
layout: default
title: End Task
parent: TaskGroup
grand_parent: Workforce
has_children: false
nav_order: 1
---


### Add Task To Shift

Add Task To Shift

***Operation name:***

> scteams.addTaskgroupToShift

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
| op | scteams.addTaskgroupToShift | (Required) Operation Name |
| org | <<org>> | (Required) Organisation ID |
| pid | <<pid>> | (Required) Project OR building ID |
| propid | <<prop_id>> | (Required) Property ID |


***Request Body:***


```
{
    "Taskgroup": {
        "SeatId":"3b749a681d14446292b6c79b48403bbd_007",
        "ShiftId":"3b749a681d14446292b6c79b48403bbd_007",
        "TaskId": "1660643173874880217"
    }
}
```

|Key|Value|
|---|---|
|Taskgroup|parent object|
|SeatId|seat id of task|
|ShiftId|shift id of task|
|TaskId|task id of task|