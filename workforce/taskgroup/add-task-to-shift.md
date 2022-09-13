---
layout: default
title: Add Task To Shift
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
    "SeatId": "3b749a681d14446292b6c79b48403bbd_007",
    "ShiftID": "4eaa69d7-f85a-406b-afd7-7114dde11b1f",
    "Taskgroup": {
        "Start":1634311700,
        "End":1634312500,
        "Name":"New Task group",
        "Zone":"zone",
        "ZoneName":"Zone name",
        "ZoneCatId":"Zone-category",
        "Priority":"L",
        "Tasks":[
            {
                "Name":"abc"
            }
        ]
    }
}
```

|Key|Value|
|---|---|
|SeatId|seat id of shift|
|ShiftID| shift id of Shift|
|Taskgroup|parent object|
|Start|task start time|
|End|task end time|
|Name|task name|
|Zone|zone id of task|
|ZoneName|zone name of zone|
|ZoneCatId|zone category id of zone|
|Priority| priority of task|
|Tasks|task list|