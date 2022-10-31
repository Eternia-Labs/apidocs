---
layout: default
title: EscalationPolicy
parent: Workforce
grand_parent: SmartClean Matrix API Docs
has_children: true
nav_order: 2
---
# Escalation Policy
Escalation-Policy defines all possible scenarios when an event can be termed as escalated. An Escalation-Policy object defines various aspects of Escalation-Policy such as event types a given escalation policy is applicable to, course of action to be taken during an escalation etc.

An Escalation-Policy object schema looks like this:-

```
{
        "Description": "Description",
        "ID": "9b0b73c4cda44a7bacf3c4f4f81ffcea",
        "IncidentTypes": [
            "*"
        ],
        "Name": "escalation policy 2",
        "PolicyId": "default",
        "TargetDurations": {
            "L": {
                "StartThreshold": 1800,
                "DueTime": 3600
            },
            "N": {
                "StartThreshold": 900,
                "DueTime": 1800
            },
            "H": {
                "StartThreshold": 300,
                "DueTime": 900
            },
            "M": {
                "StartThreshold": 600,
                "DueTime": 900
            }
        },
        "EscalationSettings": {
            "DueTimeThresholdSettings": {
                "L1": {
                    "Action": "NOTIFY",
                    "Recipients": [
                        {
                            "Entity": "$assignee",
                            "EntityMedium": "MATRIX_APP_NOTIFICATION",
                            "MediumDetails": {},
                            "NotifyForIncidents": []
                        }
                    ],
                    "TimeAfter": 300
                }
            },
            "UnassignedSettings": {
                "L0": {
                    "Action": "NOTIFY",
                    "Recipients": [],
                    "TimeAfter": 300
                }
            },
            "StartThresholdSettings": {
                "L0": {
                    "Action": "NOTIFY",
                    "Recipients": [
                        {
                            "Entity": "$assignee",
                            "EntityMedium": "MATRIX_APP_NOTIFICATION",
                            "MediumDetails": {},
                            "NotifyForIncidents": []
                        }
                    ],
                    "TimeAfter": 300
                }
            }
        },
        "ATTR": "attr#escalationpolicy#9b0b73c4cda44a7bacf3c4f4f81ffcea#default"
    }
```

## Schema Details

|Key|Type|Value|
|---|---|---|
|ID|String|Partition Key|
|ATTR|String|Sort Key|
|Name|String|escalation policy name|
|Description|String|escalation policy description|
|PolicyId|String|policy id|
|IncidentTypes|list|incident type names|
|TargetDurations|object|target durations for different priority levels|
|EscalationSettings|object|escalation event threshold settings|
|EscalationSettings.DueTimeThresholdSettings|object|object defines policy for due-time violation|
|EscalationSettings.UnassignedSettings|object|object defines policy for unassigned incidents violation|
|EscalationSettings.StartThresholdSettings|object|object defines policy for start-time violation|

### ThresholdSettings

|Key|Type|Value|
|---|---|---|
|L{#}|String(key)|escalation level; can be 0,1,2,3|
|Action|String|action id|
|Recipients|list|recipients of post-escalation actions|
|TimeAfter|number of seconds|number of seconds since last escalation (for L1 means time since L0; not applicable for L0 since L0 gets applicable right at the time of Incident reporting.)|

### Recipient

|Key|Type|Value|
|---|---|---|
|Entity|String|recipient id|
|EntityMedium|String|entity medium eg: e-mail|
|MediumDetails|Map|entity medium details|
|NotifyForIncidents|list of string|incident types|