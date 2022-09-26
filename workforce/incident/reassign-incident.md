---
layout: default
title: Reassign Incident
parent: Incident
grand_parent: Workforce
has_children: true
nav_order: 1
---

### Reassign Incident

Reassign Incident.

***Operation name:***

> scteams.startUnassignedIncident

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
| op | scteams.startUnassignedIncident | (Required) Operation Name |
| org | <<org>> | (Required) Organisation ID |
| pid | <<pid>> | (Required) Project OR building ID |
| propid | <<prop_id>> | (Required) Property ID |


***Request Body:***

### Reassign from PUBLISHED/COMPLETED/INCOMPLETE to PUBLISHED

```
{
    "IncidentID":"1660643173874880217",
    "StartTime":1659745800,
    "EndTime":1659746000,
    "ShiftID":"3b749a681d14446292b6c79b48403bbd_007",
    "SeatId":"3b749a681d14446292b6c79b48403bbd_007",
    "NewSeatId": "3b749a681d14446292b6c79b48403bbd_002",
    "NewShiftId": "3b749a681d14446292b6c79b48403bbd_002"
}
```

### Reassign from PUBLISHED/COMPLETED/INCOMPLETE to OPEN

```
{
    "IncidentID":"1660643173874880217",
    "StartTime":1659745800,
    "EndTime":1659746000,
    "ShiftID":"3b749a681d14446292b6c79b48403bbd_007",
    "SeatId":"3b749a681d14446292b6c79b48403bbd_007"
}
```

| Key | Description |
| --- |-------------|
|IncidentID|incident id|
|StartTime|new start time|
|EndTime|new end time|
|ShiftID|current shift id of incident|
|SeatId|current seat id of incident|
|NewSeatId|new seatId of incident (optional required while assigning to PUBLISHED state)|
|NewShiftId|new shift id of incident (optional required while assigning to PUBLISHED state)|