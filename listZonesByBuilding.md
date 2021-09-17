---
layout: default
title: List Zones by Building
parent: Grids Building
grand_parent: Grids
has_children: true
nav_order: 1
---


### 6. List Zones By Building


Op name: 

> scgrids.listZonesByBuilding

This lists all the Zones details for a given Building


***Endpoint:***

```bash
Method: POST
Type: RAW
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
| op | scgrids.listZonesByBuilding | (Required) Operation Name |
| org | {{org}} | (Required) Organisation ID |
| pid | {{pid}} | (Required) Project ID |



***Body:***

```js        
{
    "ESK": "{{insid}}"
}
```



***More example Requests/Responses:***


##### I. Example Request: List Zones By Building


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Authorization | {{access_token}} | (Required) The Login Access Token |
| x-sc-identity | external | (Required) |



***Query:***

| Key | Value | Description |
| --- | ------|-------------|
| op | scgrids.listZonesByBuilding | (Required) Operation Name |
| org | {{org}} | (Required) Organisation ID |
| pid | {{pid}} | (Required) The Project ID |



##### I. Example Response: List Zones By Building
```js
{
    "status": 200,
    "message": "Success",
    "data": [
        {
            "InsID": "{{insid}}",
            "LID": "{{lid}}",
            "BeaconID": "test",
            "ZoneCategoryID": "LABS",
            "Name": "Zone 5",
            "Area": 3000,
            "FloorType": "hardwood",
            "Tags": {
                "Category": "test"
            },
            "Units": {
                "General": [
                    "windows",
                    "stairs",
                    "railings"
                ]
            },
            "Status": "active",
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
            "PID": "{{pid}}"
        }
    ]
}
```


***Status Code:*** 200

<br>