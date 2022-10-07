---
layout: default
title: Get Availabilities In Property For Day-Of-Week
parent: Availability
grand_parent: Workforce
has_children: true
nav_order: 1
---

### Get Availabilities In Property For Day-Of-Week

get availabilities in the entire property for a given day of week.

***Operation name:***

> scteams.getAvailabilityInPropertyForDow

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
| op | scteams.getAvailabilityInPropertyForDow | (Required) Operation Name |
| org | <<org>> | (Required) Organisation ID |
| pid | <<pid>> | (Required) Project OR building ID |
| propid | <<prop_id>> | (Required) Property ID |

***Request Body:***

```
{
    "DayOfWeek": 6
}
```

| Key | Value | Description |
| --- | ------|-------------|
|DayOfWeek|nth day of the week (Sunday(0); Saturday(6))|
