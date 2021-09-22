---
layout: default
title: List Zones by Level
parent: Level
grand_parent: Grids
has_children: true
nav_order: 1
---


### 6. List Zones By Level


Op name: 

> scgrids.listZonesByLevel

This lists all the Zones for a given Level


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
| op | scgrids.listZonesByLevel | (Required) Operation Name |
| org | {{org}} | (Required) Organisation ID |
| pid | {{pid}} | (Required) Project ID |
| propid | {{propid}} | (Optional) Property ID |



***Body:***

```js        
{
    "LID": "{{lid}}",
    "ESK": "{{ESK}}"
}
```



***More example Requests/Responses:***


##### I. Example Request: List Zones By Level

***Body:***

```js        
{
    "LID": "{{lid}}",
    "ZoneCategoryIDs": [
        "LABS"
    ],
    "ESK": "{{ESK}}"
}
```

##### I. Example Response: List Zones By Level
```js
{
    "status": 200,
    "message": "Success",
    "data": [
        {
            "InsID": "{{insid}}",
            "LID": "{{lid}}",
            "ZoneCategoryID": "LABS",
            "Name": "New test name",
            "Area": 6000,
            "FloorType": "Test floor type",
            "Status": "PENDING"
        },
        {
            "InsID": "{{insid}}",
            "LID": "{{lid}}",
            "ZoneCategoryID": "LABS",
            "Name": "Zone 5",
            "Area": 3000,
            "FloorType": "hardwood",
            "Status": "active"
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

###### 3. Missing LID in the body

###### 4. If the ZoneCategories filter array reached more than 10

<br>