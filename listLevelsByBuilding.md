---
layout: default
title: List Levels by Building
parent: Grids Building
grand_parent: Grids
has_children: true
nav_order: 1
---

### 5. List Levels By Building


OP name: 

> scgrids.listLevelsByBuilding

This lists the levels for a given Building


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
| op | scgrids.listLevelsByBuilding | (Required) Operation Name |
| org | {{org}} | (Required) Organisation ID |
| pid | {{pid}} | (Required) Project ID |



***More example Requests/Responses:***


##### I. Example Request: List Levels By Building


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Authorization | {{access_token}} | (Required) The Login Access Token |
| x-sc-identity | external | (R)equired |



***Query:***

| Key | Value | Description |
| --- | ------|-------------|
| op | scgrids.listLevelsByBuilding | (Required) Operation Name |
| org | {{org}} | (Required) Organisation ID |
| pid | {{pid}} | (Required) The Project ID |



##### I. Example Response: List Levels By Building
```js
{
    "status": 200,
    "message": "Success",
    "data": [
        {
            "Name": "Level 3",
            "Level": "L3",
            "LID": "{{lid}}"
        },
        {
            "Name": "Level 4",
            "Level": "L4",
            "LID": "{{lid}}"
        },
        {
            "Name": "Level 2",
            "Level": "L2",
            "LID": "{{lid}}"
        },
        {
            "Name": "Level 8",
            "Level": "L8",
            "LID": "{{lid}}"
        },
        {
            "Name": "New Name",
            "Level": "L1",
            "Area": 5000,
            "LID": "{{lid}}"
        },
        {
            "Name": "Level 9",
            "Level": "L9",
            "LID": "{{lid}}"
        },
        {
            "Name": "Level 6",
            "Level": "L6",
            "LID": "{{lid}}"
        },
        {
            "Name": "Level 7",
            "Level": "L7",
            "LID": "{{lid}}"
        },
        {
            "Name": "Level 5",
            "Level": "L5",
            "LID": "{{lid}}"
        },
        {
            "Name": "Level 0",
            "Level": "L0",
            "LID": "{{lid}}"
        }
    ]
}
```


***Status Code:*** 200

<br>