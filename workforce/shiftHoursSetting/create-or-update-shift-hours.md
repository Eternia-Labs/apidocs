---
layout: default
title: Create Or Update Shift Hours
parent: ShiftHourSetting
grand_parent: Workforce
has_children: false
nav_order: 1
---

# Create Or Update Shift Hours
Creates new ShiftHours settings for a property if not exists or updated it.

***Operation name:***

> scteams.updateShiftHoursForProperty

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
| op | scteams.updateShiftHoursForProperty | (Required) Operation Name |
| org | <<org>> | (Required) Organisation ID |
| pid | <<pid>> | (Required) Project OR building ID |
| propid | <<prop_id>> | (Required) Property ID |


***Request Body:***

```
{
    "ShiftHours":[
        {
            "ShiftName":"Morning Shift",
            "ColorCode":"#fff123",
            "Start": 123456,
            "End": 234567
        },
        {
            "ShiftName":"evening Shift",
            "ColorCode":"#fff123",
            "Start": 234567,
            "End": 334567
        }
    ]
}
```

### ShiftHour

|Key|Description|
|---|---|
|ShiftHours|list object|
|ColorCode|hex color code of the shift|
|ShiftName|shift name|
|Start|shift start time in epoch seconds|
|End|shift end time in epoch seconds|