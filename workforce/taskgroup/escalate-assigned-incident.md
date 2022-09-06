---
layout: default
title: Escalate Assigned Incident
parent: TaskGroup
grand_parent: Workforce
has_children: false
nav_order: 1
---


### Escalate Assigned Incident

Escalate Assigned Incident

***Operation name:***

> scteams.escalateIncidentStatusForType

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
| op | scteams.escalateIncidentStatusForType | (Required) Operation Name |
| org | <<org>> | (Required) Organisation ID |
| pid | <<pid>> | (Required) Project OR building ID |
| propid | <<prop_id>> | (Required) Property ID |


***Request Body:***

```
{
    "ShiftID":"616493df-a751-4d3f-b3cb-e04afcb151b2",
    "SeatId":"SONY_001",
    "IncidentId":"1640432081",
    "EscalationType":"startTime"
}
```

|Key|Value|
|---|---|
|ShiftID|shift id of incident|
|SeatId|seat id of incident|
|IncidentId|incident id|
|EscalationType|type of escalation|