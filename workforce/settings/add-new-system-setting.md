---
layout: default
title: Add New System Settings
parent: Settings
grand_parent: Workforce
has_children: true
nav_order: 1
---


### Add New available System Settings

Add New System Settings to the building level settings.

***Operation name:***

> scteams.addNewSystemSettings

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
| op | scteams.addNewSystemSettings | (Required) Operation Name |
| org | <<org>> | (Required) Organisation ID |
| pid | <<pid>> | (Required) Project OR building ID |
| propid | <<prop_id>> | (Required) Property ID |


***Request Body:***

```
{
    "ScheduleSettings":{
        "ScheduleSettings":{
            "END_SHIFT_OVERSHOOT":{}
        }
    },
    "IncidentSettings":{
        "IncidentSettings":{
            "":{}
        }
    }
}
```

|Key|Value|
|---|---|
|ScheduleSettings|schedule setting parent map|
|ScheduleSettings.ScheduleSettings|updated schedule setting map|
|ScheduleSettings.END_SHIFT_OVERSHOOT|newly added system level setting key|
|IncidentSettings|incident setting parent map|
|IncidentSettings.IncidentSettings|updated incident setting map|