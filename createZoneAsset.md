---
layout: default
title: Create Zone Asset
parent: Grids Zone
grand_parent: Grids
has_children: true
nav_order: 1
---


### 2. Create Zone Asset


Op name:

> scgrids.createZoneUnit

This creates a Zone Unit/Asset like door or window


***Endpoint:***

```bash
Method: POST
Type: RAW
URL: /v1/actions
```


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Authorization | {{access_token}} | (Required) The Login Access Token |
| x-sc-identity | external | (Required) |



***Query params:***

| Key | Value | Description |
| --- | ------|-------------|
| op | scgrids.createZoneAsset | (Required) Operation Name |
| org | {{org}} | (Required) Organisation ID |
| pid | {{pid}} | (Required) Project ID |



***Body:***

```js        
{
    "Name": "Door/Opening",
    "UnitID": "DOOR/CLOSING",
    "ImageURL": "https://dummyimage.com/5:5x250",
    "ZoneCategoryID": "CONFERENCE_ROOMS"
}
```



***More example Requests/Responses:***


##### I. Example Request: Create Zone Asset


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Authorization | {{access_token}} | (Required) The Login Access Token |
| x-sc-identity | external | (Required) |



***Query:***

| Key | Value | Description |
| --- | ------|-------------|
| op | scgrids.createZoneUnit | (Required) Operation Name |
| org | {{org}} | (Required) Organisation ID |
| pid | {{pid}} | (Required) The Project ID |



***Body:***

```js        
{
    "Name": "Door/Opening",
    "UnitID": "DOOR/OPENING",
    "ImageURL": "https://dummyimage.com/5:5x250",
    "ZoneCategoryID": "CONFERENCE_ROOMS"
}
```



##### I. Example Response: Create Zone Asset
```js
{
    "status": 201,
    "message": "Success",
    "data": {
        "Name": "Door/Opening",
        "ImageURL": "https://dummyimage.com/5:5x250",
        "ZoneCategoryID": "CONFERENCE_ROOMS",
        "UnitID": "DOOR/OPENING"
    }
}
```


***Status Code:*** 201

<br>