---
layout: default
title: Mark Shift Absent
parent: Shift
grand_parent: Workforce
nav_order: 1
---


### Mark Shift Absent

Mark Shift Absent

***Operation name:***

> scteams.markShiftAbsent

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
| op | scteams.markShiftAbsent | (Required) Operation Name |
| org | <<org>> | (Required) Organisation ID |
| pid | <<pid>> | (Required) Project OR building ID |
| propid | <<prop_id>> | (Required) Property ID |


***Request Body:***

```
{
    "Shift":{
        "ShiftId":"e8376b6e-5471-4608-86c9-eeb5927b8dc0",
        "SeatId":"SONY_001"
    }
}
```

|Key|Value|
|---|---|
|Shift|parent object|
|SeatId|seat id of shift|
|ShiftId|shift id of shift|