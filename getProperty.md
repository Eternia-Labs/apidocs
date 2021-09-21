---
layout: default
title: Get Property
parent: Property
grand_parent: Grids
has_children: true
nav_order: 1
---


### 3. Get Property


Op name:

> scgrids.readProperty 

This gets a Property by ID


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
| op | scgrids.readProperty | (Required) Operation Name |
| org | {{org}} | (Required) Organisation ID |
| pid | scnoop | (Required) Project ID is scnoop when it's not known |
| propid | {{propid}} | (Optional) Property ID |



***More example Requests/Responses:***

##### I. Example Response: Get Property
```js
{
    "status": 200,
    "message": "Success",
    "data": {
        "OrgId": "SMARTCLEAN",
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
        "Status": "Active"
    }
}
```


***Status Code:*** 200

<br>


