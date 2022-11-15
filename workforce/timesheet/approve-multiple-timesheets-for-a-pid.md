---
layout: default
title: Approve Multiple TimeSheets For a Building
parent: TimeSheet
grand_parent: Workforce
nav_order: 1
---

### Approve Multiple TimeSheets For a Building

Approve multiple time-sheets raised in a given building id.

***Operation name:***

> scteams.approveMultipleTimesheetRequests

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
| op | scteams.approveMultipleTimesheetRequests | (Required) Operation Name |
| org | <<org>> | (Required) Organisation ID |
| pid | <<pid>> | (Required) Project OR building ID |
| propid | <<prop_id>> | (Required) Property ID |

***Request Body:***

```
{
    "ApprovedBy":"SC_MANGER_TEST",
    "ShiftIds":[
        "shift2222222",
        "shift234rfdsdefdesdf"
    ],
    "SeatId":"SC_SEAT_0001"
}
```

|Key|Value|
|---|---|
|ApprovedBy|approved by|
|ShiftIds|shiftIds whose time-sheets are to be approved|
|SeatId|the seatId which the time-sheets belong to|