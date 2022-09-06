---
layout: default
title: Update Task Attachments
parent: TaskGroup
grand_parent: Workforce
has_children: false
nav_order: 1
---


### Update Task Attachments

Update Task Attachments

***Operation name:***

> scteams.updateAttachments

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
| op | scteams.updateAttachments | (Required) Operation Name |
| org | <<org>> | (Required) Organisation ID |
| pid | <<pid>> | (Required) Project OR building ID |
| propid | <<prop_id>> | (Required) Property ID |


***Request Body:***

```
{
    "ShiftID":"3b749a681d14446292b6c79b48403bbd_007",
    "SeatId":"3b749a681d14446292b6c79b48403bbd_007",
    "IncidentId":"1660643173874880217",
    "Attachments":["abc","def","ghi"]
}
```

|Key|Value|
|---|---|
|ShiftID|shift id of task|
|SeatId|seat id of task|
|IncidentId|task id|
|Attachments|list of file urls|