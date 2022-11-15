---
layout: default
title: Edit TimeSheet
parent: TimeSheet
grand_parent: Workforce
nav_order: 1
---

### Edit TimeSheet

Edit a given timesheet details.

***Operation name:***

> scteams.editTimeSheet

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
| op | scteams.editTimeSheet | (Required) Operation Name |
| org | <<org>> | (Required) Organisation ID |
| pid | <<pid>> | (Required) Project OR building ID |
| propid | <<prop_id>> | (Required) Property ID |

***Request Body:***

```
{
    "TimeSheet": {
        "SeatId": "SC_SEAT_0006",
        "ShiftId": "e6056a36-7b2a-4e5f-917b-12cf517c5f77",
        "AStart": 1614673523,
        "AEnd":1614673823,
        "Breaks": [
                    {
                        "End": {{shift_break_end}},
                        "Notes": "Afternoon lunch break.",
                        "Start": {{shift_break_start}},
                        "Type": "meal"
                    }
                ]
    }
}
```

|Key|Value|
|---|---|
|TimeSheet|parent object|
|TimeSheet.SeatId|timesheet seat id|
|TimeSheet.ShiftId|timesheet shift id|
|TimeSheet.AStart|actual shift start time|
|TimeSheet.AEnd|actual shift end time|
|TimeSheet.Breaks|break details|