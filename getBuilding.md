---
layout: default
title: Get Building
parent: Building
grand_parent: Grids
has_children: true
nav_order: 1
---

### 4. Get Building


Op name: 

> scgrids.readBuilding

This gets a given Building's details


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
| op | scgrids.readBuilding | (Required) Operation Name |
| org | {{org}} | (Required) Organisation ID |
| pid | {{pid}} | (Required) Project ID |



***More example Requests/Responses:***
##### I. Example Response: scgrids.readBuilding
```js
{
    "status": 200,
    "message": "Success",
    "data": {
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
        "Name": "New Name",
        "Address": {
            "Street": "test",
            "City": "test",
            "State": "test",
            "Country": "test",
            "PostalCode": "test",
            "Coordinates": {
                "Latitude": 12.44,
                "Longitude": 32.44
            }
        },
        "LevelsCount": 10,
        "Status": "Active",
        "TimeZone": "Asia/Kolkata",
        "IsBeaconEnabled": true,
        "CreatedBy": "sc_kiran",
        "CreatedOn": 1609158882,
        "UpdatedBy": "sc_kiran",
        "UpdatedOn": 1609158882
    }
}
```


***Status Code:*** 200

***Error codes:***

##### 400

##### Possible reasons:

###### 1. Missing op/org/pid

###### 2. If the given Building ID is not found

<br>