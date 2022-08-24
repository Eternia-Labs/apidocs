---
layout: default
title: End Ad-Hoc Task
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
    "ShiftID":"47f46a96-8e93-48c0-87b3-beba3c66875e",
    "SeatId":"SONY_002",
    "TaskId":1638864287256,
    "Tasks":[
        {
            "Comments":"Some Comment",
            "Name":"Task Name",
            "Done":true,
            "T":-1
        }
    ]
}
```

|Key|Value|
|---|---|
|ShiftID|shift id of task|
|SeatId|seat id of task|
|TaskId|task id of task|
|Tasks|task list|
|Tasks[0].Comments|task comments|
|Tasks[0].Name|task name|
|Tasks[0].Done|whether task was done or not|
|Tasks[0].T|task value|