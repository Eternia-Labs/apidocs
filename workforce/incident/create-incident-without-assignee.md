---
layout: default
title: Create Incident Without Assignee
parent: Incident
grand_parent: Workforce
has_children: true
nav_order: 1
---

### Create Incident Without Assignee

Create open incident.

***Operation name:***

> scteams.createIncidentWithoutAssignee

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
| op | scteams.createIncidentWithoutAssignee | (Required) Operation Name |
| org | <<org>> | (Required) Organisation ID |
| pid | <<pid>> | (Required) Project OR building ID |
| propid | <<prop_id>> | (Required) Property ID |


***Request Body:***

```
{
    "Incident": {
        "Start":1656588219,
        "End" : 1656589219,
        "Name": "Washroom essentials.",
        "Priority": "L",
        "Tasks": [
            {
                "Name": "Wipe mirror."
            }
        ],
        "ZoneCatId": "someid",
        "Zone": "zoneid99",
        "ZoneName": "zonename",
        "By":"KG",
        "EventSource": "HK"
    }
}
```

|Key|Value|
|---|---|
|Incident|parent object|
|Start|incident expected start time|
|End|incident expected end time|
|Name|name of incident|
|Priority|incident priority|
|Tasks|list of tasks associated|
|Tasks.Name|task name|
|ZoneCatId|zone category id|
|Zone|zone id of incident|
|ZoneName|zone name of incident|
|By|incident raised by|
|EventSource| source of event that raised the incident|