---
layout: default
title: Get Task Metric For Seat
parent: TaskGroup
grand_parent: Workforce
has_children: false
nav_order: 1
---


### Get Task Metric For Seat

Get Task Metric For Seat

***Operation name:***

> scteams.getTaskGrouptMetricsForSeatID

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
| op | scteams.getTaskGrouptMetricsForSeatID | (Required) Operation Name |
| org | <<org>> | (Required) Organisation ID |
| pid | <<pid>> | (Required) Project OR building ID |
| propid | <<prop_id>> | (Required) Property ID |


***Request Body:***


```
{
    "EndTime":1634826900,
    "SeatId":"3b749a681d14446292b6c79b48403bbd_000"
}
```

|Key|Value|
|---|---|