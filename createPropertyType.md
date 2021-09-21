---
layout: default
title: Create Property Type
parent: Property
grand_parent: Grids
has_children: true
nav_order: 1
---


### 2. Create Property Type


Op name:

> scgrids.createPropertyType

This creates a type of Property at the system level


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
| op | scgrids.createPropertyType | (Required) Operation Name |
| org | {{org}} | (Required) Organisation ID |
| pid | scnoop | (Required) Project ID is scnoop when it's not known |



***Body:***

```js        
{
    "Name": "Commercial Buildings",
    "TypeID": "COMMERCIAL_BUILDINGS"
}
```



***More example Requests/Responses:***


##### I. Example Request: Create PropertyType

***Body:***

```js        
{
    "Name": "Commercial Buildings",
    "TypeID": "COMMERCIAL_BUILDINGS"
}
```

##### I. Example Response: Create PropertyType
```js
{
    "status": 201,
    "message": "Success",
    "data": {
        "Name": "Commercial Buildings",
        "TypeID": "COMMERCIAL_BUILDINGS"
    }
}
```


***Status Code:*** 201

<br>
