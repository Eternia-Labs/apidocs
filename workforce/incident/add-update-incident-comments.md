---
layout: default
title: Add/Update Incident Comment
parent: Incident
grand_parent: Workforce
has_children: true
nav_order: 1
---

### Add/Update Incident Comment

Add a new comment or update an existing comment for a given Incident.

***Operation name:***

> scteams.updateIncidentComment

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
| op | scteams.updateIncidentComment | (Required) Operation Name |
| org | <<org>> | (Required) Organisation ID |
| pid | <<pid>> | (Required) Project OR building ID |
| propid | <<prop_id>> | (Required) Property ID |


***Request Body:***

### adding new comment to an assigned incident

```
{
    "IncidentId":"1660643173874880217",
    "ShiftID":"3b749a681d14446292b6c79b48403bbd_007",
    "SeatId": "3b749a681d14446292b6c79b48403bbd_007",
    "IncidentComment":{
        "Comment":"this is the first updated comment.",
        "UserName":"kg"
    }
}
```

### adding new comment to an un-assigned incident

```
{
    "IncidentId":"1660643173874880217",
    "zoneId": "zone99",
    "IncidentComment":{
        "Comment":"this is the first updated comment.",
        "UserName":"kg"
    }
}
```

### updating an existing comment of an assigned incident

```
{
    "IncidentId":"1660643173874880217",
    "ShiftID":"3b749a681d14446292b6c79b48403bbd_007",
    "SeatId": "3b749a681d14446292b6c79b48403bbd_007",
    "IncidentComment":{
        "CommentId":"bc58c5ab-54e0-44e8-aa40-96fdf4420e60",
        "Comment":"this is the first updated comment.",
        "UserName":"kg"
    }
}
```

|Key|Value|
|---|---|
|IncidentId|incident id|
|ShiftID|shift id of incident (for assigned incident)|
|SeatId|seat id of the shift (for assigned incident)|
|zoneId|incident zone id (for unassigned incident)|
|IncidentComment|parent object|
|IncidentComment.CommentId|comment id of comment to be updated|
|IncidentComment.Comment|new or updated comment|
|IncidentComment.UserName|name of the person making the comment|