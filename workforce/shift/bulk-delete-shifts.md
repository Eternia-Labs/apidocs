---
layout: default
title: Bulk Delete Shifts
parent: Shift
grand_parent: Workforce
nav_order: 1
---


### Bulk Delete Shifts

Update Shift Settings

***Operation name:***

> scteams.bulkDeleteShift

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
| op | scteams.bulkDeleteShift | (Required) Operation Name |
| org | <<org>> | (Required) Organisation ID |
| pid | <<pid>> | (Required) Project OR building ID |
| propid | <<prop_id>> | (Required) Property ID |


***Request Body:***

```
{
    "ShiftBulkDelete":{
        "SeatShiftPairs":[
            {
                "SeatId":"",
                "ShiftId":"0899ea51-cee8-4a74-bf67-c1da3b1426fb"
            },
            {
                "SeatId":"3b749a681d14446292b6c79b48403bbd_007",
                "ShiftId":"85e43657-4eae-45cf-a06b-fa692b16fde0"
            },
            {
                "SeatId":"3b749a681d14446292b6c79b48403bbd_007",
                "ShiftId":"ee3e20f3-0941-4ade-862d-61f2d6d0e653"
            }
        ]
    }
}
```

|Key|Value|
|---|---|
|ShiftBulkDelete|parent object|
|SeatShiftPair|list of objects having Seat/Shift ids|
|SeatId|seat id of Shift to be deleted|
|ShiftId| shift if of Shift to be deleted|