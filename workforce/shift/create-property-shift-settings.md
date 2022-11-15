---
layout: default
title: Create Property Shift Settings
parent: Shift
grand_parent: Workforce
nav_order: 1
---


### Create Property Shift Settings

Create Property Shift Settings defines Shift definition for a given property on a given day of the week. A property can be configured to have different Shift schedules for different days of the week. Each Shift schedule is independent of the other and hence the time span of one shift schedule can overlap with the other.

***Operation name:***

> scteams.createShiftDefinitionForProperty

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
| op | scteams.createShiftDefinitionForProperty | (Required) Operation Name |
| org | <<org>> | (Required) Organisation ID |
| pid | <<pid>> | (Required) Project OR building ID |
| propid | <<prop_id>> | (Required) Property ID |


***Request Body:***

```
{
    "PropertyShiftSetting":{
        "ShiftSettings":[
            {
                "End": 61200,
                "Start": 28800,
                "Name": "Morning Shift",
                "ColorCode": "somecode"
            }
        ],
        "DaysOfWeek":[1,2,3,4]
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
|DayOfWeek|nth day of week(0 => Sunday, 6 => Saturday)|