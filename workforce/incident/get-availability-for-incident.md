---
layout: default
title: Get Availability For Incident
parent: Incident
grand_parent: Workforce
has_children: true
nav_order: 1
---

### Get Availability For Incident

Get Availability For Incident.

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
| op | scteams.getAvailabilityForIncident | (Required) Operation Name |
| org | <<org>> | (Required) Organisation ID |
| pid | <<pid>> | (Required) Project OR building ID |
| propid | <<prop_id>> | (Required) Property ID |


***Request Body:***

```
{
    "Incident":{
        "End":1628874000,
        "TimeZone":"",
        "ZoneCatId":"zonecat1",
        "Zone":"zone"
    }
}
```

|Key|Value|
|---|---|
|Incident|parent object|
|End|end time in epoch seconds|
|TimeZone|time zone id|
|ZoneCatId|zone category id|
|Zone| zone id of incident|