---
layout: default
title: List Property
parent: Property
grand_parent: Grids
has_children: true
nav_order: 1
---


### 7. List Properties


Op name: 

> scgrids.listProperties

This lists all the Properties for an Organisation and can filter them by type of Property


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
| op | scgrids.listProperties | (Required) Operation name |
| org | {{org}} | (Required) Organisation ID |
| pid | scnoop | (Required) Project ID is scnoop when it's not known |



***More example Requests/Responses:***

##### I. Example Response: List Properties
```js
{
    "status": 200,
    "message": "Success",
    "data": [
        {
            "OrgId": "{{org}}",
            "PropId": "{{prop_id}}",
            "Name": "Test Property for getProperty query change to SUB1",
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
            "TypeID": "TEST",
            "Status": "Active",
            "TimeZone": "Asia/Kolkata"
        },
        {
            "OrgId": "{{org}}",
            "PropId": "{{prop_id}}",
            "Name": "Test Property for getProperty query change to SUB1",
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
            "Status": "Active",
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