---
layout: default
title: Create Incident
parent: TaskGroup
grand_parent: Workforce
has_children: false
nav_order: 1
---


### Create Incident

Create Incident (Assigned Incidents) to report an Incident in published state to a given Shift or Seat. An incident can be reported to a published Shift or even to a Seat directly(in which case the ShiftId is same as the SeatId).

***Operation name:***

> scteams.createIncident

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
| op | scteams.createIncident | (Required) Operation Name |
| org | <<org>> | (Required) Organisation ID |
| pid | <<pid>> | (Required) Project OR building ID |
| propid | <<prop_id>> | (Required) Property ID |


***Request Body:***

### when reporting an Incident to a published Shift

```
{
    "Taskgroup": {
        "SeatId": "3b749a681d14446292b6c79b48403bbd_007",
        "ShiftId": "d4ca22ec-900d-4e7a-86ce-96144b7205e5",
        "EventSource": "Sensors",
        "Start": 1660432080,
        "End": 1660430080,
        "PropID": "SONY",
        "Tasks": [
            {
                "Name": "Clean floor."
            },
            {
                "Name": "Mop floor"
            }
        ],
        "ZoneName": "Zone name",
        "ZoneCatId": "MEETING_ROOMS",
        "Zone": "71d899661d5645acb0b8f8030e26fc35"
    }
}
```

### when reporting an Incident to a SeatId

```
{
    "Taskgroup": {
        "SeatId": "3b749a681d14446292b6c79b48403bbd_007",
        "ShiftId": "3b749a681d14446292b6c79b48403bbd_007",
        "EventSource": "Sensors",
        "Start": 1660432080,
        "End": 1660430080,
        "PropID": "SONY",
        "Tasks": [
            {
                "Name": "Clean floor."
            },
            {
                "Name": "Mop floor"
            }
        ],
        "ZoneName": "Zone name",
        "ZoneCatId": "MEETING_ROOMS",
        "Zone": "71d899661d5645acb0b8f8030e26fc35"
    }
}
```

|Key|Value|
|---|---|
|Taskgroup|parent object|
|SeatId|seat id of incident|
|ShiftId| shift id of incident|
|EventSource|source of event that raised the incident|
|Start| incident expected start time|
|End|incident expected end time|
|PropID|property id (optional)|
|Tasks|task list|
|ZoneName|zone name of zone|
|ZoneCatId|zone category id of zone|
|Zone|zone id of incident|