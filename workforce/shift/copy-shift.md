---
layout: default
title: Copy Shift
parent: Shift
grand_parent: Workforce
nav_order: 1
---


### Copy Shift

Copy Shift

***Operation name:***

> scteams.copyShift

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
| op | scteams.copyShift | (Required) Operation Name |
| org | <<org>> | (Required) Organisation ID |
| pid | <<pid>> | (Required) Project OR building ID |
| propid | <<prop_id>> | (Required) Property ID |


***Request Body:***

```
{
    "SeatId": "3b749a81d14446292b6c79b48403bbd_007",
    "Shift": {
        "SeatId": "3b749a681d14446292b6c79b48403bbd_007",
        "ShiftId": "4eaa69d7-f85a-406b-afd7-7114dde11b1f"
    },
    "Repeat": {
        "RepeatDates": [
            "20221116"
        ]
    },
    "IncludeZones":true,
    "IncludeBreaks":true,
    "IncludeTaskGroups": true
}
```

|Key|Value|
|---|---|
|SeatId|new Shift seat id|
|Shift|source shift object|
|Shift.ShiftId|source shift id|
|Shift.SeatId|source seat id|
|Repeat|repeat details|
|Repeat.RepeatDates|list of string dates|
|IncludeZones|should zone be copied to destination shift ?|
|IncludeBreaks|should breaks be copied to destination shift?|
|IncludeTaskGroups|should TGs be copied to destination shift?|