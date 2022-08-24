---
layout: default
title: Create Ad-Hoc Task
parent: TaskGroup
grand_parent: Workforce
has_children: false
nav_order: 1
---


### Add Task To Shift

Add Task To Shift

***Operation name:***

> scteams.addTaskgroupToShift

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
| op | scteams.addTaskgroupToShift | (Required) Operation Name |
| org | <<org>> | (Required) Organisation ID |
| pid | <<pid>> | (Required) Project OR building ID |
| propid | <<prop_id>> | (Required) Property ID |


***Request Body:***

```
{
    "EndTime":1635724918,
    "ZoneName":"Adhoc Task Zone",
    "By":"Sam",
    "ShiftID":"47f46a96-8e93-48c0-87b3-beba3c66875g",
    "zoneId":"zoneid2",
    "ZoneCategoryId":"someid"
}
```

|Key|Value|
|---|---|
|EndTime|task end time|
|ZoneName|zone name of task|
|By|adhoc task raised by|
|ShiftID|shift id of adhoc task|
|zoneId|zone id of adhoc task|
|ZoneCategoryId|zone categoryId of adhoc task|