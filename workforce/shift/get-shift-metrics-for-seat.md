---
layout: default
title: Get Shift Metrics For Seat
parent: Shift
grand_parent: Workforce
nav_order: 1
---


### Get Shift Metrics For Seat

Get Shift Metrics For Seat

***Operation name:***

> scteams.getShiftMetricsForSeatID

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
| op | scteams.getShiftMetricsForSeatID | (Required) Operation Name |
| org | <<org>> | (Required) Organisation ID |
| pid | <<pid>> | (Required) Project OR building ID |
| propid | <<prop_id>> | (Required) Property ID |


***Request Body:***

```
{
    "SeatId": "SONY_001",
    "EndTime": 1637095200,
    "StartTime": 1638095200
}
```

|Key|Value|
|---|---|
|SeatId|seat id for which metrics is to be queried|
|EndTime|time range end time|
|StartTime|time range start time|