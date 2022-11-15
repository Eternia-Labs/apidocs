---
layout: default
title: Approve TimeSheet
parent: TimeSheet
grand_parent: Workforce
nav_order: 1
---

### Approve TimeSheet

Approve a given timesheet.

***Operation name:***

> scteams.approveRequest

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
| op | scteams.approveRequest | (Required) Operation Name |
| org | <<org>> | (Required) Organisation ID |
| pid | <<pid>> | (Required) Project OR building ID |
| propid | <<prop_id>> | (Required) Property ID |

***Request Body:***

```
{
    "TimeSheet": {
        "SeatId": "ORG1_SEAT_0001",
        "ShiftId": "4d31bd53-8053-4df3-8a1d-f336f4113272"
    }
}
```

|Key|Value|
|---|---|
|TimeSheet|parent object|
|TimeSheet.SeatId|timesheet seat id|
|TimeSheet.ShiftId|timesheet shift id|