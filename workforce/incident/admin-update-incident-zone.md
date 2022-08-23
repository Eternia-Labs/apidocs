---
layout: default
title: Admin Update Incident Zone
parent: Incident
grand_parent: Workforce
has_children: true
nav_order: 1
---

### Admin Update Incident Zone

Update incident zone.

***Operation name:***

> scteams.adminUpdateIncidentZone

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
| op | scteams.adminUpdateIncidentZone | (Required) Operation Name |
| org | <<org>> | (Required) Organisation ID |
| pid | <<pid>> | (Required) Project OR building ID |
| propid | <<prop_id>> | (Required) Property ID |


***Request Body:***

```
{
    "Incident": {
        "TaskId":"1653890798910",
        "Zone": "zoneid99"
    },
    "zoneId":"zoneid",
    "ZoneName":"zone name",
    "ZoneCategoryId":"zone category id"
}
```

|Key|Value|
|---|---|
|Incident|parent object|
|Incident.TaskId|incident id|
|Incident.Zone|incident zone id|
|zoneId|new zone id|
|ZoneName|new zone name|
|ZoneCategoryId|new zone category id|