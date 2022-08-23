---
layout: default
title: Escalate Open Incident
parent: Incident
grand_parent: Workforce
has_children: true
nav_order: 1
---

### Escalate Open Incident

Escalate Open Incident.

***Operation name:***

> scteams.escalateUnassignedIncident

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
| op | scteams.escalateUnassignedIncident | (Required) Operation Name |
| org | <<org>> | (Required) Organisation ID |
| pid | <<pid>> | (Required) Project OR building ID |
| propid | <<prop_id>> | (Required) Property ID |


***Request Body:***

```
{
    "zoneId":"zone99",
    "IncidentId":"1658990379566880217"
}
```

|Key|Value|
|---|---|
|zoneId|zone id of incident|
|IncidentId|incident id|