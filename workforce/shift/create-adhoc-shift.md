---
layout: default
title: Create Adhoc Shift
parent: Shift
grand_parent: Workforce
nav_order: 1
---


### Create Adhoc Shift

Create Adhoc Shift

***Operation name:***

> scteams.createAdhocShift

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
| op | scteams.createAdhocShift | (Required) Operation Name |
| org | <<org>> | (Required) Organisation ID |
| pid | <<pid>> | (Required) Project OR building ID |
| propid | <<prop_id>> | (Required) Property ID |


***Request Body:***

```
{
    "SeatId":"3b749a681d14446292b6c79b48403bbd_003",
    "TimeZone":"Asia/Singapore",
    "DaysOfWeek":[2],
    "Zones":{
        "zoneid1":"zone1",
        "zoneid2":"zone2"
    }
}
```

|Key|Value|
|---|---|
|SeatId|seat id of the adhoc shift|
|TimeZone|time zone of the shift|
|DaysOfWeek|list of numbers representing day of week|
|Zones|map of zones associated with this shift|