---
layout: default
title: Assign Open Incident
parent: Incident
grand_parent: Workforce
has_children: true
nav_order: 1
---

### Assign Open Incident

Assign Open Incident.

***Operation name:***

> scteams.assignIncident

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
| op | scteams.assignIncident | (Required) Operation Name |
| org | <<org>> | (Required) Organisation ID |
| pid | <<pid>> | (Required) Project OR building ID |
| propid | <<prop_id>> | (Required) Property ID |


***Request Body:***

```
{
    "SeatId":"3b749a681d14446292b6c79b48403bbd_007",
    "ShiftID":"3b749a681d14446292b6c79b48403bbd_007",
    "zoneId":"zoneid99",
    "IncidentID":"1660643173874880217"
}
```

|Key|Value|
|---|---|
|SeatId|seat id to which the incident is being assigned|
|ShiftID|shift id to which the incident is being assigned|
|zoneId|incident zone id|
|IncidentId| incident id|