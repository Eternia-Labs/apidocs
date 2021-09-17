---
layout: default
title: Update Level
parent: Grids Level
grand_parent: Grids
has_children: true
nav_order: 1
---


### 7. Update Level


Op name: 

> scgrids.updateLevel

This updates a Given Level details like FloorPlan, Area or Name.


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
| op | scgrids.updateLevel | (Required) Operation Name |
| org | {{org}} | (Required) Organisation ID |
| pid | {{pid}} | (Required) The Project ID |
| propid | {{prop_id}} | (Required) Property ID |



***Body:***

```js        
{
    "LID": "{{lid}}",
    "Area": 3000,
    "Level": "L10",
    "Name": "TestLevel"
}
```



***More example Requests/Responses:***


##### I. Example Request: Update Level


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Authorization | {{access_token}} | (Required) The Login Access Token |
| x-sc-identity | external | (Required) |



***Query:***

| Key | Value | Description |
| --- | ------|-------------|
| op | scgrids.updateLevel | (Required) Operation Name |
| org | {{org}} | (Required) Organisation ID |
| pid | {{pid}} | (Required) The Project ID |
| propid | {{prop_id}} | (Required) Property ID |



***Body:***

| Key | Value | Description |
| --- | ------|-------------|
| LID | {{lid}} |  |
| Name | New Name |  |
| file |  |  |
| Area | 5000 |  |
| Level | L10 |  |



##### I. Example Response: Update Level
```js
{
    "status": 200,
    "message": "Success",
    "data": {
        "Name": "New Name",
        "Level": "L10",
        "Area": 5000,
        "LID": "{{lid}}"
    }
}
```


***Status Code:*** 200

<br>