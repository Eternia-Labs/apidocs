---
layout: default
title: Get All Escalation Policies
parent: EscalationPolicy
grand_parent: Workforce
has_children: false
nav_order: 1
---

### Get All Escalation Policies

Get all escalation policies defined for a given building.

***Operation name:***

> scteams.getAllEscalationPolicies

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
| op | scteams.getAllEscalationPolicies | (Required) Operation Name |
| org | <<org>> | (Required) Organisation ID |
| pid | <<pid>> | (Required) Project OR building ID |
| propid | <<prop_id>> | (Required) Property ID |


***Request Body:***

```
{
    "MapToArray":true
}
```

| Key | Description |
| --- |-----|
|MapToArray|should the escalation policy settings be mapped to array ? (optional default value is <false>)|