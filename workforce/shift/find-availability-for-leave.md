---
layout: default
title: Find Availability For Leave
parent: Shift
grand_parent: Workforce
nav_order: 1
---


### Find Availability For Leave

Find Availability For Leave

***Operation name:***

> scteams.findAvailabilityForLeave

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
| op | scteams.findAvailabilityForLeave | (Required) Operation Name |
| org | <<org>> | (Required) Organisation ID |
| pid | <<pid>> | (Required) Project OR building ID |
| propid | <<prop_id>> | (Required) Property ID |


***Request Body:***

```
{
    "StartTime": 1610821321,
    "EndTime": 1650430261,
    "SeatId":"3b749a681d14446292b6c79b48403bbd_003"
}
```

|Key|Value|
|---|---|
|SeatId|seatid of shift|
|StartTime|time range start time|
|EndTime|time range end time|