---
layout: default
title: Get Escalation Policy
parent: EscalationPolicy
grand_parent: Workforce
has_children: false
nav_order: 1
---

### Get Escalation Policy

Get escalation policy for a given building by policy id.

***Operation name:***

> scteams.getEscalationPolicy

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
| op | scteams.getEscalationPolicy | (Required) Operation Name |
| org | <<org>> | (Required) Organisation ID |
| pid | <<pid>> | (Required) Project OR building ID |
| propid | <<prop_id>> | (Required) Property ID |


***Request Body:***

```
{
    "EscalationPolicyId": "default"
    "MapToArray":false
}
```

| Key | Description |
| --- |-----|
|EscalationPolicyId|policy id (optional default value is <default>)|
|MapToArray|should the escalation policy settings be mapped to array ? (optional default value is <false>)|