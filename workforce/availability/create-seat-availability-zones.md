---
layout: default
title: Create Seat Availability Zones
parent: Availability
grand_parent: Workforce
has_children: true
nav_order: 1
---

### Create Seat-Availability-Zones

Creates seat-availability-zones for a given Seat. It defines in which zones of the property the Seat is available.

***Operation name:***

> scteams.createAvailabilityZones

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
| op | scteams.createAvailabilityZones | (Required) Operation Name |
| org | <<org>> | (Required) Organisation ID |
| pid | <<pid>> | (Required) Project OR building ID |
| propid | <<prop_id>> | (Required) Property ID |


***Request Body:***

```
{
    "SeatAvailabilityZones":{
        "SeatId":"3b749a681d14446292b6c79b48403bbd_009",
        "Zones": {
            "SONY":{
                "zoneid1":"zone1",
                "zoneid2":"zone2"
            }
        }
    }
}
```

| Key | Description |
| --- |-----|
|SeatAvailabilityZones|parent object|
|SeatId|seat-id of the seat|
|Zones|Map of building specific zones corresponding to each building-id|