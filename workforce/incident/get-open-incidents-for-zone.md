---
layout: default
title: Get Open Incidents For Zone
parent: Incident
grand_parent: Workforce
has_children: true
nav_order: 1
---

### Get Open Incidents For Zone

Get list of open incidents in a given time range for a given zone id.

***Operation name:***

> scteams.getUnassignedIncidentsForZone

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
| op | scteams.getUnassignedIncidentsForProperty | (Required) Operation Name |
| org | <<org>> | (Required) Organisation ID |
| pid | <<pid>> | (Required) Project OR building ID |
| propid | <<prop_id>> | (Required) Property ID |


***Request Body:***

```
{
    "StartTime": 0,
    "EndTime":1666588219,
    "zoneId": "zoneid"
}
```

| Key | Description |
| --- |-------------|
|StartTime|time range start in epoch seconds|
|EndTime|time range end in epoch seconds|
|zoneId|requested zone id|