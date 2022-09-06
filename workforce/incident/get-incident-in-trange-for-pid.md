---
layout: default
title: Get Open Incident In T-Range for a Building
parent: Incident
grand_parent: Workforce
has_children: true
nav_order: 1
---

### Get Open Incident In T-Range for a Building

Get list of open incidents in a given time range for a given building id.

***Operation name:***

> scteams.getUnAssignedIncidentsInTRangeForGivenID

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
| op | scteams.getUnAssignedIncidentsInTRangeForGivenID | (Required) Operation Name |
| org | <<org>> | (Required) Organisation ID |
| pid | <<pid>> | (Required) Project OR building ID |
| propid | <<prop_id>> | (Required) Property ID |


***Request Body:***

```
{
    "StartTime": 1205148100,
    "EndTime": 1805148100
}
```

| Key | Description |
| --- |-------------|
|StartTime|time range start in epoch seconds|
|EndTime|time range end in epoch seconds|