---
layout: default
title: Delete Incident
parent: Incident
grand_parent: Workforce
has_children: true
nav_order: 1
---

### Delete Incident

Delete Open incident.

***Operation name:***

> scteams.adminDeleteIncident

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
| op | scteams.adminDeleteIncident | (Required) Operation Name |
| org | <<org>> | (Required) Organisation ID |
| pid | <<pid>> | (Required) Project OR building ID |
| propid | <<prop_id>> | (Required) Property ID |


***Request Body:***

```
{
    "IncidentID":"1656056805791023771",
    "SeatId":"3b749a681d14446292b6c79b48403bbd_007",
    "ShiftID":"20391490-1ffd-4ef7-a283-7dec06784b8f"
}
```

|Key|Value|
|---|---|
|IncidentID|incident id|
|SeatId|seat id of incident|
|ShiftID|shift id of incident|