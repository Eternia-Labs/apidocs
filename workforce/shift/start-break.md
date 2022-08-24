---
layout: default
title: Start Break
parent: Shift
grand_parent: Workforce
nav_order: 1
---


### Start Break

Start Break

***Operation name:***

> scteams.startBreak

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
| op | scteams.startBreak | (Required) Operation Name |
| org | <<org>> | (Required) Organisation ID |
| pid | <<pid>> | (Required) Project OR building ID |
| propid | <<prop_id>> | (Required) Property ID |


***Request Body:***

```
{
    "Shift": {
        "SeatId": "3b749a681d14446292b6c79b48403bbd_002",
        "ShiftId": "59930f45-f3a8-4e52-afba-91e859068845",
        "Breaks": [
            {
                "ID": "0005",
                "Notes":"Some notes about break",
                "Type":"Coffee break"
            }
        ]
    }
}
```

|Key|Value|
|---|---|
|Shift|parent object|
|SeatId|seatid of shift|
|ShiftId|Shift id if shift|
|Breaks|list of breaks|
|ID|break id|
|Notes|break notes|
|Type|break type|