---
layout: default
title: Create Escalation Policy
parent: EscalationPolicy
grand_parent: Workforce
has_children: false
nav_order: 1
---

### Create Escalation Policy

Creates escalation policy for a given building.

***Operation name:***

> scteams.createEscalationPolicy

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
| op | scteams.createEscalationPolicy | (Required) Operation Name |
| org | <<org>> | (Required) Organisation ID |
| pid | <<pid>> | (Required) Project OR building ID |
| propid | <<prop_id>> | (Required) Property ID |


***Request Body:***

```
{
    "EscalationPolicy":{
        "Name":"EscalationPolicy 1",
        "Description":"",
        "IsDefault":false,
        "IncidentTypes":["*"],
        "DueTimeThresholdSettings":[
            {
                "Level":"L3",
                "Recipients":[{
                    "Entity":"OCBC_001",
                    "EntityMedium":"MATRIX_MOBILE_APP"
                }],
                "TimeAfter":90,
                "Action":"NOTIFY"
            },
            {
                "Level":"L2",
                "Recipients":[{
                    "Entity":"gaurav@smartclean.sg",
                    "EntityMedium":"EMAIL"
                }],
                "TimeAfter":90,
                "Action":"NOTIFY"
            }
        ],
        "StartThresholdSettings":[
            {
                "Level":"L3",
                "Recipients":[{
                    "Entity":"OCBC_001",
                    "EntityMedium":"MATRIX_MOBILE_APP"
                }],
                "TimeAfter":90,
                "Action":"NOTIFY"
            },
            {
                "Level":"L2",
                "Recipients":[{
                    "Entity":"gaurav@smartclean.sg",
                    "EntityMedium":"EMAIL"
                }],
                "TimeAfter":90,
                "Action":"NOTIFY"
            }
        ],
        "TargetDurations":[
            {
                "Priority":"H",
                "DueTime":900,
                "StartThreshold":300
            },
            {
                "Priority":"M",
                "DueTime":900,
                "StartThreshold":600
            },
            {
                "Priority":"N",
                "DueTime":1800,
                "StartThreshold":900
            },
            {
                "Priority":"L",
                "DueTime":3600,
                "StartThreshold":1800
            }
        ]
    }
}
```

| Key | Description |
| --- |-----|
|EscalationPolicy|parent object|
|Name|escalation policy name|
|Description|policy description|
|IsDefault|is this default policy for the building|
|IncidentTypes|incident types this policy is applicable to |
|DueTimeThresholdSettings|due time threshold settings object|
|StartThresholdSettings|start time threshold settings object|
|TargetDurations|target durations|


### ThresholdSettings

|Key|Description|
|---|---|
|Level|escalation level|
|Recipients|escalation notification recipients list|
|TimeAfter|time in seconds since last-level escalation|
|Action|action to be taken|

### TargetDuration

|Key|Description|
|---|---|
|Priority|Incident priority|
|DueTime|time difference in seconds from the expected end time of Incident|
|StartThreshold|time difference in seconds from the expected start time of the Incident|