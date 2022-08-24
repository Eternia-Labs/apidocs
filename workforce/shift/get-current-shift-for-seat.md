---
layout: default
title: Get Current Shift For Seat
parent: Shift
grand_parent: Workforce
nav_order: 1
---


### Get Current Shift For Seat

Get Current Shift For Seat

***Operation name:***

> scteams.getCurrentShiftForSeat

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
|x-sc-identity|external|

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
| op | scteams.getCurrentShiftForSeat | (Required) Operation Name |
| org | <<org>> | (Required) Organisation ID |
| pid | <<pid>> | (Required) Project OR building ID |
| propid | <<prop_id>> | (Required) Property ID |


***Request Body:***

```
{
    "StartTime":1639225000,
    "SeatId":"3b749a681d14446292b6c79b48403bbd_002"
}
```

|Key|Value|
|---|---|
|SeatId|seatid of shift|
|StartTime|time range start time|