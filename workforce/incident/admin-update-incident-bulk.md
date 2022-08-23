---
layout: default
title: Admin Update Incident Bulk
parent: Incident
grand_parent: Workforce
has_children: true
nav_order: 1
---

### Admin Update Incident Bulk

Update incident details and incident-zone.

***Operation name:***

> scteams.adminUpdateIncidentBulk

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
| op | scteams.adminUpdateIncidentBulk | (Required) Operation Name |
| org | <<org>> | (Required) Organisation ID |
| pid | <<pid>> | (Required) Project OR building ID |
| propid | <<prop_id>> | (Required) Property ID |


***Request Body:***

### updating details & zone of an unassigned incident

```
{
    "zoneId": "zoneid99",
    "IncidentId":"1660891710363880217",
    "UpdateIncident":{
        "Details":{
            "Name":"Clean mirron",
            "Description": "clean mirror new",
            "Priority": "L"
        },
        "Zones": {
            "NewZoneId":"",
            "NewZoneName": "new zone",
            "NewZoneCatId": "new zone cat"
        }
    }
}
```

### updating only details of an assigned incident

```
{
    "ShiftID": "shift id",
    "SeatId": "seat id",
    "IncidentId":"1660891710363880217",
    "UpdateIncident":{
        "Details":{
            "Name":"Clean Mirror",
            "Description": "clean mirror new",
            "Priority": "N"
        }
    }
}
```

|Key|Value|
|---|---|
|ShiftID|shift id of assigned incident|
|SeatId|seat id of assigned incident|
|zoneId|zone id of unassigned incident|
|IncidentId| incident id|
|UpdateIncident|parent object|
|UpdateIncident.Details|first child|
|UpdateIncident.Details.Name|new name of the incident|
|UpdateIncident.Details.Description|new description of the incident|
|UpdateIncident.Details.Priority|new priority|
|UpdateIncident.Zones|first child|
|UpdateIncident.Zones.NewZoneId| new zone id of incident|
|UpdateIncident.Zones.NewZoneName|new zone name|
|UpdateIncident.Zones.NewZoneCatId|new zone category id|