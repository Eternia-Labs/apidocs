---
layout: default
title: Get Tasks In Shift By ShiftId
parent: TaskGroup
grand_parent: Workforce
has_children: false
nav_order: 1
---


### Get Tasks In Shift By ShiftId

Get Tasks In Shift By ShiftId

***Operation name:***

> scteams.getTasksForShiftById

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
| op | scteams.getTasksForShiftById | (Required) Operation Name |
| org | <<org>> | (Required) Organisation ID |
| pid | <<pid>> | (Required) Project OR building ID |
| propid | <<prop_id>> | (Required) Property ID |


***Request Body:***

```
{
    "ShiftID":"9dec3fd3-51c1-43c4-921b-f549d9c3c185"
}
```

|Key|Value|
|---|---|
|ShiftID|shift id|