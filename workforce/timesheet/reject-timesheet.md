---
layout: default
title: Reject TimeSheet
parent: TimeSheet
grand_parent: Workforce
nav_order: 1
---

### Reject TimeSheet

reject time sheet.

***Operation name:***

> scteams.rejectTimesheet

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
| op | scteams.rejectTimesheet | (Required) Operation Name |
| org | <<org>> | (Required) Organisation ID |
| pid | <<pid>> | (Required) Project OR building ID |
| propid | <<prop_id>> | (Required) Property ID |

***Request Body:***

```
{
    "TimeSheet": {
        "SeatId": "",
        "ShiftId": "4638b8f3-c422-465f-8ec2-dc3d73119823",
        "Reason": "Check the time"
    }
}
```

|Key|Value|
|---|---|
|TimeSheet|parent object|
|TimeSheet.SeatId|timesheet seat id|
|TimeSheet.ShiftId|timesheet shift id|
|TimeSheet.Reason|reason of rejection|