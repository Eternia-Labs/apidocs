---
layout: default
title: Update Shift and TaskGroup
parent: Shift
grand_parent: Workforce
nav_order: 1
---


### Update Shift and TaskGroup

Update Shift and TaskGroup

***Operation name:***

> scteams.updateShift

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
| op | scteams.updateShift | (Required) Operation Name |
| org | <<org>> | (Required) Organisation ID |
| pid | <<pid>> | (Required) Project OR building ID |
| propid | <<prop_id>> | (Required) Property ID |


***Request Body:***

```
{
  "Shift": {
    "SeatId": "3b749a681d14446292b6c79b48403bbd_007",
    "ShiftId": "1ef53f4f-09ad-4e5c-b5c8-bd354f735386",
    "TimeZone":"Asia/Singapore",
    "Start": 1662282000,
    "End": 1662292800
  },
  "TaskGroups": [
      {
                "Tasks": [
                    {
                        "Name": "Task 1- Clean floor",
                        "Done": false,
                        "T": -1
                    },
                    {
                        "Name": "Task 6- Clean doors",
                        "Done": false,
                        "T": -1
                    }
                ],
                "ZoneName": "Zone name",
                "ZoneCatId": "MEETING_ROOMS",
                "TaskId": "1662022800000",
                "Zone": "71d899661d5645acb0b8f8030e26fc35"
            }
  ],
  "DeleteTaskGroupIds":["1662022100000"],
  "AddTaskGroups":[
      {
                    "End": 1662023800,
                    "Name": "TG3- Clean Meeting Room",
                    "Priority": "L",
                    "Start": 1662022800,
                    "Tasks": [
                        {
                            "Name": "Task 1- Clean floor"
                        },
                        {
                            "Name": "Task 6- Clean doors"
                        }
                    ],
                    "TimeZone": "Asia/Singapore",
                    "Type": "TASK",
                    "Zone": "71d899661d5645acb0b8f8030e26fc35",
                    "ZoneCatId": "MEETING_ROOMS",
                    "ZoneName":"zone-name1"
                }
  ]
}
```

|Key|Value|
|---|---|
|Shift|parent object|
|Shift.ShiftId|shift id of shift|
|Shift.SeatId|seat id of shift|
|Shift.TimeZone|time zone of shift|
|Shift.Start|start time of shift optional |
|Shift.End|end time of shift optional|
|TaskGroups|list of taskgroups to be udpated|
|TaskGroups[0].Tasks|updated task list|
|TaskGroups[0].TaskId|taskId of Taskgroup|
|TaskGroups[0].Zone|zone id of task|
|TaskGroups[0].ZoneName|zone name of task|
|TaskGroups[0].ZoneCatId|zone category of task zone|
|DeleteTaskGroupIds|list of taskIds to be deleted|
|AddTaskGroups|list of new Taskgroups to be added to the Shift|
