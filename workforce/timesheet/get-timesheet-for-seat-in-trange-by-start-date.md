---
layout: default
title: Get TimeSheets For Seat In T-Range By Start-Date
parent: TimeSheet
grand_parent: Workforce
nav_order: 1
---

### Get TimeSheets For Seat In T-Range By Start-Date

Get all time-sheets for a given SeatId in time-range for a given start date.

***Operation name:***

> scteams.getTimeSheetForSeatIdInTRangeByStartDate

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
| op | scteams.getTimeSheetForSeatIdInTRangeByStartDate | (Required) Operation Name |
| org | <<org>> | (Required) Organisation ID |
| pid | <<pid>> | (Required) Project OR building ID |
| propid | <<prop_id>> | (Required) Property ID |

***Request Body:***

```
{
    "SeatId": "SONY_001",
    "StartTime": 1665148200,
    "EndTime":  1645148200
}
```

|Key|Value|
|---|---|
|StartTime|time range start|
|EndTime|time range end|
|SeatId|seat id|