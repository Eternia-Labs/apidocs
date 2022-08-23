---
layout: default
title: Get System Incident Settings
parent: Settings
grand_parent: Workforce
has_children: true
nav_order: 1
---


### Get System Incident Settings

Get all or specific system incident settings

***Operation name:***

> scteams.getSystemIncidentSettings

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
| op | scteams.getSystemIncidentSettings | (Required) Operation Name |
| org | <<org>> | (Required) Organisation ID |
| pid | <<pid>> | (Required) Project OR building ID |
| propid | <<prop_id>> | (Required) Property ID |


***Request Body:***

### when querying for specific incident settings

```
{
    "IncidentSettings":{
        "IncidentSettings":{
            "ALLOW_DELETION_OPEN_INCIDENTS":{}
        }
    }
}
```

### when querying for all system incident settings

> no request body needed

|Key|Value|
|---|---|
|IncidentSettings|parent incident setting map|
|IncidentSettings.IncidentSettings|incident setting map|
|ALLOW_DELETION_OPEN_INCIDENTS|specific setting key|