---
layout: default
title: Update Zone
parent: Zone
grand_parent: Grids
has_children: true
nav_order: 1
---


### 14. Update Zone


Op name: 

> scgrids.updateZone

This updates the Zone's details like Name, Area ro Status


***Endpoint:***

```bash
Method: POST
Type: application/json
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
| op | scgrids.updateZone | (Required) Operation Name |
| org | {{org}} | (Required) Operation Name |
| pid | {{pid}} | (Required) Project ID |



***Body:***

```js        
{
    "InsID": "{{insid}}",
    "Name": "New test name",
    "Area": 6000,
    "FloorType": "Test floor 2",
    "Status": "PENDING",
    "IsBuildingOperatingHours": true,
    "OperatingHours": {
        "0": [
            {
                "Start": "1111",
                "End": "2222"
            }
        ],
        "1": [
            {
                "Start": "0000",
                "End": "2359"
            }
        ],
        "2": [
            {
                "Start": "0000",
                "End": "2359"
            }
        ],
        "3": [
            {
                "Start": "0000",
                "End": "2359"
            }
        ],
        "4": [
            {
                "Start": "0000",
                "End": "2359"
            }
        ],
        "5": [
            {
                "Start": "0000",
                "End": "2359"
            }
        ],
        "6": [
            {
                "Start": "0000",
                "End": "2359"
            }
        ]
    },
    "Units": {
        "General": [
            {
                "Key": "windows",
                "Count": 1
            },
            {
                "Key": "stairs",
                "Count": 2
            },
            {
                "Key": "railings",
                "Count": 2
            }
        ]
    }
}
```



***More example Requests/Responses:***


##### I. Example Request: Update Zone

***Body:***

```js        
{
    "InsID": "{{insid}}",
    "Name": "testname",
    "Area": 5000,
    "FloorType": "Test",
    "Status": "Pending",
    "IsBuildingOperatingHours": true,
    "OperatingHours": {
        "0": [
            {
                "Start": "0000",
                "End": "2359"
            }
        ],
        "1": [
            {
                "Start": "0000",
                "End": "2359"
            }
        ],
        "2": [
            {
                "Start": "0000",
                "End": "2359"
            }
        ],
        "3": [
            {
                "Start": "0000",
                "End": "2359"
            }
        ],
        "4": [
            {
                "Start": "0000",
                "End": "2359"
            }
        ],
        "5": [
            {
                "Start": "0000",
                "End": "2359"
            }
        ],
        "6": [
            {
                "Start": "0000",
                "End": "2359"
            }
        ]
    },
    "Units": {
        "General": [
            "windows",
            "stairs",
            "railings",
            "new unit"
        ]
    }
}
```

##### I. Example Response: Update Zone
```js
{
    "status": 200,
    "message": "Success",
    "data": {
        "PID": "{{pid}}",
        "InsID": "{{insid}}",
        "LID": "{{lid}}",
        "BeaconID": "test",
        "ZoneCategoryID": "LABS",
        "Name": "testname",
        "Area": 5000,
        "FloorType": "Test",
        "Tags": {
            "Category": "test"
        },
        "Units": {
            "General": [
                "windows",
                "stairs",
                "railings",
                "new unit"
            ]
        },
        "Status": "Pending",
        "IsBuildingOperatingHours": true,
        "CreatedOn": 1609928625
    }
}
```


***Status Code:*** 200

***Error codes:***

##### 400
##### Possible reasons:

###### 1. Missing op/org/pid

###### 3. Missing InsId in the body

###### 4. Missing access_token in the header

<br>