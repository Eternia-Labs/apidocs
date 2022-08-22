---
layout: default
title: Update Seat Availability Zones
parent: Availability
grand_parent: Workforce
has_children: true
nav_order: 1
---

### Update Seat-Availability-Zones

Updates seat-availability-zones for a given Seat for the requested buildings of the property.

***Operation name:***

> scteams.updateAvailabilityZones

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
| op | scteams.updateAvailabilityZones | (Required) Operation Name |
| org | <<org>> | (Required) Organisation ID |
| pid | <<pid>> | (Required) Project OR building ID |
| propid | <<prop_id>> | (Required) Property ID |


***Request Body:***

```
{
    "SeatAvailabilityZones":{
        "SeatId":"3b749a681d14446292b6c79b48403bbd_003",
        "Zones": {
                "SONY": {
                    "zoneid2": "zone2",
                    "zoneid1": "zone122"
                },
                "TEST-PID": {
                    "zoneid2": "zone2",
                    "zoneid1": "zone1"
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