---
layout: default
title: List Zone Categories
parent: Grids Zone
grand_parent: Grids
has_children: true
nav_order: 1
---



### 9. List Zone Categories


Op name: 

> scgrids.listZoneCategories

This lists all the system level Zone categories for a given Property type


***Endpoint:***

```bash
Method: POST
Type: RAW
URL: /v1/actions
```


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Authorization | {{access_token}} | (Required) Login Access Token |
| x-sc-identity | external | (Required) |



***Query params:***

| Key | Value | Description |
| --- | ------|-------------|
| op | scgrids.listZoneCategories | (Required) Operation Name |
| org | {{org}} | (Required) Organisation ID |
| pid | scnoop | (Required) Project ID is scnoop when it's not known |



***Body:***

```js        
{
    "PropertyTypeID": "{{property_type}}"
}
```



***More example Requests/Responses:***


##### I. Example Request: List Zone Categories


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Authorization | {{access_token}} | (Required) THe Login Access Token |
| x-sc-identity | external | (Required) |



***Query:***

| Key | Value | Description |
| --- | ------|-------------|
| op | scgrids.listZoneCategories | (Required) Operation Name |
| org | {{org}} | (Required) Organisation ID |
| pid | scnoop | (Required) Project ID is scnoop when it's not known |



***Body:***

```js        
{
    "PropertyTypeID": "{{property_type}}"
}
```



##### I. Example Response: List Zone Categories
```js
{
    "status": 200,
    "message": "Success",
    "data": [
        {
            "Name": "Auditoriums/Theaters",
            "PropertyTypeID": "SCHOOL",
            "CategoryID": "AUDITORIUMS/THEATERS"
        },
        {
            "Name": "Classrooms",
            "PropertyTypeID": "SCHOOL",
            "CategoryID": "CLASSROOMS"
        },
        {
            "Name": "Labs",
            "PropertyTypeID": "SCHOOL",
            "CategoryID": "LABS"
        },
        {
            "Name": "Swimming Pools",
            "PropertyTypeID": "SCHOOL",
            "CategoryID": "SWIMMING_POOLS"
        }
    ]
}
```


***Status Code:*** 200

<br>