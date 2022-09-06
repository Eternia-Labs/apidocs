---
layout: default
title: Start Task
parent: TaskGroup
grand_parent: Workforce
has_children: false
nav_order: 1
---


### Start Task

Start Task

***Operation name:***

> scteams.taskStart

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
| op | scteams.taskStart | (Required) Operation Name |
| org | <<org>> | (Required) Organisation ID |
| pid | <<pid>> | (Required) Project OR building ID |
| propid | <<prop_id>> | (Required) Property ID |


***Request Body:***

```
{
    "Taskgroup": {
        "SeatId": "3b749a681d14446292b6c79b48403bbd_007",
        "ShiftId": "20391490-1ffd-4ef7-a283-7dec06784b8f",
        "TaskId": "1659591261049880217"
    }
}
```

|Key|Value|
|---|---|
|Taskgroup|parent object|
|SeatId|seatid of the task|
|ShiftId|shift id of task|
|TaskId|task id of task|