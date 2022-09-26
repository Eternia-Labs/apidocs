---
layout: default
title: Create Availability For Seat
parent: Availability
grand_parent: Workforce
has_children: true
nav_order: 1
---

### Create Availabilities for Seat

Creates availabilities for a given Seat for all the requested days of the week.

***Operation name:***

> scteams.createSeatAvailability

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
| op | scteams.createSeatAvailability | (Required) Operation Name |
| org | <<org>> | (Required) Organisation ID |
| pid | <<pid>> | (Required) Project OR building ID |
| propid | <<prop_id>> | (Required) Property ID |


***Request Body:***

```
{
    "Availability":{
        "SeatId":"3b749a681d14446292b6c79b48403bbd_003",
        "DaysOfWeek":[4,5,6],
        "TimeSlots":[
            {
                "StartTime":16000,
                "EndTime":26000,
                "Name":""
            },
            {
                "StartTime":44000,
                "EndTime":33000,
                "Name":"evening shift"
            }
        ]
    }
}
```

| Key | Description |
| --- |-----|
|Availability|parent object|
|SeatId|seat id of the person|
|DaysOfWeek|list of numbers representing nth day of week|
|TimeSlots|list of time-slot objects|
|TimeSlots.StartTime|number of seconds since midnight|
|TimeSlots.EndTime|number of seconds since midnight|
|TimeSlots.Name|name of time-slot|

