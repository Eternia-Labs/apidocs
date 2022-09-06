---
layout: default
title: Get Escalation Details of Incidents
parent: Incident
grand_parent: Workforce
has_children: true
nav_order: 1
---

### Get Escalation Details of Incidents

Get Escalation Details of Incidents.

***Operation name:***

> scteams.getIncidentEscalations

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
| op | scteams.getIncidentEscalations | (Required) Operation Name |
| org | <<org>> | (Required) Organisation ID |
| pid | <<pid>> | (Required) Project OR building ID |
| propid | <<prop_id>> | (Required) Property ID |


***Request Body:***

```
{
    "TaskGroups": [
        {
            "TaskId":"1658990379566880217",
            "Zone": "zone99"
        },
        {
            "TaskId":"1653388446311",
            "ShiftId": "20391490-1ffd-4ef7-a283-7dec06784b8f"
        }
    ]
}
```

|Key|Value|
|---|---|
|TaskGroups|list of incidents|
|TaskId|incident id|
|Zone|zone id of incident (if this incident is unassigned)|
|ShiftId|shift id of incident (if this incident is assigned)|