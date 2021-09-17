---
layout: default
title: listZoneAssetByZoneCategory
parent: Grids Zone
grand_parent: Grids
has_children: true
nav_order: 1
---



### 8. List Zone Asset By Zone Category


Op name: 

> scgrids.listZoneUnitsByZoneCategory

This lists all the stayet level Zone Units/Assets


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
| op | scgrids.listZoneAssetsByZoneCategory | (Required) Operation Name |
| org | {{org}} | (Required) Organisation ID |
| pid | scnoop | (Required) Project ID |



***Body:***

```js        
{
    "ZoneCategoryID": "CONFERENCE_ROOMS"
}
```



***More example Requests/Responses:***


##### I. Example Request: List Zone Units By Zone Category


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Authorization | {{access_token}} | (Required) The Login Access Token |
| x-sc-identity | external | (Required) |



***Query:***

| Key | Value | Description |
| --- | ------|-------------|
| op | scgrids.listZoneUnitsByZoneCategory | (Required) Operation Name |
| org | {{org}} | (Required) Organisation ID |
| pid | scnoop | (Required) The Project ID |



***Body:***

```js        
{
    "ZoneCategoryID": "CONFERENCE_ROOMS"
}
```



##### I. Example Response: List Zone Units By Zone Category
```js
{
    "status": 200,
    "message": "Success",
    "data": [
        {
            "Name": "Door/Opening",
            "ImageURL": "https://dummyimage.com/5:5x250",
            "ZoneCategoryID": "CONFERENCE_ROOMS",
            "UnitID": "DOOR/OPENING"
        },
        {
            "Name": "Windows",
            "ImageURL": "https://dummyimage.com/5:5x250",
            "ZoneCategoryID": "CONFERENCE_ROOMS",
            "UnitID": "WINDOWS"
        }
    ]
}
```


***Status Code:*** 200

<br>