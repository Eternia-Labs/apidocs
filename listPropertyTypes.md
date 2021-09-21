---
layout: default
title: List Property Types
parent: Property
grand_parent: Grids
has_children: true
nav_order: 1
---


### 8. List Property Types


Op name: 

> scgrids.listPropertyTypes 

This lists all the system level Property types


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
| op | scgrids.listPropertyTypes | (Required) Operation Name |
| org | {{org}} | (Required) Organisation ID |
| pid | scnoop | (Required) Project ID is scnoop when it's not known |



***More example Requests/Responses:***

##### I. Example Response: List PropertyTypes
```js
{
    "status": 200,
    "message": "Success",
    "data": [
        {
            "Name": "Bank",
            "TypeID": "BANK"
        },
        {
            "Name": "Commercial Buildings",
            "TypeID": "COMMERCIAL_BUILDINGS"
        },
        {
            "Name": "Corporate Buildings",
            "TypeID": "CORPORATE_BUILDINGS"
        },
        {
            "Name": "Restaurants",
            "TypeID": "RESTAURANTS"
        },
        {
            "Name": "School",
            "TypeID": "SCHOOL"
        }
    ]
}
```


***Status Code:*** 200


***Error codes:***

##### 400
##### Possible reasons:
###### 1. Missing op/org/pid


<br>