---
layout: default
title: Request TimeSheet
parent: TimeSheet
grand_parent: Workforce
nav_order: 1
---

### Request TimeSheet

request time sheet.

***Operation name:***

> scteams.requestTimeSheet

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
| op | scteams.requestTimeSheet | (Required) Operation Name |
| org | <<org>> | (Required) Organisation ID |
| pid | <<pid>> | (Required) Project OR building ID |
| propid | <<prop_id>> | (Required) Property ID |

***Request Body:***

```
{
    "TimeSheet": {
        "SeatId": "",
        "ShiftId": "2b78ef29-05bf-4e14-9297-4f144f0ee4b8",
        "AEnd": 12345678,
        "AStart": 12345678
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