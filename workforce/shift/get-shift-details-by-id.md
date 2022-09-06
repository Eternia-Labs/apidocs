---
layout: default
title: Get Shift Details By Shift Id
parent: Shift
grand_parent: Workforce
nav_order: 1
---


### Get Shift Details By Shift Id

Get Shift Details By Shift Id

***Operation name:***

> scteams.getShiftDetailsByID

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
| op | scteams.getShiftDetailsByID | (Required) Operation Name |
| org | <<org>> | (Required) Organisation ID |
| pid | <<pid>> | (Required) Project OR building ID |
| propid | <<prop_id>> | (Required) Property ID |


***Request Body:***

```
{
    "Shift": {
        "SeatId": "3b749a681d14446292b6c79b48403bbd_007",
    "ShiftId": "d4ca22ec-900d-4e7a-86ce-96144b7205e5"
    }
}
```

|Key|Value|
|---|---|
|Shift|parent object|
|SeatId|seatid of shift|
|ShiftId|Shift id if shift|