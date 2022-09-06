---
layout: default
title: Update Incident Settings
parent: Settings
grand_parent: Workforce
has_children: true
nav_order: 1
---


### Update Incident Settings

Update Incident Settings

***Operation name:***

> scteams.updateIncidentsSettings

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
| op | scteams.updateIncidentsSettings | (Required) Operation Name |
| org | <<org>> | (Required) Organisation ID |
| pid | <<pid>> | (Required) Project OR building ID |
| propid | <<prop_id>> | (Required) Property ID |


***Request Body:***

```
{
    "IncidentSettings":{
        "IncidentSettings":{
            "TASK_CLOSURE_PIC_COMPULSORY": {
                "BooleanValue": true,
                "Description": "If this is set to true, users must upload a picture before they can close the task.",
                "Type": "Boolean"
            }
        }
    }
}
```

|Key|Value|
|---|---|
|IncidentSettings|parent object|
|IncidentSettings|incident setting updated map|
|IncidentSettings.TASK_CLOSURE_PIC_COMPULSORY|the key of the Settings object to be updated|
|Settings.Description|updated description|
|Settings.BooleanValue|updated value of boolean type field|
|Settings.Type|data type of the value field being updated|