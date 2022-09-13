---
layout: default
title: Get System Schedule Settings
parent: Settings
grand_parent: Workforce
has_children: true
nav_order: 1
---


### Get System Schedule Settings

Get all or specific system schedule settings

***Operation name:***

> scteams.getSystemScheduleSettings

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
| op | scteams.getSystemScheduleSettings | (Required) Operation Name |
| org | <<org>> | (Required) Organisation ID |
| pid | <<pid>> | (Required) Project OR building ID |
| propid | <<prop_id>> | (Required) Property ID |


***Request Body:***

### when querying for specific schedule settings

```
{
    "ScheduleSettings":{
        "ScheduleSettings":{
            "END_SHIFT_OVERSHOOT":{}
        }
    }
}
```

### when querying for all system schedule settings

> no request body needed

|Key|Value|
|---|---|
|ScheduleSettings|parent schedule setting map|
|ScheduleSettings.ScheduleSettings|schedule setting map|
|END_SHIFT_OVERSHOOT|specific setting key|