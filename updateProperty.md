---
layout: default
title: Create Property
parent: Property
grand_parent: Grids
has_children: true
nav_order: 1
---


### 9. Update Property


Op name: 

> scgrids.updateProperty

This updates a given Property's Name or Status


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
| op | scgrids.updateProperty | (Required) Operation Name |
| org | {{org}} | (Required) Organisation ID |
| pid | scnoop | (Required) Project ID is scnoop when it's not known |
| propid | {{prop_id}} | (Required) Property ID |



***Body:***

```js        
{
    "Status": "Pending"
}
```



***More example Requests/Responses:***


##### I. Example Request: scgrids.updateProperty

***Body:***

```js        
{
    "Status": "Pending"
}
```

##### I. Example Response: scgrids.updateProperty
```js
{
    "status": 200,
    "message": "Success",
    "data": {
        "OrgId": "{{org}}",
        "PropId": "{{prop_id}}",
        "Name": "Test Property",
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
        "TypeID": "SCHOOL",
        "Status": "Pending"
    }
}
```


***Status Code:*** 200

***Error codes:***

##### 400
##### Possible reasons:

###### 1. Missing op/org/pid/propid

<br>