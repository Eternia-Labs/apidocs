---
layout: default
title: Delete Incident Comments
parent: Incident
grand_parent: Workforce
has_children: true
nav_order: 1
---

### Delete Incident Comments

Delete Open incident comments.

***Operation name:***

> scteams.adminDeleteIncidentComment

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
| op | scteams.adminDeleteIncidentComment | (Required) Operation Name |
| org | <<org>> | (Required) Organisation ID |
| pid | <<pid>> | (Required) Project OR building ID |
| propid | <<prop_id>> | (Required) Property ID |


***Request Body:***

```
{
    "IncidentId":"1656053597407793546",
    "IncidentComment":{
        "CommentId":"4856ee7b-ceda-4dbb-ba43-683f20c9b5eb"
    }
}
```

| Key | Description |
| --- |-------------|
|IncidentId|id of the incident|
|IncidentComment| parent object|
|IncidentComment.CommentId|comment id of comment to be deleted|