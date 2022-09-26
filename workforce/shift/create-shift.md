---
layout: default
title: Create Shift
parent: Shift
grand_parent: Workforce
nav_order: 1
---


### Create Shift

Create Shift

***Operation name:***

> scteams.createShift

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
| op | scteams.createShift | (Required) Operation Name |
| org | <<org>> | (Required) Organisation ID |
| pid | <<pid>> | (Required) Project OR building ID |
| propid | <<prop_id>> | (Required) Property ID |


***Request Body:***

```
{
    "SeatId": "testpropertyid_001",
    "Repeat": {
        "RepeatDates": [
            "20220909"
        ]
    },
    "Schedule": [
        {
            "shift": {
                "Cost": {
                    "U": "SGD",
                    "V": 225
                },
                "Breaks": [
                    {
                        "DurationInSeconds": 120,
                        "IsPlannedBreak": false,
                        "Type": "meal_break"
                    }
                ],
                "End": 1662033600,
                "Start": 1662022800,
                "TimeZone": "Asia/Singapore",
                "Zones": {
                    "71d899661d5645acb0b8f8030e26fc35": "M Room 2"
                },
                "Description": ""
            },
            "taskGroup": [
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
                },
                {
                    "End": 1662024800,
                    "Name": "TG3- Clean Meeting Room",
                    "Priority": "L",
                    "Start": 1662023800,
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
    ],
    "Publish":false
}
```

|Key|Value|
|---|---|
|SeatId|seat id of this shift|
|Repeat|parent object|
|RepeatDates|list of string dates|
|Schedule|list of scheduled shifts to be created|
|shift|shift object|
|Cost|shift cost|
|Breaks|breaks scheduled in the shift|
|End|shift planned end time|
|Start|shift planned start time|
|TimeZone|shift timezone|
|Zones|map of zones which can send alerts to this shift|
|Description|shift description|
|taskGroup|list of task groups which are part of this shift|
|Name|task name|
|Start|task expected start time|
|End|task expected end time|
|Priority|task priority|
|Tasks|list of work items|
|TimeZone|task time zone|
|Type|task type|
|Zone|task zone id|
|ZoneName|task zone name|
|ZoneCatId|task zone cat id|
|Publish|create shift in published state ?|