---
layout: default
title: Approve Multiple TimeSheets For A Property
parent: TimeSheet
grand_parent: Workforce
nav_order: 1
---

### Approve Multiple TimeSheets For A Property

Approves multiple time-sheets raised in a given property.

***Operation name:***

> scteams.approveMultipleTimeSheetsForProperty

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
| op | scteams.approveMultipleTimeSheetsForProperty | (Required) Operation Name |
| org | <<org>> | (Required) Organisation ID |
| pid | <<pid>> | (Required) Project OR building ID |
| propid | <<prop_id>> | (Required) Property ID |

***Request Body:***

```
{
    "ApprovedBy": "KG12",
    "TimeSheets": [
        {
            "ID": "SONY",
            "SeatId": "3b749a681d14446292b6c79b48403bbd_007",
            "ShiftId": "1d3224a6-4004-4965-b84b-4c93b7c72ae1",
            "Comments": "approving with comments new new"
        },
        {
            "ID": "SONY",
            "SeatId": "3b749a681d14446292b6c79b48403bbd_007",
            "ShiftId": "c02f8510-0f98-4fa0-862d-a43b43d439a1"
        }
    ]
}
```

|Key|Value|
|---|---|
|ApprovedBy|approved by|
|TimeSheets|parent list object|
|TimeSheets[0].ID|timesheet id|
|TimeSheets[0].SeatId|timesheet seat id|
|TimeSheets[0].ShiftId|timesheet shift id|
|TimeSheets[0].Comments|comments by approver(optional)|