---
layout: default
title: Get Incident Timeline
parent: Incident
grand_parent: Workforce
has_children: true
nav_order: 1
---

### Get Incident Timeline

Get Incident Timeline.

***Operation name:***

> scteams.getIncidentTimeline

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
| op | scteams.getIncidentTimeline | (Required) Operation Name |
| org | <<org>> | (Required) Organisation ID |
| pid | <<pid>> | (Required) Project OR building ID |
| propid | <<prop_id>> | (Required) Property ID |


***Request Body:***

```
{
    "zoneId":"zoneid99",
    "IncidentID":"1656056805791023771"
}
```

|Key|Value|
|---|---|
|zoneId|incident zone id|
|IncidentID|incident id|