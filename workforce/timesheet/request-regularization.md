---
layout: default
title: Request Regularization
parent: TimeSheet
grand_parent: Workforce
nav_order: 1
---

### Request Regularization

request time sheet regularization.

***Operation name:***

> scteams.requestRegularization

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
| op | scteams.requestRegularization | (Required) Operation Name |
| org | <<org>> | (Required) Organisation ID |
| pid | <<pid>> | (Required) Project OR building ID |
| propid | <<prop_id>> | (Required) Property ID |

***Request Body:***

```
{
    "TimeSheet": {
        "SeatId": "ORG1_SEAT_0002",
        "ShiftId": "4638b8f3-c422-465f-8ec2-dc3d73119823",
        "ReasonForRegularization": "Forgot to punch out",
        "Breaks": [
            {
                "End": 1605149600,
                "Notes": "Afternoon lunch break.",
                "Start": 1605149200,
                "Type": "meal",
                "ID": "0001"
            }
        ]
    },
    "Zones": {
        "zoneID1": "ZoneName1",
        "zoneID2": "ZoneName2"
    }
}
```

|Key|Value|
|---|---|
|TimeSheet|parent object|
|TimeSheet.SeatId|timesheet seat id|
|TimeSheet.ShiftId|timesheet shift id|
|TimeSheet.ReasonForRegularization|regularization reason|
|TimeSheet.Breaks|break details|
|TimeSheet.Zones|zones associated with the Shift|
