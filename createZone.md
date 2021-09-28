---
layout: default
title: Create Zone
parent: Zone
grand_parent: Grids
has_children: true
nav_order: 1
---


### 1. Create Zone


Op name: 

> scgrids.createZone

This creates a Zone object for a given Level for a Building


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
| op | scgrids.createZone | (Required) Operation Name |
| org | {{org}} | (Required) Organisation ID |
| pid | {{pid}} | (Required) Project ID |
| propid | {{prop_id}} | (Required) Property ID |



***Body:***

```js        
{
    "Zone": [
        {
            "Name": "Zone 5",
            "Area": 3000,
            "FloorType": "hardwood",
            "Tags": {
                "Category": "test"
            },
            "LID": "{{lid}}",
            "ZoneCategoryID": "AUDITORIUMS/THEATERS",
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
            },
            "IsBuildingOperatingHours": true,
            "Status": "active",
            "BeaconID": "test"
        }
    ]
}
```



***More example Requests/Responses:***


##### I. Example Request: Create Zone

***Body:***

```js        
{
    "Zone": [
        {
            "Name": "Zone 5",
            "Area": 3000,
            "FloorType": "hardwood",
            "Tags": {
                "Category": "test"
            },
            "LID": "{{lid}}",
            "ZoneCategoryID": "{{zone_category_id}}",
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
            },
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
            "Status": "active",
            "BeaconID": "test"
        },
        {
            "Name": "Zone 2",
            "Area": 3000,
            "FloorType": "hardwood",
            "Tags": {
                "Category": "test"
            },
            "LID": "{{lid}}",
            "ZoneCategoryID": "{{zone_category_id}}",
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
            },
            "Status": "active",
            "BeaconID": "test",
            "IsBuildingOperatingHours": true
        }
    ]
}
```

##### I. Example Response: Create Zone
```js
{
    "status": 201,
    "message": "Success",
    "data": [
        {
            "OrgId": "{{org}}",
            "PID": "{{pid}}",
            "LID": "{{lid}}",
            "InsID": "{{insid}}}",
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
            "IsBuildingOperatingHours": false,
            "CreatedOn": 1611811493
        },
        {
            "OrgId": "{{org}}",
            "PID": "{{pid}}",
            "LID": "{{lid}}",
            "InsID": "{{insid}}}",
            "BeaconID": "test",
            "ZoneCategoryID": "LABS",
            "Name": "Zone 2",
            "Area": 3000,
            "FloorType": "hardwood",
            "Tags": {
                "Category": "test"
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
            },
            "Status": "active",
            "IsBuildingOperatingHours": true,
            "CreatedOn": 1611811493
        }
    ]
}
```


***Status Code:*** 200


***Error codes:***

##### 400

##### Possible reasons:

###### 1. Missing op/org/pid/propid

###### 2. Invalid characters/improper input body

###### 3. Missing access_token in the header

###### 4. If the given building is not found


<br>