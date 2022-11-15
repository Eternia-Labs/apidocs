---
layout: default
title: Update Escalation Policy Details
parent: EscalationPolicy
grand_parent: Workforce
has_children: false
nav_order: 1
---

### Update Escalation Policy Details

Update escalation policy details.

***Operation name:***

> scteams.updateEscalationPolicyDetails

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
| op | scteams.updateEscalationPolicyDetails | (Required) Operation Name |
| org | <<org>> | (Required) Organisation ID |
| pid | <<pid>> | (Required) Project OR building ID |
| propid | <<prop_id>> | (Required) Property ID |


***Request Body:***

```
{
    "EscalationPolicy":{
        "PolicyId":"policyid",
        "Description":"Additional Policy",
        "Name":"New Policy",
        "IncidentTypes":[],
        "UpdateOverride":false
    },
    "MapToArray":true
}
```

| Key | Description |
| --- |-----|
|EscalationPolicy|parent object|
|PolicyId|policy id|
|Name|escalation policy name|
|Description|policy description|
|IncidentTypes|incident types this policy is applicable to |
|UpdateOverride|should the existing incident types be completely replaced by the newly provided incident types ? (optional; default value is <false>)|
|MapToArray|should the updated response be returned in array format ? (optional default value is <false>)|
