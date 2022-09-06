---
layout: default
title: Get Shift In T-range For Building On Status
parent: Shift
grand_parent: Workforce
nav_order: 1
---


### Get Shift In T-range For Building On Status

Get Shift In T-range For Building On Status

***Operation name:***

> scteams.getShiftsInTRangeForIDonStatus

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
| op | scteams.getShiftsInTRangeForIDonStatus | (Required) Operation Name |
| org | <<org>> | (Required) Organisation ID |
| pid | <<pid>> | (Required) Project OR building ID |
| propid | <<prop_id>> | (Required) Property ID |


***Request Body:***

```
{
    "Shift": {
        "Start":1630364400,
        "End":1634139500,
        "Status":"COMPLETED"
    }
}
```

|Key|Value|
|---|---|
|Shift|parent object|
|End|time range end time|
|Start|time range start time|
|Status|Shift status|