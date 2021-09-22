---
layout: default
title: Update Level
parent: Level
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
Type: FORMDATA
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

***Error codes:***

##### 400
##### Possible reasons:

###### 1. Missing op/org/pid

###### 3. Missing LID in the body

###### 4. Missing access_token in the header

<br>
