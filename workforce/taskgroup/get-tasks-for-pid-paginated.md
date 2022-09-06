---
layout: default
title: Get Paginated Tasks List for Building
parent: TaskGroup
grand_parent: Workforce
has_children: false
nav_order: 1
---


### Get Paginated Tasks List for Building

Get Paginated Tasks List for Building

***Operation name:***

> scteams.getTasksForIDPaginated

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
| op | scteams.getTasksForIDPaginated | (Required) Operation Name |
| org | <<org>> | (Required) Organisation ID |
| pid | <<pid>> | (Required) Project OR building ID |
| propid | <<prop_id>> | (Required) Property ID |


***Request Body:***

```
{
    "StartTime": 1616134038,
    "EndTime" : 1646719364,
    "Type" : "TASK"
}
```

|Key|Value|
|---|---|
|Type|task type (optional)|
|EndTime|time range end time|
|StartTime|time range start time|