---
layout: default
title: Delete Property Shift Settings
parent: Shift
grand_parent: Workforce
nav_order: 1
---


### Delete Property Shift Settings

Delete Property Shift Settings

***Operation name:***

> scteams.deleteShiftDefinitionForProperty

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
| op | scteams.deleteShiftDefinitionForProperty | (Required) Operation Name |
| org | <<org>> | (Required) Organisation ID |
| pid | <<pid>> | (Required) Project OR building ID |
| propid | <<prop_id>> | (Required) Property ID |


***Request Body:***

```
{
    "DaysOfWeek":[1,2,3,4]
}
```

|Key|Value|
|---|---|
|DaysOfWeek|list of numbers representing nth days of week|