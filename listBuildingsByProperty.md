---
layout: default
title: List Buildings By Property
parent: Property
grand_parent: Grids
has_children: true
nav_order: 1
---

### 5. List Buildings By Property


Op name: 

> scgrids.listBuildingsByProperty

This lists all the buildings under a given listBuildingsByProperty


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
| op | scgrids.listBuildingsByProperty | (Required) Operation Name |
| org | {{org}} | (Required) Organisation ID |
| pid | scnoop | (Required) Project ID is scnoop when it's not known |
| propid | {{prop_id}} | (Required) Property ID |



***More example Requests/Responses:***
##### I. Example Response: List Buildings By Property
```js
{
    "status": 200,
    "message": "Success",
    "data": [
        {
            "PropId": "{{prop_id}}",
            "PID": "{{pid}}",
            "Config": {
                "Email": {
                    "Default": "{{email}}"
                }
            },
            "OperatingHours": {
                "0": [
                    {
                        "End": "2359",
                        "Start": "0000"
                    }
                ],
                "1": [
                    {
                        "End": "2359",
                        "Start": "0000"
                    }
                ],
                "2": [
                    {
                        "End": "2359",
                        "Start": "0000"
                    }
                ],
                "3": [
                    {
                        "End": "2359",
                        "Start": "0000"
                    }
                ],
                "4": [
                    {
                        "End": "2359",
                        "Start": "0000"
                    }
                ],
                "5": [
                    {
                        "End": "2359",
                        "Start": "0000"
                    }
                ],
                "6": [
                    {
                        "End": "2359",
                        "Start": "0000"
                    }
                ]
            },
            "Coordinates": {},
            "Name": "Demo Project (January)",
            "Address": {
                "Street": "16th Cross",
                "City": "Bangalore",
                "State": "Karnataka",
                "Country": "India",
                "PostalCode": "560078",
                "Coordinates": {
                    "Latitude": 12.44,
                    "Longitude": 32.44
                }
            },
            "LevelsCount": 2,
            "Status": "draft",
            "TimeZone": "Asia/Kolkata",
            "IsBeaconEnabled": true,
            "CreatedBy": "sc_kiran",
            "CreatedOn": 1609918117,
            "UpdatedBy": "sc_kiran",
            "UpdatedOn": 1609918117
        }
    ]
}
```


***Status Code:*** 200


***Error codes:***

##### 400
##### Possible reasons:

###### 1. Missing op/org/pid/propid



<br>