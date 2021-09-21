---
layout: default
title: Get Level
parent: Level
grand_parent: Grids
has_children: true
nav_order: 1
---

### 5. Get Level


Op name: 

> scgrids.readLevel

This gets a given Level for a valid Project


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
| op | scgrids.readLevel | (Required) Operation Name |
| org | {{org}} | (Required) Organisation ID |
| pid | {{pid}} | (Required) Project ID |
| propid | {{propid}} | (Optional) Property ID |



***Body:***

```js        
{
    "LID": "{{lid}}"
}
```



***More example Requests/Responses:***


##### I. Example Request: Get Level

***Body:***

```js        
{
    "LID": "{{lid}}"
}
```

##### I. Example Response: Get Level
```js
{
    "status": 200,
    "message": "Success",
    "data": {
        "Name": "New Name",
        "Level": "L1",
        "Area": 5000,
        "FloorPlan": "{{floor_plan}}",
        "LID": "{{lid}}"
    }
}
```


***Status Code:*** 200

<br>