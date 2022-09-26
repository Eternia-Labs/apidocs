---
layout: default
title: Get Paginated list of open Incidents
parent: Incident
grand_parent: Workforce
has_children: true
nav_order: 1
---

### Get Paginated list of open Incidents

Get list of open incidents in a given time range in paginated form.

***Operation name:***

> scteams.getPaginatedListOfUnAssignedIncidents

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
| op | scteams.getPaginatedListOfUnAssignedIncidents | (Required) Operation Name |
| org | <<org>> | (Required) Organisation ID |
| pid | <<pid>> | (Required) Project OR building ID |
| propid | <<prop_id>> | (Required) Property ID |


***Request Body:***

```
{
    "StartTime": 1616134038,
    "EndTime" : 1646719364,
    "LastEvaluatedKey": "ewogICJTdGFydCIgOiB7CiAgICAibiIgOiAiMTYyMDQ2ODM4MyIKICB9LAogICJJRCIgOiB7CiAgICAicyIgOiAiUElEMSIKICB9LAogICJBVFRSIiA6IHsKICAgICJzIiA6ICJhdHRyI1BJRDEjem9uZWlkIzE2MjA0NjgzODMwMDAiCiAgfQp9"
}
```

| Key | Description |
| --- |-------------|
|StartTime|time range start in epoch seconds|
|EndTime|time range end in epoch seconds|
|LastEvaluatedKey|optional field to used for subsequent requests|