---
layout: default
title: Update Availability
parent: Availability
grand_parent: Workforce
has_children: true
nav_order: 1
---

### Update Seat Availabilities

Updates availabilities for a given Seat for all the requested days of the week.

***Operation name:***

> scteams.updateSeatAvailability

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
| op | scteams.updateSeatAvailability | (Required) Operation Name |
| org | <<org>> | (Required) Organisation ID |
| pid | <<pid>> | (Required) Project OR building ID |
| propid | <<prop_id>> | (Required) Property ID |

***Request Body:***

```
{
    "SeatId":"3b749a681d14446292b6c79b48403bbd_003",
    "Availabilities":[
    {
        "DayOfWeek":0,
        "TimeSlots":[
            {
                        "StartTime": 16000,
                        "EndTime": 26000,
                        "Name": "morning shift"
                    },
                    {
                        "StartTime": 26000,
                        "EndTime": 33000,
                        "Name": "evening shift"
                    }
        ],
        "Zones":{
            "zoneid":"zone-name"
        }
    },
    {
        "DayOfWeek":1,
        "TimeSlots":[
            {
                        "StartTime": 16000,
                        "EndTime": 26000,
                        "Name": "morning shift"
                    },
                    {
                        "StartTime": 26000,
                        "EndTime": 33000,
                        "Name": "evening shift"
                    }
        ]
    }
    ]
}
```

| Key | Description |
| --- |-----|
|SeatId|SeatId of the user|
|Availabilities|list of availabilities to be updated|
|Availabilities.DayOfWeek|day of the week whose availability is to be updated|
|Availabilities.TimeSlots|updated time-slots|
|TimeSlots.StartTime|number of seconds since midnight|
|TimeSlots.EndTime|number of seconds since midnight|
|TimeSlots.Name|name of time-slot|