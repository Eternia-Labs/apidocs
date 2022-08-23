---
layout: default
title: Update Shift Settings
parent: Settings
grand_parent: Workforce
has_children: true
nav_order: 1
---


### Update Shift Settings

Update Shift Settings

***Operation name:***

> scteams.updateSettings

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
| op | scteams.updateSettings | (Required) Operation Name |
| org | <<org>> | (Required) Organisation ID |
| pid | <<pid>> | (Required) Project OR building ID |
| propid | <<prop_id>> | (Required) Property ID |


***Request Body:***

```
{
    "ScheduleSettings":{
        "ScheduleSettings":{
            "DEFAULT_SHIFT_DURATION":{
                "Description":"The default time to use for clocking out unscheduled shifts.",
                "LongValue":28800,
                "Type":"Long"
            }
        }
    }
}
```

|Key|Value|
|---|---|
|ScheduleSettings|parent object|
|ScheduleSettings|schedule setting updated map|
|ScheduleSettings.DEFAULT_SHIFT_DURATION|the key of the Settings object to be updated|
|Settings.Description|updated description|
|Settings.LongValue|updated value of long type field|
|Settings.Type|data type of the value field being updated|