---
layout: default
title: Delete Availability
parent: Availability
grand_parent: Workforce
has_children: true
nav_order: 1
---

### Delete Seat Availabilities

Delete availabilities for a given Seat for all the requested days of the week.

***Operation name:***

> scteams.deleteSeatAvailability

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
| op | scteams.deleteSeatAvailability | (Required) Operation Name |
| org | <<org>> | (Required) Organisation ID |
| pid | <<pid>> | (Required) Project OR building ID |
| propid | <<prop_id>> | (Required) Property ID |

***Request Body:***

```
{
    "SeatId":"3b749a681d14446292b6c79b48403bbd_003",
    "Availability":{
        "DaysOfWeek":[4,5,6]
    }
}
```

| Key | Description |
| --- |-----|
|SeatId|SeatId of the user|
|Availability|availability object|
|Availability.DaysOfWeek|list of number representing nth day of week whose availability is to be deleted|