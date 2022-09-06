---
layout: default
title: Get Shift For Project In T-range
parent: Shift
grand_parent: Workforce
nav_order: 1
---


### Get Shift For Project In T-range

Get Shift For Project In T-range

***Operation name:***

> scteams.getShiftsForProjectInTRange

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
| op | scteams.getShiftsForProjectInTRange | (Required) Operation Name |
| org | <<org>> | (Required) Organisation ID |
| pid | <<pid>> | (Required) Project OR building ID |
| propid | <<prop_id>> | (Required) Property ID |


***Request Body:***

```
{
    "EndTime": 1660002400,
    "StartTime": 1660582400
}
```

|Key|Value|
|---|---|
|EndTime|time range end time|
|StartTime|time range start time|