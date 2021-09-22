---
layout: default
title: List Zones by ZoneCategory
parent: Zone
grand_parent: Grids
has_children: true
nav_order: 1
---


### 13. ListZoneByZoneCategory


Op name:

> scgrids.listZonesByZoneCategory

This lists all the Zones for a given ZoneCategory


***Endpoint:***

```bash
Method: POST
Type: application/json
URL: /v1/actions
```


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Authorization | {{access_token}} | (Required) The Acccess Token or HMAC Signature |
| x-sc-identity | external | (Required) |



***Query params:***

| Key | Value | Description |
| --- | ------|-------------|
| op | scgrids.listZonesByZoneCategory |  |
| org | {{org}} |  |
| pid | {{pid}} |  |



***Body:***

```js        
{
    "ZoneCategoryID": "{{zone_category_id}}",
    "ESK": "{{insid}}"
}
```



***More example Requests/Responses:***


##### I. Example Request: ListZoneByZoneCategory


***Body:***

```js        
{
    "ZoneCategoryID": "{{zone_category_id}}",
     "ExclusiveStartKey": "{{insid}}"
}
```

##### I. Example Response: ListZoneByZoneCategory
```js
{
    "status": 200,
    "message": "Success",
    "data": [
        {
            "InsID": "{{insid}}",
            "LID": "{{lid`}}",
            "ZoneCategoryID": "{{zone_category_id}}",
            "Name": "Zone 5",
            "Area": 3000,
            "FloorType": "hardwood",
            "Status": "active",
            "PID": "{{pid}}"
        },
        {
            "InsID": "{{insid}}",
            "LID": "{{lid`}}",
            "ZoneCategoryID": "{{zone_category_id}}",
            "Name": "Zone 5",
            "Area": 3000,
            "FloorType": "hardwood",
            "Status": "active",
            "PID": "{{pid}}"
        }
    ],
    "LEK": "{{LEK}}"
}
```


***Status Code:*** 200


***Error codes:***

##### 400
##### Possible reasons:

###### 1. Missing op/org/pid

###### 3. Missing ZoneCategoryID in the body

<br>