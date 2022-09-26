---
layout: default
title: Get Availability For Incident
parent: Shift
grand_parent: Workforce
nav_order: 1
---


### Get Availability For Incident

Get Availability For Incident

***Operation name:***

> scteams.getAvailabilityForIncident

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
| op | scteams.getAvailabilityForIncident | (Required) Operation Name |
| org | <<org>> | (Required) Organisation ID |
| pid | <<pid>> | (Required) Project OR building ID |
| propid | <<prop_id>> | (Required) Property ID |


***Request Body:***

```
{
    "Incident":{
        "End":1685976000,
        "TimeZone":"Asia/Singapore",
        "Zone":"zone",
        "ZoneCatId":"zonecat"
    }
}
```

|Key|Value|
|---|---|
|Incident|parent object|
|End|time range end|
|TimeZone|time zone|
|Zone|zone id of incident|
|ZoneCatId|zone cat id of Zone|