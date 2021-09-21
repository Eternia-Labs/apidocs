---
layout: default
title: listZoneAssetByZoneCategory
parent: Zone
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