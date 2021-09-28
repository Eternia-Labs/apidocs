---
layout: default
title: List Owner Org Properties
parent: Property
grand_parent: Grids
has_children: true
nav_order: 1
---

### 6. List Owner Org Properties


Op name:

> scgrids.listOwnerOrgProperties

This lists all the owner Org properties


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
| op | scgrids.listOwnerOrgProperties | (Required) Operation Name |
| org | {{org}} | (Required) Organisation Name |
| pid | scnoop | (Required) Project ID is scnoop when it's not known |



***Body:***

```js        
{
    "PropTypeID": "BANK"
}
```



***More example Requests/Responses:***


##### I. Example Request: List Owner Org Properties

***Body:***

```js        
{
    "PropTypeID": "BANK"
}
```

##### I. Example Response: List Owner Org Properties
```js
{
    "status": 200,
    "message": "Success",
    "data": [
        {
            "OrgId": "{{org}}",
            "PropId": "{{prop_id}}",
            "Name": "Test Property 10",
            "Address": {
                "Street": "16th Cross, J P Nagar",
                "City": "Bangalore",
                "State": "Karnataka",
                "Country": "India",
                "PostalCode": "560078",
                "Coordinates": {
                    "Latitude": 3.165725,
                    "Longitude": 101.646267
                }
            },
            "TypeID": "BANK",
            "Status": "INACTIVE",
            "TimeZone": "Asia/Kolkata"
        },
        {
            "OrgId": "{{org}}",
            "PropId": "{{prop_id}}",
            "Name": "Test Property 10",
            "Address": {
                "Street": "16th Cross, J P Nagar",
                "City": "Bangalore",
                "State": "Karnataka",
                "Country": "India",
                "PostalCode": "560078",
                "Coordinates": {
                    "Latitude": 3.165725,
                    "Longitude": 101.646267
                }
            },
            "TypeID": "BANK",
            "Status": "INACTIVE",
            "TimeZone": "Asia/Kolkata"
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

