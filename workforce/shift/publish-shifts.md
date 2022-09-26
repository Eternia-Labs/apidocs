---
layout: default
title: Publish Shifts
parent: Shift
grand_parent: Workforce
nav_order: 1
---


### Publish Shifts

Publish Shifts

***Operation name:***

> scteams.publishShifts

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
| op | scteams.publishShifts | (Required) Operation Name |
| org | <<org>> | (Required) Organisation ID |
| pid | <<pid>> | (Required) Project OR building ID |
| propid | <<prop_id>> | (Required) Property ID |


***Request Body:***

```
{
    "Schedule": [
        {
            "shift": {
                "SeatId": "3b749a681d14446292b6c79b48403bbd_007",
                "ShiftId": "d893d581-15a3-4d12-877c-17493a9943ea"
            }
        }
    ]
}

```

|Key|Value|
|---|---|
|Schedule|parent object with list of Shifts to be published|
|Shift|shift to be published|
|SeatId|seat id of shift|
|ShiftId|shift id of shift|