---
layout: default
title: Create Level
parent: Level
grand_parent: Grids
has_children: true
nav_order: 1
---

### 2. Create Level


Op name: 

> scgrids.createLevel

This creates a Level object for a given Building


***Endpoint:***

```bash
Method: POST
Type: application/json
URL: /v1/actions
```


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Authorization | {{access_token}} | (Required) The Access Token or HMAC Signature |
| x-sc-identity | external | (Required) |



***Query params:***

| Key | Value | Description |
| --- | ------|-------------|
| op | scgrids.createLevel | (Required) Operation Name |
| org | {{org}} | (Required) Organisation ID |
| pid | {{pid}} | (Required) Project ID |
| propid | {{propid}} | (Optional) Property ID |



***Body:***

```js        
{
    "Name": "JWT Level Test 3",
    "FloorPlan": "{{floor_plan}}",
    "Level": "L29"
}
```



***More example Requests/Responses:***


##### I. Example Request: Create Level


***Body:***

```js        
{
    "Name": "Level 25",
    "FloorPlan": "{{floor_plan}}",
    "Level": "L25"
}
```

##### I. Example Response: Create Level
```js
{
    "status": 201,
    "message": "Successfully created the level!",
    "data": {
        "Name": "Level 25",
        "FloorPlan": "{{floor_plan}}",
        "LID": "{{lid}}"
    }
}
```


***Status Code:*** 201

***Error codes:***

##### 400

##### Possible reasons:

###### 1. Missing op/org/pid/propid

###### 2. Invalid characters/improper input body

###### 3. Missing access_token in the header

###### 6. If the level name is already taken under the given building

###### 7. If the given building is not found

<br>
