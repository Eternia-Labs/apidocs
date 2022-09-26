---
layout: default
title: Find Availability For Incident
parent: Shift
grand_parent: Workforce
nav_order: 1
---


### Find Availability For Incident

Find Availability For Incident

***Operation name:***

> scteams.findAvailabilityForIncident-v2

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
| op | scteams.findAvailabilityForIncident-v2 | (Required) Operation Name |
| org | <<org>> | (Required) Organisation ID |
| pid | <<pid>> | (Required) Project OR building ID |
| propid | <<prop_id>> | (Required) Property ID |


***Request Body:***

```
{
    "EndTime": 1645976000,
    "ZoneID": [
        "71d899661d5645acb0b8f8030e26fc35"
    ]
}
```

|Key|Value|
|---|---|
|EndTime|time range end time|
|ZoneID|list of zone ids|