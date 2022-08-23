---
layout: default
title: Get Incident Comments
parent: Incident
grand_parent: Workforce
has_children: true
nav_order: 1
---

### Get Incident Comments

Get Incident Comments.

***Operation name:***

> scteams.listIncidentComments

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
| op | scteams.listIncidentComments | (Required) Operation Name |
| org | <<org>> | (Required) Organisation ID |
| pid | <<pid>> | (Required) Project OR building ID |
| propid | <<prop_id>> | (Required) Property ID |


***Request Body:***

```
{
    "IncidentId":"1656058344842880217"
}
```

|Key|Value|
|---|---|
|IncidentId|incident id|