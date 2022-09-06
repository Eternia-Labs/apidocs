---
layout: default
title: Update Property Shift Settings
parent: Shift
grand_parent: Workforce
nav_order: 1
---


### Update Property Shift Settings

Update Property Shift Settings

***Operation name:***

> scteams.updateShiftDefinitionForProperty

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
| op | scteams.updateShiftDefinitionForProperty | (Required) Operation Name |
| org | <<org>> | (Required) Organisation ID |
| pid | <<pid>> | (Required) Project OR building ID |
| propid | <<prop_id>> | (Required) Property ID |


***Request Body:***

```
{
    "PropertyShiftSetting":{
        "ShiftSettings":[
            {
                "End":61200,
                "Start":68800,
                "Name":"evening Shift",
                "ColorCode": "#ffffff",
                "ExpectedPresentByTeam":{
                    "b633094b-8516-4283-b849-ccb9776ada88":5
                }
            },
            {
                "End":28800,
                "Start":0,
                "Name":"Night Shift",
                "ExpectedPresent":10,
                "ColorCode": "#ffffff"
            }
        ],
        "DayOfWeek":1
    }
}
```

|Key|Value|
|---|---|
|PropertyShiftSetting|parent object|
|ShiftSettings|list of Shift-Settings|
|ShiftSettings.End|shift end time|
|ShiftSettings.Start|shift start time|
|ShiftSettings.Name|shift name|
|ShiftSettings.ColorCode|shift color code|
|ShiftSettings.ExpectedPresentByTeam|optional field having number of people from each team expected in the shift|
|DayOfWeek|nth day of week(0 => Sunday, 6 => Saturday)|