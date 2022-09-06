---
layout: default
title: Update Open Incident attachments
parent: Incident
grand_parent: Workforce
has_children: true
nav_order: 1
---

### Update Open Incident attachments

Update Open incident attachments.

***Operation name:***

> scteams.updateUnassignedIncidentAttachments

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
| op | scteams.updateUnassignedIncidentAttachments | (Required) Operation Name |
| org | <<org>> | (Required) Organisation ID |
| pid | <<pid>> | (Required) Project OR building ID |
| propid | <<prop_id>> | (Required) Property ID |


***Request Body:***

```
{
    "IncidentId":"1620209183000",
    "zoneId":"zoneid3",
    "Attachments":["ghi","jkl"]
}
```

| Key | Description |
| --- |-------------|
|IncidentId|id of the incident|
|zoneId| zone id of the incident|
|Attachments|list of attachment urls|