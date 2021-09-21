---
layout: default
title: Batch Get Buildings
parent: Building
grand_parent: Grids
has_children: true
nav_order: 1
---

### 1. Batch Get Buildings


## Op name: 

> scgrids.readBuildings

## This gets a Building's details given a list of PIDs


***Endpoint:***

```bash
Method: POST
Type: application/json
URL: /v1/actions
```


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Authorization | {{access_tokren}} | (Required) The Acccess Token or HMAC Signature |
| x-sc-identity | external | (Required) |



***Query params:***

| Key | Value | Description |
| --- | ------|-------------|
| op | scgrids.readBuildings | (Required) Operation Name |
| org | {{org}} | (Required) Organization Name |
| pid | scnoop | (Required) Project Name |



***Body:***

```js        
{
    "PIDs": [
        "{{pid}}"
    ]
}
```



***More example Requests/Responses:***


##### I. Example Request: Batch Get Buildings

***Body:***

```js        
{
    "PIDs": [
        "{{pid}}"
    ]
}
```

##### I. Example Response: Batch Get Buildings
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
                        "End": "2222",
                        "Start": "0001"
                    }
                ],
                "1": [
                    {
                        "End": "2333",
                        "Start": "0002"
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
            "Name": "Test Building",
            "IsPropertyAddress": true,
            "LevelsCount": 1,
            "Status": "Active",
            "IsBeaconEnabled": true,
            "CreatedBy": "sc_kiran",
            "CreatedOn": 1611908128,
            "UpdatedBy": "sc_kiran",
            "UpdatedOn": 1611908128
        }
    ]
}
```

***Status Code:*** 200

<br>