---
layout: default
title: Mark Shift On Leave
parent: Shift
grand_parent: Workforce
nav_order: 1
---


### Mark Shift On Leave

Mark Shift On Leave

***Operation name:***

> scteams.markOnLeave

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
| op | scteams.markOnLeave | (Required) Operation Name |
| org | <<org>> | (Required) Organisation ID |
| pid | <<pid>> | (Required) Project OR building ID |
| propid | <<prop_id>> | (Required) Property ID |


***Request Body:***

```
{
    "Shift":{
        "ShiftId":"4eaa69d7-f85a-406b-afd7-7114dde11b1f",
        "SeatId":"3b749a681d14446292b6c79b48403bbd_007"
    }
}
```

|Key|Value|
|---|---|
|Shift|parent object|
|SeatId|seat id of shift|
|ShiftId|shift id of shift|