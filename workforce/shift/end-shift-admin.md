---
layout: default
title: End Shift Admin
parent: Shift
grand_parent: Workforce
nav_order: 1
---


### End Shift Admin

End Shift Admin

***Operation name:***

> scteams.shiftEndAdmin

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
| op | scteams.shiftEndAdmin | (Required) Operation Name |
| org | <<org>> | (Required) Organisation ID |
| pid | <<pid>> | (Required) Project OR building ID |
| propid | <<prop_id>> | (Required) Property ID |


***Request Body:***

```
{
    "Shift": {
        "SeatId": "3b749a681d14446292b6c79b48403bbd_007",
        "ShiftId": "1d3224a6-4004-4965-b84b-4c93b7c72ae1",
        "Coordinates": {
            "ClockOut": {
                "Latitude": 3.165725,
                "Longitude": 101.646267
            }
        }
    }
}
```

|Key|Value|
|---|---|
|Shift|parent object|
|SeatId|seat id of shift|
|ShiftId|shift id of shift|
|Coordinates|object with clock out geo-location|