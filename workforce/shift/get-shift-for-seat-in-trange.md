---
layout: default
title: Get Shift For Seat In T-range
parent: Shift
grand_parent: Workforce
nav_order: 1
---


### Get Shift For Seat In T-range

Get Shift For Seat In T-range

***Operation name:***

> scteams.getShiftsForSeatInTRange

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
| op | scteams.getShiftsForSeatInTRange | (Required) Operation Name |
| org | <<org>> | (Required) Organisation ID |
| pid | <<pid>> | (Required) Project OR building ID |
| propid | <<prop_id>> | (Required) Property ID |


***Request Body:***

```
{
    "SeatId": "3b749a681d14446292b6c79b48403bbd_003",
    "StartTime": 1635095200,
    "EndTime": 1665181600,
    "ID": "SONY"
}
```

|Key|Value|
|---|---|
|SeatId|seat id|
|EndTime|time range end time|
|StartTime|time range start time|
|ID|building id to get shifts of only one building (optional)|