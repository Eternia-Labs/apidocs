---
layout: default
title: Grids
has_children: false
has_toc: true
nav_order: 2
---

# Smartclean / SCGrids v1.0

## Grids module includes the APIs for smartclean Property, Building, Level, Zone (installations / locations). The hierarchy is as follows 
> Property  
>> Building 
>>> Level 
>>>> Zone
        

## Indices

* [Building](#building)

  * [Batch Get Buildings](#1-batch-get-buildings)
  * [Building Zone Map](#2-building-zone-map)
  * [Create Building](#3-create-building)
  * [Get Building](#4-get-building)
  * [List Levels By Building](#5-list-levels-by-building)
  * [List Zones By Building](#6-list-zones-by-building)
  * [Update Building](#7-update-building)

* [Level (Floor)](#level-(floor))

  * [Annotations](#1-annotations)
  * [Create Level](#2-create-level)
  * [Delete Level](#3-delete-level)
  * [Get FloorPlan](#4-get-floorplan)
  * [Get Level](#5-get-level)
  * [List Zones By Level](#6-list-zones-by-level)
  * [Update Level](#7-update-level)
  * [Update Level FloorPlan](#8-update-level-floorplan)

* [Property](#property)

  * [Create Property](#1-create-property)
  * [Create PropertyType](#2-create-propertytype)
  * [Get Property](#3-get-property)
  * [Get Property Collaboration](#4-get-property-collaboration)
  * [List Buildings By Property](#5-list-buildings-by-property)
  * [List Owner Org Properties](#6-list-owner-org-properties)
  * [List Properties](#7-list-properties)
  * [List PropertyTypes](#8-list-propertytypes)
  * [Update Property](#9-update-property)

* [Property V2](#property-v2)

  * [Create Property V2](#1-create-property-v2)
  * [Get Subscription Plan](#2-get-subscription-plan)
  * [Get Subscription Plan for a Property](#3-get-subscription-plan-for-a-property)

* [Zone](#zone)

  * [Create Zone](#1-create-zone)
  * [Create Zone Asset](#2-create-zone-asset)
  * [Create Zone Asset For Building](#3-create-zone-asset-for-building)
  * [Create Zone Category](#4-create-zone-category)
  * [Create Zone Category For Building](#5-create-zone-category-for-building)
  * [Delete Zone](#6-delete-zone)
  * [Get Zone](#7-get-zone)
  * [List Zone Asset By Zone Category](#8-list-zone-asset-by-zone-category)
  * [List Zone Categories](#9-list-zone-categories)
  * [List Zone Categories By Building](#10-list-zone-categories-by-building)
  * [List Zone Units By Building](#11-list-zone-units-by-building)
  * [List Zones By IDs](#12-list-zones-by-ids)
  * [ListZoneByZoneCategory](#13-listzonebyzonecategory)
  * [Update Zone](#14-update-zone)

* [Ungrouped](#ungrouped)

  * [Get Media Attachment](#1-get-media-attachment)
  * [Get Thumbnails](#2-get-thumbnails)
  * [Upload Media Attachment](#3-upload-media-attachment)


--------


## Building
## This directory lists all the APIs regarding Building



### 1. Batch Get Buildings


## Op name: 

> scgrids.readBuildings

## This gets a Building's details given a list of PIDs


***Endpoint:***

```bash
Method: POST
Type: RAW
URL: /v1/actions
```


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Authorization | {{access_tokren}} | (Required) Login Access Token |
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



***Query:***

| Key | Value | Description |
| --- | ------|-------------|
| op | scgrids.readBuildings |  |
| org | {{org}} |  |
| pid | scnoop |  |



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
                    "Default": "corporate@isikhlassuci.com,abhishek@smartclean.sg"
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
            "Name": "redis test 2",
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



### 2. Building Zone Map


Op Name: 

> scgrids.buildingZoneMap

This lists a given Building's zone name and zone id map


***Endpoint:***

```bash
Method: POST
Type: RAW
URL: /v1/actions
```



***Query params:***

| Key | Value | Description |
| --- | ------|-------------|
| op | scgrids.buildingZoneMap | (Required) Operation Name |
| org | {{org}} | (Required) Organisation Name |
| pid | {{pid}} | (Required) Project ID |



***Body:***

```js        
{
    "ESK": ""
}
```



### 3. Create Building


Op name: 

> scgrids.createBuilding

This creates a Building object for a given Property


***Endpoint:***

```bash
Method: POST
Type: RAW
URL: /v1/actions
```


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Authorization | {{access_token}} | (Required) The Login Acccess Token |
| x-sc-identity | external | (Required) |



***Query params:***

| Key | Value | Description |
| --- | ------|-------------|
| op | scgrids.createBuilding | (Required) Operation Name |
| org | {{org}} | (Required) Organisation ID |
| pid | scnoop | (Required) Project ID is scnoop when it's not known |
| propid | {{prop_id}} | (Required) Property ID |



***Body:***

```js        
{
    "Name": "Powerful Industrial Main Office",
    "OperatingHours": {
        "0": [
            {
                "Start": "0001",
                "End": "2359"
            }
        ],
        "1": [
            {
                "Start": "0001",
                "End": "2359"
            }
        ],
        "2": [
            {
                "Start": "0001",
                "End": "2359"
            }
        ],
        "3": [
            {
                "Start": "0001",
                "End": "2359"
            }
        ],
        "4": [
            {
                "Start": "0001",
                "End": "2359"
            }
        ],
        "5": [
            {
                "Start": "0001",
                "End": "2359"
            }
        ],
        "6": [
            {
                "Start": "0001",
                "End": "2359"
            }
        ]
    },
    "Email": {
        "Default": "abhishek@smartclean.sg"
    },
    "LevelsCount": 1,
    "TimeZone": "Asia/Hong_Kong",
    "PropID": "a19c68083e6d459da38ad32e86bf5402",
    "IsBeaconEnabled": false,
    "IsPropertyAddress": true,
    "Country": "HKG",
    "Area": 1200,
    "CountryLocale": "HKG",
    "PID": "66be2ae3e53845209f60f1cff418a9c5"
}
```



***More example Requests/Responses:***


##### I. Example Request: Create Building


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Authorization | {{access_token}} | (Required) The Login Acccess Token |
| x-sc-identity | external | (Required) |



***Query:***

| Key | Value | Description |
| --- | ------|-------------|
| op | scgrids.createBuilding | (Required) Operation Name |
| org | {{org}} | (Required) Organisation ID |
| pid | scnoop | (Required) Project ID is scnoop when it's not known |
| propid | {{prop_id}} | (Required) Property ID |



***Body:***

```js        
{
    "Name": "Demo Project (January)",
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
    "Email": {
        "Default": "corporate@isikhlassuci.com,abhishek@smartclean.sg"
    },
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
    "TimeZone": "Asia/Kolkata",
    "IsBeaconEnabled": true,
    "IsPropertyAddress": false,
    "Country": "IND",
    "CountryLocale": "BLR"
}
```



##### I. Example Response: Create Building
```js
{
    "status": 200,
    "message": "Successfully created the project!",
    "data": {
        "PropId": "{{prop_id}}",
        "PID": "{{pid}}",
        "Config": {
            "Email": {
                "Default": "corporate@isikhlassuci.com,abhishek@smartclean.sg"
            }
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
        "Status": "draft",
        "TimeZone": "Asia/Kolkata",
        "IsBeaconEnabled": true
    }
}
```


***Status Code:*** 200

<br>



### 4. Get Building


Op name: 

> scgrids.readBuilding

This gets a given Building's details


***Endpoint:***

```bash
Method: POST
Type: 
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
| op | scgrids.readBuilding | (Required) Operation Name |
| org | {{org}} | (Required) Organisation ID |
| pid | {{pid}} | (Required) Project ID |



***More example Requests/Responses:***


##### I. Example Request: scgrids.readBuilding


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Authorization | {{access_token}} | (Required) The Login Access Token |
| x-sc-identity | external | (Required) |



***Query:***

| Key | Value | Description |
| --- | ------|-------------|
| op | scgrids.readBuilding | (Required) Operation Name |
| org | {{org}} | (Required) Organisation ID |
| pid | {{pid}} | (Required) The Project ID |



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
                "Default": "corporate@isikhlassuci.com,abhishek@smartclean.sg"
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

<br>



### 5. List Levels By Building


OP name: 

> scgrids.listLevelsByBuilding

This lists the levels for a given Building


***Endpoint:***

```bash
Method: POST
Type: FORMDATA
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
| op | scgrids.listLevelsByBuilding | (Required) Operation Name |
| org | {{org}} | (Required) Organisation ID |
| pid | {{pid}} | (Required) Project ID |



***More example Requests/Responses:***


##### I. Example Request: List Levels By Building


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Authorization | {{access_token}} | (Required) The Login Access Token |
| x-sc-identity | external | (R)equired |



***Query:***

| Key | Value | Description |
| --- | ------|-------------|
| op | scgrids.listLevelsByBuilding | (Required) Operation Name |
| org | {{org}} | (Required) Organisation ID |
| pid | {{pid}} | (Required) The Project ID |



##### I. Example Response: List Levels By Building
```js
{
    "status": 200,
    "message": "Success",
    "data": [
        {
            "Name": "Level 3",
            "Level": "L3",
            "LID": "{{lid}}"
        },
        {
            "Name": "Level 4",
            "Level": "L4",
            "LID": "{{lid}}"
        },
        {
            "Name": "Level 2",
            "Level": "L2",
            "LID": "{{lid}}"
        },
        {
            "Name": "Level 8",
            "Level": "L8",
            "LID": "{{lid}}"
        },
        {
            "Name": "New Name",
            "Level": "L1",
            "Area": 5000,
            "LID": "{{lid}}"
        },
        {
            "Name": "Level 9",
            "Level": "L9",
            "LID": "{{lid}}"
        },
        {
            "Name": "Level 6",
            "Level": "L6",
            "LID": "{{lid}}"
        },
        {
            "Name": "Level 7",
            "Level": "L7",
            "LID": "{{lid}}"
        },
        {
            "Name": "Level 5",
            "Level": "L5",
            "LID": "{{lid}}"
        },
        {
            "Name": "Level 0",
            "Level": "L0",
            "LID": "{{lid}}"
        }
    ]
}
```


***Status Code:*** 200

<br>



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
        },
        {
            "InsID": "{{insid}}",
            "LID": "{{lid}}",
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
                    "windows",
                    "stairs",
                    "railings"
                ]
            },
            "Status": "active",
            "OperatingHours": {
                "0": null,
                "1": null,
                "2": null,
                "3": null,
                "4": null,
                "5": null,
                "6": null
            },
            "PID": "{{pid}}"
        }
    ]
}
```


***Status Code:*** 200

<br>



##### II. Example Request: List Zones By Building


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
| pid | {{pid}} | (Required) Project ID |



***Body:***

```js        
{
    "ESK": "{{insid}}"
}
```



##### II. Example Response: List Zones By Building
```js
{
    "status": 200,
    "message": "Success",
    "data": [
        {
            "InsID": "{{insid}}",
            "LID": "{{lid}}",
            "BeaconID": "test",
            "ZoneCategoryID": "{{zone_category_id}}",
            "Name": "testname",
            "Area": 5000,
            "FloorType": "Test",
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
            "Status": "Pending",
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
            "IsBuildingOperatingHours": true,
            "PID": "{{pid}}"
        }
    ],
    "LEK": {
        "ID": "SCProjects#{{pid}}",
        "ATTR": "attr#installations#info#{{pid}}#{{insid}}"
    }
}
```


***Status Code:*** 200

<br>



### 7. Update Building


Op name: 

 > scgrids.updateBuilding

This updates a given building's Name or Status


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
| op | scgrids.updateBuilding | (Required) Operation Name |
| org | {{org}} | (Required) Organisation ID |
| pid | {{pid}} | (Required) Project ID |



***Body:***

```js        
{
    "Status": "",
    "Name": "",
    "OperatingHours": {
        "0": [
            {
                "Start": "0000",
                "End": "2322"
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
    }
}
```



***More example Requests/Responses:***


##### I. Example Request: Update Building


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Authorization | {{access_token}} | (Required) The Login Access Token |
| x-sc-identity | external | (Required) |



***Query:***

| Key | Value | Description |
| --- | ------|-------------|
| op | scgrids.updateBuilding | (Required) Operation Name |
| org | {{org}} | (Required) Organisation ID |
| pid | {{pid}} | (Required) The Project ID |



***Body:***

```js        
{
    "Status": "Pending",
    "Name": "New Name",
    "OperatingHours": {
        "0": [
            {
                "Start": "0000",
                "End": "2322"
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
    }
}
```



##### I. Example Response: Update Building
```js
{
    "status": 200,
    "message": "Success",
    "data": {
        "PropId": "{{prop_id}}",
        "PID": "{{pid}}",
        "Config": {
            "Email": {
                "Default": "corporate@isikhlassuci.com,abhishek@smartclean.sg"
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

<br>



## Level (Floor)



### 1. Annotations



***Endpoint:***

```bash
Method: 
Type: 
URL: 
```



### 2. Create Level


Op name: 

> scgrids.createLevel

This creates a Level object for a given Building


***Endpoint:***

```bash
Method: POST
Type: RAW
URL: /v1/actions
```


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| x-sc-identity | external | (Required) |
| Authorization | {{access_token}} | (Required) The Login Access Token |
| x-sc-identity | external | (Requirec) |



***Query params:***

| Key | Value | Description |
| --- | ------|-------------|
| op | scgrids.createLevel | (Required) Operation Name |
| org | {{org}} | (Required) Organisation ID |
| pid | {{pid}} | (Required) Project ID |
| propid | {{propid}} | (Optional) Property ID |



***Body:***

```js        
{
    "Name": "JWT Level Test 3",
    "FloorPlan": "https://smartclean-images-staging.s3-ap-southeast-1.amazonaws.com/plan.jpg",
    "Level": "L29"
}
```



***More example Requests/Responses:***


##### I. Example Request: Create Level


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Authorization | {{access_token}} | (Required) The Login Access Token |
| x-sc-identity | external | (Required) |



***Query:***

| Key | Value | Description |
| --- | ------|-------------|
| op | scgrids.createLevel | (Required) Operation Name |
| org | {{org}} | (Required) Organisation ID |
| pid | {{pid}} | (Required) The Project ID |



***Body:***

```js        
{
    "Name": "Level 25",
    "FloorPlan": "https://smartclean-images-staging.s3-ap-southeast-1.amazonaws.com/plan.jpg",
    "Level": "L25"
}
```



##### I. Example Response: Create Level
```js
{
    "status": 201,
    "message": "Successfully created the level!",
    "data": {
        "Name": "Level 25",
        "FloorPlan": "https://smartclean-images-staging.s3-ap-southeast-1.amazonaws.com/plan.jpg",
        "LID": "7305dd25a4784c558032bc3fef596417"
    }
}
```


***Status Code:*** 201

<br>



### 3. Delete Level


Op Name:

> scgrids.deleteLevel

Deletes a given Level


***Endpoint:***

```bash
Method: POST
Type: RAW
URL: /v1/actions
```


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Authorization | {{access_token}} | (Required) Login Access Token |
| x-sc-identity | external | (Required) |



***Query params:***

| Key | Value | Description |
| --- | ------|-------------|
| op | scgrids.deleteLevel | (Required) Operation Name |
| org | {{org}} | (Required) Organisation Name |
| pid | {{pid}} | (Required) Project ID |
| propid | {{prop_id}} | (Optional) Property ID |



***Body:***

```js        
{
    "lid": "{{lid}}"
}
```



### 4. Get FloorPlan


Op name: 

> scgrids.readFloorPlan

This reads the FloorPlan for a Level from DB and returns the Base64 version


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
| op | scgrids.readFloorPlan | (Required) Operation Name |
| org | {{org}} | (Required) Organisation ID |
| pid | {{pid}} | (Required) Project ID |
| propid | {{prop_id}} | (Required) Property ID |



***Body:***

```js        
{
    "LID": "{{lid}}"
}
```



***More example Requests/Responses:***


##### I. Example Request: Get FloorPlan


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Authorization | {{access_token}} |  |



***Query:***

| Key | Value | Description |
| --- | ------|-------------|
| op | scgrids.readFloorPlan | (Required) Operation Name |
| org | {{org}} | (Required) Organisation ID |
| pid | {{pid}} | (Required) Project ID |
| propid | {{prop_id}} | (Required) Property ID |



***Body:***

```js        
{
    "LID": "{{lid}}"
}
```



##### I. Example Response: Get FloorPlan
```js
{
    "status": 200,
    "message": "Success",
    "data": "/9j/4AAQSkZJRgABAQEAYABgAAD//gA7Q1JFQVRPUjogZ2QtanBlZyB2MS4wICh1c2luZyBJSkcgSlBFRyB2NjIpLCBxdWFsaXR5ID0gODUK/9sAQwAFAwQEBAMFBAQEBQUFBgcMCAcHBwcPCwsJDBEPEhIRDxERExYcFxMUGhURERghGBodHR8fHxMXIiQiHiQcHh8e/9sAQwEFBQUHBgcOCAgOHhQRFB4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4e/8AAEQgCyAM0AwEiAAIRAQMRAf/EAB0AAQEBAAIDAQEAAAAAAAAAAAAEBQgJAQYHAwL/xABnEAABAgMCCQIMDwsJBwMFAAMAAQIDBAUGEQcSFENTgaLB4SExCAkTNDhBUWN1srPxFRgiMjU2N2FxdJSV0dLTFlRVVldzhJGStMIXIzNCUmKCobEkRGRyk6PUJYOkJmXD4/AohcT/xAAWAQEBAQAAAAAAAAAAAAAAAAAAAQL/xAAcEQEAAwEBAQEBAAAAAAAAAAAAARFBITFRYfD/2gAMAwEAAhEDEQA/AOWQAAspmc1by0ipmc1by0AYxsmMALKZnNW8jLKZnNW8C0AAYwAAspmc1by0ipmc1by0AYxsmMALKZnNW8jLKZnNW8C0AAYwAAspmc1by0ipmc1by0AYxsmMALKZnNW8jLKZnNW8C0AAYwAAspmc1by0ipmc1by0AYxsmMALKZnNW8jLKZnNW8C0AAYwAAspmc1by0ipmc1by0AYxsmMALKZnNW8jLKZnNW8C0AAYwAAspmc1by0ipmc1by0AYxsmMALKZnNW8jLKZnNW8C0AAYwAAspmc1by0ipmc1by0AYxsmMALKZnNW8jLKZnNW8C0AAYwAAspmc1by0ipmc1by0AYxsmMALKZnNW8jLKZnNW8C0AAYwAAspmc1by0ipmc1by0AYxsmMALKZnNW8jLKZnNW8C0AAYwAAspmc1by0ipmc1by0AYxsmMALKZnNW8jLKZnNW8C0AAYwAAAACzIV0uzxGQrpdniWgCHrPvmPquu855y5dHtcBUs3r3EYFmXLo9rgMhXS7PEjNkCLIV0uzxPHWffMfVdd5y4iqWb17gGXLo9rgMuXR7XAjAFmQrpdniMhXS7PEtAEPWffMfVdd5zzly6Pa4CpZvXuIwLMuXR7XAZCul2eJGbIEWQrpdnieOs++Y+q67zlxFUs3r3AMuXR7XAZcuj2uBGALMhXS7PEZCul2eJaAIes++Y+q67znnLl0e1wFSzevcRgWZcuj2uAyFdLs8SM2QIshXS7PE8dZ98x9V13nLiKpZvXuAZcuj2uAy5dHtcCMAWZCul2eIyFdLs8S0AQ9Z98x9V13nPOXLo9rgKlm9e4jAsy5dHtcBkK6XZ4kZsgRZCul2eJ46z75j6rrvOXEVSzevcAy5dHtcBly6Pa4EYAsyFdLs8RkK6XZ4loAh6z75j6rrvOfE6z0RrJm0E/ScH2D20FuG016w5yckfUS7XovK1r8V2N+pL+1enKfVsI0Gej2Oq8Cl42XxKfMMlcVbl6qsNUZd799x8F6FSfnPStw4NhZemx7TycaYZFl5xVbDylYyr/ADtyov8ARK274ETtAfT8DeGSg4SpeoQpGRnaXV6ZE6nUKZPJiR4C3ql93bS9FTtKipcqJyH0LIe+bPE4t2StvaqpWgwp2WtVZ6ylKrFNs7GmJmbokNyRIsRYSKmNFxlV1yOT30VPeMLA1Z2Zs30OUbDq2t1up2plaRPQ5CFHmViS8tD6q+Gi4ipeuKqOicq3cq8nJeBzByHvmzxPHWffMfVdd5zh/VMHVNpPQzy2GiTtZXG27yOBV3Vhag93VIsR7b4CtVcVUTGxLudVTlvS9p7My0dVr/RM4HqpPPjSsSq2LyyalGvc2H1R8GYcvqObnXkvTtJ3AOTeXLo9rgMuXR7XA4tZbNr0ReGuAk7MLBg2UxoTEjOxYbsmg8rUvuRb+4fOZSxUvOdB03CVN1yvzFopFzoshGdUImJKNSc6mrGMvuRFvc5V57157kuA515D3zZ4nodNt9IzuG6p4LmSM0ydp9MbUXziq3qT2qsP1KJfff8AzifqU+J2njTuFDCrgosBaurTzKDP2RgVqegy8dYPohNOhOc5HK26/wDo0Xk5URXXXX3leBizkrZLo2rVUCn1GdnZKVsy3J0nJh0eJLw3OlnJBx3Kqq1t/qb+Ztye+B9lw1YRpLBJY1tpp+nTNUgxJqHLdRl3NY5FcjlReXtch6jQ8O9o6lWpGRi4E7dyUKamIcF01GllSHBa5yIr3Li8jUvvX3kMjpgt/wDIZAxbr/RiXuv+B5r2FpWHuBaSnx7V2osfN0Nqqs1Ak5V7Yz24q3I1VYiIt93bA9usRhUkrU4QbW2Ql6TMy8ezUWHDjR4kRqsjY+NcrUTlT1vbPeMh75s8TiRZ+vz9l8IXRF2hpbEfPSECFGgXpejXo2Lc5U7aN51T3iWZwdU6W6GVmGqDaytpbtJNlXWs+iL1xoroiXwFbfi3cuJdz43vepA5g5D3zZ4njrPvmPquu85xbq1WqWGLCjg5sNa2dm6bQqjZKDX56SlYywFn5l7HKrVVLlxUxb0ROZEd8KeKVCj4OcM1s8F9nqlPzVlo1lY1UgykeO6K6mRsS65rlVVRF/iZz3XqHKbLl0e1wGXLo9rgcWegzsBLz9lKFhOqldrU9VoazcvLQIs0rpeFBx3sVuKqXqt+M6++71ScnIcmgLMhXS7PEZCul2eJaAIes++Y+q67znnLl0e1wFSzevcRgWZcuj2uAyFdLs8SM2QIshXS7PE8dZ98x9V13nLiKpZvXuAZcuj2uAy5dHtcCMAWZCul2eIyFdLs8S0AQ9Z98x9V13nPOXLo9rgKlm9e4jAsy5dHtcBkK6XZ4kZsgRZCul2eJ46z75j6rrvOXEVSzevcAy5dHtcBly6Pa4EYAsyFdLs8RkK6XZ4loAh6z75j6rrvOecuXR7XAVLN69xGBZly6Pa4DIV0uzxIzZAiyFdLs8Tx1n3zH1XXecuIqlm9e4Bly6Pa4DLl0e1wIwBZkK6XZ4jIV0uzxLQBD1n3zH1XXec85cuj2uAqWb17iMCzLl0e1wGQrpdniRmyBFkK6XZ4njrPvmPquu85cRVLN69wDLl0e1wGXLo9rgRgCzIV0uzxGQrpdniWgCLIV0uzxBaAAMYAWVLN69xGWUzOat5aBjGyDGA2SKpZvXuIyymZzVvAjBsgADGAFlSzevcRllMzmreWgYxsgxgNkiqWb17iMspmc1bwIwbIAAxgBZUs3r3EZZTM5q3loGMbIMYDZIqlm9e4jLKZnNW8CMGyAAMYAWVLN69xGWUzOat5aBjGyDGA2SKpZvXuIyymZzVvAjB6fQMI753CBVKTNQ5JtHRsyylRob1WPFiybmtmkeirddjOXEuuvSE9V7R5hYYKB6BpWJqjWjk5aPJw56SSPIpjzsB8SHDxoTWuVVVHRod7Vudc9FRFQD6QD5euEeQSNAknWftA2qxp1JP0NWXhpHY50F8Zr1XqmJ1NWQ3rjI5Uvaqc6XH8twnUeIsR8Ck1yNAcyO6RjslUVlRWAirEbA9Ve5yI1yojkbjo1VbjAfRalm9e4+KWv6HmxVbtDOV+l1Cv2Wn51yunHUWd6gyYVb1VXNVFS9VW9brkVeW69VPp9g7T0q1EOemKLEiTUlAiMhtnEb/Mx3K3GXqbv6yNvRFW65HXt52qiQ4RKla2mTMkln6jRWPn4zJOUlJumxY0SLGXGc5yvZGYjWNY1z19StyMXnVUQD1awuBawtjqJWKbRpKa6pWZaJKz09HmFiTMWG9FRUxl5E57+RE5eVbz3OwtgLP2RweQLByMGLOUSFCjQVhTrkirEZFc5z2v5ERUXHcl13MYTbZ2hSs5a6BTPudbX0oLoSMek2sRXJC6uj8bFxerLdiYt+L6rGv5D8MLVtZuylJVlEkoM/V1hLMrCiqvU4EsxzUiRYl3L28Vqc7nKnaRyoHrst0MVgoc1BgPq1q49nYMxlMOzsWqK6nNiY1/9HdjXf4r+6q8p7BhfwP2Zt5UqNVpidq1EqtIasOTnqRMpLxocPk9RfcqIict1yIqXr3TZtpa2nWVZT0nIEzMx6hMLLysCAsNroj0Y56+qiPYxORq87kVeZL1M6Ywp0elykecfRrQx5eWl4EeffCkUTIeqpexkZrnI5H3KiqjUdioqK65FRQMWymBKx1m6nXajTotYdMV2nOkJ50xOrFV7XIiPiYzkV3VHKl6uVV5VXkTmLIGCKysHA6/BYyLUvQF7Varljt6vyxurevxbvXe9zch9VjRGwoT4rvWsarlu7iHzWFhnoj5JJxLNWsbLrTWVbqjpBiIki7nmF/nPWt7bfX3cqNVOUD+bb4EbIWqoVnKfFmKvTJuzUCFApVVkJpIU5BYxqNRMfFVF9ai83Pypdet/wDWDnAlY+wltZm11GmK1Hq83JLKTUaenlmFj4z2vdFerkvWI5zEVVvu57kQ8T2E6zkraWJQlSZixmTSSXVWLCxHTStRWwURXo/GVVRqOxcTGVGq5FM2yeFSXqFGpExV6JUZGZm6U+qzbmsYsCTl2KqOiPdj34vJyIl7lTtc9we0YZbAUPCRZiDZ20L51km2ZbMosrFSG/HaionKqLyeqXtG8xqNYjU5kS5D0Wn4ZbKJJzEV8GeZMI+XbClHOgdUipGVyQ3I7qvU2Je11+O9qtuuVEVURfbKha6DK2BnbWeh07ASBAiPbKTcPqUV0Rqq1rF509U5ERHIqoqKioqoqAeuUDBrZqjWmtVX4LJmZj2pxUqcGZe18FzURyYrW4vIio5UVFVT1mH0MNgWzLJd1XtW+zsOYyltnHVVy05ImNjf0d2Nd/iv989ztZUrb0+oUaVkKpZ7KqlEhwGScSmRYiq5rMaPE6okdt0NqI5U9Tfytbyq5D12h2xrs/bSaps5Gl6VKOnZmTp8KZocy3KVho5Gq2ZWIkNyqrHPxUbytRbl51QN/Cfgkspb1KbHnVn6RU6SmLTqnSI+TTMq271rXIipi+9dydq69b86x2B2ytjpKsMlpiq1Sp12E+FUqtUprq05HYrbrse5EREv7Sdy++5Cmw9StPPWhq8rVKhR5+n05UlnRpOQiS6rNXI5zExoz0VrWq29eT1Trv6qn9pbadXChTLNUuSgxqU+PFlalPPVb2TDZd8ZkGFdyKqI296ryJjNTnvuCrBnYukWAsfKWWoT5p8hKuiOhrMxEfEve9XreqIic7l7R7IZFbt9S6Za9tl8gqc9PJCgxoyykNj0gsivVjHK1XpEel7XKvU2vxUS9bj8aThFpNRtDIUmXptZbCqcaPCp9QfLNSVmlgte6IrXI7GRPUOuVzUxudt6coHuwPnmFW0VSstYmaq9Ip+XzyRYMCDDVqOa10SK2GjnIrm3omNzI5L1uS9OVUgk8JlASvQKBORYjZtZhsjFmbobIOV4t6wsXqixE5b0vuVl/qcdVA+i1LN69xGfNJzDVR22bq09QJCan56DJpOSUB6wkSbgpEax0Vt0S9rW9UYqo/Edc5FROe76FRK/MTVqKhRZyWSWfClJeelmuVOqLCi4zXNeiKqY7Hw3Ity3XOb8KhSbIMYDZIqlm9e4jLKZnNW8CMGyAAMYAWVLN69xGWUzOat5aBjGyDGA2SKpZvXuIyymZzVvAjBsgADGAFlSzevcRllMzmreWgYxsgxgNkiqWb17iMspmc1bwIwbIAAxgBZUs3r3EZZTM5q3loGMbIMYDZIqlm9e4jLKZnNW8CMGyAAMYAbIMYAAWZCul2eIyFdLs8QFMzmreWkPWffMfVdd5zzly6Pa4AWmMWZcuj2uAyFdLs8QIyymZzVvGQrpdnieOs++Y+q67zgXAiy5dHtcBly6Pa4ARgsyFdLs8RkK6XZ4gKZnNW8tIes++Y+q67znnLl0e1wAtMYsy5dHtcBkK6XZ4gRllMzmreMhXS7PE8dZ98x9V13nAuBFly6Pa4DLl0e1wAjBZkK6XZ4jIV0uzxAUzOat5aQ9Z98x9V13nPOXLo9rgBaYxZly6Pa4DIV0uzxAjLKZnNW8ZCul2eJ46z75j6rrvOBcCLLl0e1wGXLo9rgBGCzIV0uzxGQrpdniApmc1by0h6z75j6rrvOecuXR7XAC0xizLl0e1wGQrpdniBGfvLMiRJeYhwYqwYjmXMiI1HYiqi3LcvIt3cP1yFdLs8Tx1n3zH1XXecD0n+SyzkhQqYyjyErLVel4r4dRZLQ2zE29IbmREjPuvckVHvR1687r+dEPVX4KrSRMGdPkZy0NRn61KU2TkJOG5YEPIGpGlnx1a9rUSI9Egpc51/IxEuVVVV+w5cuj2uAy5dHtcAPQKPYPJq5K1+pV2cqlWhTWURZiJChw0iIkCJBZDRjURGtakV7uTlVyqqry3JFBwbOlsWFKWpqsCVkmx/QeCjIa+hz4zXNc9rsW+IrWve1mPejUdy41yKn0zIV0uzxGQrpdniB6tg8sfCsnCiyFDqMeDRkjLFhU97Ue2DjMuc1r19UiK++Jy3+qc7tLcm9P0SXnLU0uuRo0RX02BMQ4MG5MTGi4iLEXt4yNY5qe89xV1n3zH1XXec85cuj2uAHqy2AgLaVZ/wBGZ30JWopVVpGJD6ks4mcx7sfFxkx8S+7H5feMW2eDGzdsKbEZXpaFMVWLKNlX1NsJGRVa1VVOROTnVy3cyYyn0PLl0e1wGQrpdniB6dbWycG0dCl6VDm8jhy7kVrHy0KZgxGo3FxIkKKite27m5lRURUXu+n1nBHNylgqjRbHV6owGx5SHDmJJeo4s89i+pVXub/NIqXMVGXJiNa1EbcfYchXS7PE8dZ98x9V13nA8w5eMsvMwZmbWP1Z78V3U0b1NjuZvJz3J215z05cGcg6irS/ROcxFss2zePitv6kjbuq83r/AHuY9xy5dHtcBly6Pa4AfPJfB3KytsYlflKk+DCjzeWx5XI4D3PjXJeqRnMWI1iqiOVqLz33KiKqH50TBnTZKnvp87UZuoyjqNFoqsiNaxVlXvc5EVWonqka7Fxu3z859HyFdLs8RkK6XZ4gfOqPgxxKFUaZEtHFe6Y6k1j0pko1iMYq+piwkh4sbGvudjpctyK1Gql5pQ8HUrT8FNRsZTI/qphsWNCiPa2HDZMOf1RuLDYiNhw0fdcxqXInJy86+5dZ98x9V13nPOXLo9rgBmy9IdN2jp9pp1YsGbgU18skmqtcyC6K6G+IqOTnd/NtbenJcnvnrLLHRn2jg1CetHUp+nyk4+ek6fHRitgxnNcl/VLsdzG478Vqrc29OdGtRPeMuXR7XAZCul2eIHrFCoLqNQFpslUInVnzUWaiTT4bXOe+LHdFiXpzcuMrfeS7uGfKYLrILa6QtNK0qDJz8jOxJ1zoLbkjxYjHo5XcvPjPx7051Q93yFdLs8Tx1n3zH1XXecD1DCHg3krZVaXm56pxoUCG1jXwEloMRzVa7GR8CK9qvl3rzK5ipeiJzKl5l/yfVmnWvs5GpFfnIlDpkzOOgSURkLEp7YsvFa1UW5HRcV70a1FVcVqqi3859Ey5dHtcBly6Pa4AetWloTa9Zz0InJuI2+JAiPjMaiOc6FFZE5uZL1Z/mevy+DmSlrWTFZlqg+HKTMy+bjyeSQHK6K+/HujKxYiMVVxsVHc/MqJ6k+i5Cul2eIyFdLs8QPmdDwRyUvQarQ21yZSRmJDIZRIclLQ3y7L0VrnPbDR0ZzcRqIr15URb0VVvPcKDRZ+HbKoV2pOZEelPlqdLxUuR0ZGK+JEiq1ORuM+Jcje1ie+bfWffMfVdd5zzly6Pa4AWmMWZcuj2uAyFdLs8QIyymZzVvGQrpdnieOs++Y+q67zgXAiy5dHtcBly6Pa4ARgsyFdLs8RkK6XZ4gKZnNW8tIes++Y+q67znnLl0e1wAtMYsy5dHtcBkK6XZ4gRllMzmreMhXS7PE8dZ98x9V13nAuBFly6Pa4DLl0e1wAjBZkK6XZ4jIV0uzxAUzOat5aQ9Z98x9V13nPOXLo9rgBaYxZly6Pa4DIV0uzxAjLKZnNW8ZCul2eJ46z75j6rrvOBcCLLl0e1wGXLo9rgBGCzIV0uzxGQrpdniApmc1by0h6z75j6rrvOecuXR7XAC0xizLl0e1wGQrpdniBGWUzOat4yFdLs8Tx1n3zH1XXecC4EWXLo9rgMuXR7XACMFmQrpdniMhXS7PECMFmQrpdniALQABFUs3r3EZZUs3r3EYA2TGNkARVLN69xaRVLN69wEYAA2QABFUs3r3EZZUs3r3EYA2TGNkARVLN69xaRVLN69wEYAA2QABFUs3r3EZZUs3r3EYA2TGNkARVLN69xaRVLN69wEYAA2QABFUs3r3EZZUs3r3EYA2TGNkARVLN69xaRVLN69wEYAA2QABFUs3r3EZZUs3r3EYA2TGNkARVLN69xaRVLN69wEYAA2QABFUs3r3EZZUs3r3EYA2TGNkARVLN69xaRVLN69wEYAA2QABFUs3r3EZZUs3r3EYA2TGLqtHfK0ubmoWKsSDAfEajuZVRqql/vAVkVSzevcfwrKy1FVJmQir/ZWXfDv147v9CWemptiNyunRGsbffEgL1ZiakRHbN3vgeQfxAiwo0NIsGIyJDdzOY5FRdaH9gbIAAiqWb17iMsqWb17jKyxIkR0KUgxZyI1cVyQUS5q9tFcqo1F96+/wB4Ck2TCZJ1iIt7lkZVLv70Zf4Lv1qWSMacWoTEpNxIEXqcKHEa6FCVnrleioqK539hP1gaJFUs3r3FpFUs3r3ARgADZAAEVSzevcRllSzevcRgDZMY2QBFUs3r3FpFUs3r3ARgADZAAEVSzevcRllSzevcRgDZMY2QBFUs3r3FpFUs3r3ARgADZAAAAAYwAAspmc1by0ipmc1by0AYxsmMALKZnNW8jLKZnNW8C0AAYwAAspmc1by0ipmc1by0AYxsmMALKZnNW8jLKZnNW8C0AAYwAAspmc1by0ipmc1by0AYxsmMALKZnNW8jLKZnNW8C0AAYwAAspmc1by0ipmc1by0AYxsmMALKZnNW8jLKZnNW8C0AAYwAAspmc1by0ipmc1by0AYxsmMALKZnNW8jLKZnNW8C0AAYwAAspmc1by0ipmc1by0AYxsmMALKZnNW8jLKZnNW8C0AAYwAAspmc1by0ipmc1by0Aes132En/i0TxVPZj1mu+wk/8AFoniqB7MAAM+YkU6s+ak4nUJl12M669kS7tPb2/h507t3IftKTHVkcyI3qUZl3VId991/MqL22r2l/0VFRKiKowIj2tmJbrmDerEvuSInbYvvL/kty9oCM/l7msY573I1rUvc5VuRE7p/MvGZHgMjQ78VyX3Klyp7yp2lTuCRgrPTyxHouTSr0uTtRIqbm8n+L/lA/SWlJibaro6uhSr05ICXtfETuvXnRP7vP3e201YMNkKG2HDY1jGpc1rUuRE7iIfoABhzftimfikDx4puGHN+2KZ+KQPHigf2WUzOat5GWUzOat4FoAAxgABZTM5q3lpFTM5q3loAxjZMYAWUzOat5GWUzOat4FoAAxgABZTM5q3lpFTM5q3loAxjZMYAWUzOat5GWUzOat4FoAAxgAAAAFmQrpdniMhXS7PEtAEPWffMfVdd5zzly6Pa4CpZvXuIwLMuXR7XAZCul2eJGbIEWQrpdnieOs++Y+q67zlxFUs3r3AMuXR7XAZcuj2uBGALMhXS7PEZCul2eJaAIes++Y+q67znnLl0e1wFSzevcRgWZcuj2uAyFdLs8SM2QIshXS7PE8dZ98x9V13nLiKpZvXuAZcuj2uAy5dHtcCM60sMttrZSuFu18rLWtr8CBCrc4yHCh1KM1rGpGeiNREdciInJcgHZzkK6XZ4jIV0uzxOpv+UK3v48Wm+dY/1h/KFb38eLTfOsf6wHbH1n3zH1XXec85cuj2uB1NLhAt4711trSr8NVj/WPH3f25/HO0nzpG+sB2yrP8n9FtcDMkm1Sak4My2Vkmtiw2xERZl16IqX6M6rfu/tz+OdpPnSN9Y7QKHNV6Ws1Z3+fpr0moUvC9VAiXtvhX334/KvIBsZNV/veR+Uv+zP1lmViDjXSkg7Gu/wB6en/4z9cSuffNO+Tv+uMSuffNO+Tv+uB56pWfvKQ+WP8Asx1Ss/eUh8sf9meMSuffNO+Tv+uQ1qbrdOpkWcyimOxMVERYD0RVVyJ/b98D+5dk56IslJqDBhpEhPiNfCiq/wBarEuVFan9v/IvyFdLs8Ti30f9ZtVQbNWWmZKuRZCJEnY7FfTokWXe5MRq3OVH8qcicnvHD/8AlCt7+PFpvnWP9YDtj6z75j6rrvOecuXR7XA6mlwgW8d6621pV+Gqx/rHj7v7c/jnaT50jfWA7ZsuXR7XAZCul2eJ1M/d/bn8c7SfOkb6x/X8oVvfx4tN86x/rAdsmQrpdnieOs++Y+q67znU5/KFb38eLTfOsf6x4XCBbx3rrbWlX4arH+sB2y5cuj2uAy5dHtcDqZ+7+3P452k+dI31h939ufxztJ86RvrAds2QrpdniMhXS7PE6m/5Qre/jxab51j/AFh/KFb38eLTfOsf6wHbDFiMp0J8WK9qsxVc5zlxUaic6qS/dJT9PD/b4HVvZ63dtpi0NOgzFsrSRoT5qEx7HVOM5HNV6IqXY3LenaOy6ZfPJVlbKR6y+V6heqxmR2pj4y810JV5gNr7pKfpof7fA/PLaT+FIBm49Q0lQ/XM/YjHqGkqH65n7EDSy2k/hSAf2ysUyVvxZ2DFxu4t11xlY9Q0lQ/XM/YjHqGkqH65n7EDW+6Sn6aH+3wH3SU/TQ/2+Bk49Q0lQ/XM/YjHqGkqH65n7EDSy2k/hSAMtpP4UgGbj1DSVD9cz9iMeoaSofrmfsQNVlYpkrfizsGLjdxbrrjz90lP00P9vgZOPUNJUP1zP2Ix6hpKh+uZ+xA1XWkprWq50xCa1OVVV9yJ/kXZCul2eJ6HaGJPJQLTLOTNahwmUx6y6w2RlbjdTiY3KsNF/snWv/KFb38eLTfOsf6wHbJkK6XZ4njrPvmPquu851OfyhW9/Hi03zrH+seFwgW8d6621pV+Gqx/rAdsuXLo9rgMuXR7XA6mfu/tz+OdpPnSN9Yfd/bn8c7SfOkb6wHbNkK6XZ4jIV0uzxOpv+UK3v48Wm+dY/1h/KFb38eLTfOsf6wHbH1n3zH1XXec85cuj2uB1NLhAt4711trSr8NVj/WPH3f25/HO0nzpG+sB2zZcuj2uBDX5PFoVQd1XmlYi+t/uqdU/wB39ufxztJ86RvrHPHoW6laOqdC/K1GeqiT8R0Oex4s4sSNGejYsRLler+XkS5O5yAcggfzDW9iL3UQ/oAAAPXZxuQzNQRi+uYkxLw8Xkc9y4qsT4X4q/DENinSrZKShSzXq/qbbnPXne7nVy++q3qvwmVaVr1rNBRvrYs46FE/5UYsVNqC03wAAAGS+X6taGaXHxbpSB2r/wCvFNYwlWoPtNPNlIsqxrZaXxuqw3OVb3Rea5yXAaGQrpdnieOs++Y+q67znV5hHt5bqXwiWll4ds7QQ2QqtNMayFU47WNRIz0RGpjciJ2kPXlwgW8d6621pV+Gqx/rAdsuXLo9rgMuXR7XA6mfu/tz+OdpPnSN9Yfd/bn8c7SfOkb6wHbNkK6XZ4jIV0uzxOpv+UK3v48Wm+dY/wBYfyhW9/Hi03zrH+sB2x9Z98x9V13nPOXLo9rgdeXQk2wtbVuiBs3I1O1NcnpWJlOPAmahFiQ3XS8RUva5yovKiLqOwECzLl0e1wGQrpdniRmyBFkK6XZ4njrPvmPquu85cRVLN69wDLl0e1wGXLo9rgRgCzIV0uzxGQrpdniWgCHrPvmPquu855y5dHtcBUs3r3EYFmXLo9rgMhXS7PEjNkCLIV0uzxPHWffMfVdd5y4iqWb17gGXLo9rgMuXR7XAjAFmQrpdniMhXS7PEtAEWQrpdniC0AAYwAsqWb17iMspmc1by0DGNkGMBskVSzevcRllMzmreBGDZAAGMALKlm9e4jLKZnNW8tAxjZBjAbJFUs3r3EZZTM5q3gRnVjhw92W2nh6d8u87Zzqcw8e7Zbfw/O+XeB7N0OOBePhiqdYkoFfh0VaZBhxVc+VWN1THc5Lrkc267FPtHpGp/wDKPLfNDvtSbpaPtotl8SlvHec3gOFXpGp/8o8t80O+1PymughnpeWix1wiyzkhsc+70Jdy3JfpTm0S1j2JnPzD/FUDhhA6CCfjS8OMmEWVRHsR13oS7tpfpTldL0GUpMrQJdqxIkWViwoOOsV6o5WwnNvxVcqJzHsVM9jJX8yz/RCat/09M+Ot8R4GkAABj2kgQZ6FL0uNDSJDmo7ViMW/1jFx1Xk99rU1obF9yXqZlNVZuciVJb+pq3qUtf8A2L71f/iW7U1vdA+UdEfgLTCtSaRIyVdSirT5iJFc+LCfM9URzUS5EV6Xcx8T9I1UPyjyvzQ77U5rADhT6RqoflHlfmh32o9I1UPyjyvzQ77U5rADhT6RqoflHlfmh32p+U50EU/LSkeZXCLKuSFDc+70Jcl9yX6U5tkdc9hJ/wCLRPFUDqvwG4PImE/CHLWQhVVlLdMQYsVJh0BYqNxGq67FRyc93dOQ3pGqh+UeV+aHfanzXoDOyNpXxKb8kp2QAcKfSNVD8o8r80O+1Ph/RE4Io2B+0tOo0euQ6y6ek8q6qyWWCjPVubi3K51/rb7ztGOB/TJPdQs34F//ADxAPGD/AKD6ctbYeiWoh28l5RtVkYU2kBaY56wuqNR2LjdUS+6+6+5Dc9I1P/lHlvmh32pyY6HT3BrD+ApTyTT30DhnSugmqMhU5WebhDloiy8ZkVGLSXJjYrkW6/qvJzHLW+039mkftRPoNcAZF9pv7NI/aifQL7Tf2aR+1E+g1wBgw5m0TqhFlFh0pOpwmRMbGiLfjK5Lub+7/mftj2g/tUj9qIfvB9sk18Tg+PFMHqMG9f8A06nfMMf6ANhH2gXmdSP1xDz/APUf/wBp/XEMqTgQkm4KpISDV6o3lbRYzFTl7TlS5PhXmNSNLQJ6tRYE5CbHgwZeG5kN6XtRznPRVu5lW5qfBy90Dz/9R9ylfriHr0jbGLOyVdnIMSWSDQo8aBO48pHa7GhNxnrDRUviNu5lbejlRUQ0qfDbOVCPS5hViSco5ythOVVR17vUo7uo25bkXup3EPyhWbhMlZ+DHg05YkbGZJqsJP5tvqlanKnJdevInNdeB+lAq1WrtEk6vIJILKzkFsaEsaHFhvRrkvRHMcl7XJ20XmU/eBNWiizkzLNh0m+BiXqronLjJf3D84VP9CZGXmWthQ5zKGJMOg8jYvVItzkXmxvX3oq8t6fCaFP9nap8EHxVAza5I2jqdFnqa51KhpNy0SAr06ouLjtVt93buvOJ/pGp/wDKPLfNDvtTmqAOFXpGp/8AKPLfNDvtR6Rqf/KPLfNDvtTmqAOFXpGp/wDKPLfNDvtR6Rqf/KPLfNDvtTmqAOnOsSmQVWbkeqY6y0d8HHRLsbFcqX3drmIzlNXeg3wlz1bn56FW7KpDmJmJFYjpmOiojnKqX/zXPykXpKsJ/wCHLJ/Ko/2IHGY5PYLuhHnLcYPqNayHbmXkWVOX6sku6mrEWHyql2N1RL+buIfKcN+B60mCSdpkpaOcpc0+owokSCsjEe9GoxURcbGY3+0ndOwLoUux1sX4OTx3Acd/SNVD8o8r80O+1ORWBTBVKWAwZyVkKhPejDpd0ZYkdqPgsiJEiOddiY6pzOu98+mAAiXJcgAAAAD8okGFEfCc9jXOhOx4aqnrVuVt6alVNZ+oAAAADPmqVIzU0szGhO6srEYr2RXMVURVVEXFVL7r1/WaAA4d2o6C6drFpapV4eECXgMnpyNMthLS3OViPerkaruq8t1915m+kaqH5R5X5od9qc1gBwp9I1UPyjyvzQ77UekaqH5R5X5od9qc1gBwp9I1UPyjyvzQ77U4/wCHzBrEwVW9dZSLV2VVySsOZyhsusFPV3+pxVc7mu57ztWOu3pgfZBRPBMt/GB6z0GfZHWY/Sv3aKdj51z9BN2S9lv0r91inZiBjGyDGA2SKpZvXuIyymZzVvAjBsgADGAFlSzevcRllMzmreWgYxsgxgNkiqWb17iMspmc1bwIwbIAAxgBsgxgABZkK6XZ4jIV0uzxAUzOat5aQ9Z98x9V13nPOXLo9rgBaYxZly6Pa4DIV0uzxAjLKZnNW8ZCul2eJ46z75j6rrvOBcCLLl0e1wGXLo9rgBGCzIV0uzxGQrpdniApmc1by0h6z75j6rrvOecuXR7XAC0xizLl0e1wGQrpdniBGWUzOat4yFdLs8Tx1n3zH1XXecC46nMPHu2W38Pzvl3natly6Pa4HVPhzdj4abbOuuvr86v/AH3gch+lo+2i2XxKW8d5zeOEPS0fbRbL4lLeO85vACWsexM5+Yf4qlRLWPYmc/MP8VQPNM9jJX8yz/RCat/09M+Ot8R5TTPYyV/Ms/0QnrUGZipKvlYTIz4EdIisdExL0xXJz3L3QNE/OI9kKG6JEe1jGpe5zluRE7qqQo6tRLkbBkZVO250R0VU/wAKI1P8zxCpTHPbFn5iJOxG8rUiIiQ2r3UYnJrW9ffA/lXvqqYrUcyQX1zlS5Y6dxO4zur2+1ycq6jUREuRERE5kQ8gAAAAAAEdc9hJ/wCLRPFUsIq5y0WeREvXJoniqB12dAZ2RtK+JTfklOyA6kbB1+2Fh7Rw7QWXdNSFShQ3w2RslSJc1yXOS57VTm947UrFz8zUKFAjTsTqkz1OG6IuKjb8aG16cif8wG4cD+mSe6hZvwL/APniHOWpxHwKZNxobsV7IL3NW7mVEVUOr3ojbX2otXhPqv3Tzj5lKZOTMlI40u2FiS7Y78VqYrUxvhW9ffA7EOh09waw/gKU8k099Pm3Q91OmQsBdiYUWoybHsocojmujtRUXqTeRUvPe/Rek/hSR+UN+kC4EPovSfwpI/KG/SPRek/hSR+UN+kC4EPovSfwpI/KG/SPRek/hSR+UN+kD+IPtkmvicHx4phY8S9f9sh/PrvqF0OsUhtoplzqrINRZOCiKswzl9XF98l6vIfjFZ//AKEP64CTc/K4V80x3q28no059/L/AGcXl+Dtm1L+2Gd+LQPGimPBmqdDise60FBVGuRVRsKG1V+Bcfk+EomahTHTWVSdoKbAjKxIb8eKx7XtRVVOTGRb0vXlv7agKD7Zap//AH9ZTVmpCUmo8vHmILYkSXfjwXKq+pXumIyPRocJr4NopKHNo5znTHV4a46uVFcitvuuW5OTtXJcp/foo38baN+wz7QDTtB7Ht+My/lmH8U/2dqnwQfFUzoM9TXx2RahaWnzCQ33w4bIkOGxHdpV9Uqqqdrlu968/unVekrWqm9KpIq1epXKkwy5fUr74HsIIfRek/hSR+UN+kei9J/Ckj8ob9IFwIfRek/hSR+UN+kei9J/Ckj8ob9IFwIfRikfhSS+UN+kta5HNxmqioqXoqdsDyAAOEXTLvbLYz4nNePDOR/QpdjrYvwcnjuOOHTLvbLYz4nNePDOR/QpdjrYvwcnjuA+nAAAAAAAAAAAAAAAAAAAAAB129MD7IKJ4Jlv4zsSOu3pgfZBRPBMt/GBgdBN2S9lv0r91inZidZfQWROpdEnZd9192Vcl/8AwsU7J8uXR7XAC0xizLl0e1wGQrpdniBGWUzOat4yFdLs8Tx1n3zH1XXecC4EWXLo9rgMuXR7XACMFmQrpdniMhXS7PEBTM5q3lpD1n3zH1XXec85cuj2uAFpjFmXLo9rgMhXS7PECMspmc1bxkK6XZ4njrPvmPquu84FwIsuXR7XAZcuj2uAEYLMhXS7PEZCul2eIEYLMhXS7PEAWgACKpZvXuIyypZvXuIwBsmMbIAiqWb17i0iqWb17gIwABsgACKpZvXuIyypZvXuIwBsmMbIAiqWb17i0iqWb17gIzqxw4e7LbTw9O+Xedpx1Y4cPdltp4enfLvA5E9LR9tFsviUt47zm8cIelo+2i2XxKW8d5zeAEtY9iZz8w/xVKiWsexM5+Yf4qgeaZ7GSv5ln+iFJNTPYyV/Ms/0QpAAADEbaehuti+x7ahDWuskkn3SeK7GSXV+J1S+7FuxuS6+8jlLd2SmoFZmIdfk2QKJOOkalFjOWEyXjoqIsNXPREVb1ROS+9VuQ+W1Sq06g9Gkk1XJ6VpstP2ISBLRpmKkOHFiNm1crEc65Ma5FW7uIfFbZwZar4IsKNdlqjMMpsTCSkaXmZWPiQZhixIbVcruZ7UxsZF5kciL2hGf2n1y8q9u7KUifq1PqNYhy8zR5BKjUGOhvXqEsqqiRFVG3KnIvIl6+8f3I23stPVeFSpWsQXzkSlMrDWK1zUyJ63NjK5URqNv7q3+8cfsJ1UnWTOE2zUK0U/VaJJ4OIMWV6vN9XSK5cZqx1dzOe5ES9yc95NUJ2qVF09ZZa1U4FHTAxBnmy0tMKxvVmqnq0Tuua3EXutVU7ZJ5BrlFSp+SqlOgVGmzcGbk5hiRIMeC9HMiNXmc1U5FRe6WIcTLG2hi4NcGeCm3cO1NUqFlFlFkLQSj5xZiHLxIsDHhYrU5GdTe3Fu50RyIfbuh4baONgqptYtZPzc5V6059TitjvV2TsjOxocFiL61rWYnqe0t5a9S30UABQzpuBGhTOXSbGviYqMjQ77uqtS+65e05L1u7XKqL2lTRAGBWavTo1DqDMpZBi5LERYMZepxEXFXkxXXLuOF/TJfdKsz4GXyzznXFgwoyIkWEyIiLeiOai3HHLoo8A9cwv26p89Sa5Tqaym01sGI2aY9VerosRyKmKnNyAfUeh3hQnYCLDq6ExVWhSnKrU0TT3zqEHQw/2UPV8ENIi0DBfZyhR40ONFptOhSj4kNFxXuhtxFcl/Lct157YB+fUIOhh/soOoQdDD/ZQ/QAfn1CDoYf7KDqEHQw/2UP0AH5LLwF54EJfhYh4yaX+94X7CH7AD8cml/veF+wgyaX+94X7CH7AD8cml/veF+wgyaX+94X7CH7AD8cml/veF+wh5SBARLkgw0T/lQ/UAfn1CDoYf7KDqEHQw/wBlD9AB+fUIOhh/soOoQdDD/ZQ/QAST8GDkEx/Mw/6J39VO4p4onsLJfF4fiofrP9YzH5p3+in5UT2Gkvi8PxUAsAAHCLpl3tlsZ8TmvHhnI/oUux1sX4OTx3HHDpl3tlsZ8TmvHhnI/oUux1sX4OTx3AfTgAAAAAAAAAAAAAAAAAAAAA67emB9kFE8Ey38Z2JHXb0wPsgongmW/jA9Z6DPsjrMfpX7tFOx864Ogz7I6zH6V+7RTsfAGyYxsgCKpZvXuLSKpZvXuAjAAGyAAIqlm9e4jLKlm9e4jAGyYxsgCKpZvXuLSKpZvXuAjAAGyAAAAAxgABZTM5q3lpFTM5q3loAxjZMYAWUzOat5GWUzOat4FoAAxgABZTM5q3lpFTM5q3loAxjZMYAWUzOat5GWUzOat4Fp1OYePdstv4fnfLvO2M6nMPHu2W38Pzvl3gchelo+2i2XxKW8d5zeOEPS0fbRbL4lLeO85vACWsexM5+Yf4qlRLWPYmc/MP8AFUDzTPYyV/Ms/wBEKSamexkr+ZZ/ohSAAMxtdpCuVPRGWbcqpe5+Kl6LcvKvIBHayyllbVS8KVtRQaXWIUFyuhMnZdkXEVedW4ycl/vH7wbM2chWcSzcKhUttExMT0PSUZk+Lffd1O7Fuv5ebnOKeHCBQ53ok7QztbsBP28pslZmXmXS8lOLDWWRHLfG9S5Fcl16XJfz8xtYKbUWjsPgSpD6CkjMRbaWqySy8rNTzpuXpEvG9ayLERcZ2JiPvYi33r3b0Edg8cjodlLMMgxILbOUhsKLJtkYjEkYaNfLN9bBVLuWGnaZzJ3CiBQaJAm8sg0anw5lsokkkZksxHpLot6Qb0S/qaf2eb3j4lW8MlqbBylvKbbKTpdXqtmafKz8lNU+G+BBm2TERITGxGOc5YatiOS+5Vvbfzdu6JhBwiWQtRAs7bZbO1OPVqDOVKnzFOgRILZeYloXVHwYjXPdjw7rrnorVXudx+kRj2LCPggkrV0WUsrTp+Vs3ZFZlJiq0inUqEzL3I9r0/nEu6nytS9Uaqrydw+mQYUODCbChMaxjGo1rUS5EROZEONtBwqYXKvM4PGN+4+ClvJOZWVZkkdUkHQGI9Yrl6p/OXtvVGepuW5L+S9fqHQ/W1rFtrFTc7X4Um2p02rTVMmHyjXNhRXQXXY7WuVVbeipyX/QKP19HJaksRtNmVgOxYqQnqxU50dct3+ZULr0uUDFkKcseRgR/RWpr1SE19/V05b0v7h+/oR/90qf/X4CzyrDknSTlVXycRYC3/2U5WLrYrTTAzPQj/7pU/8Ar8D8FoDFmHR21WqNiOajHKkxzoiqqdr+8v6zaAE1OlIUjJQpWCr3MhpcivdjOX31XtqUgAAAAAAAAAAAAAAAAAAAAAAE1UXFpk05O1Beuyp67TItTZTZGFBn48zFWVhvdDgysNMRFal16uciJ8F957DVvYqb/MP8VTFoD3U+ShRYsCNEhTUCC9sSDCdEVqpCY1WuRqKv9VFRbruVebth+8ilRmkdiVaIx7FxYkKJKsRzF9/l/wA0vRT8I01Nwor2LV472sW6JFhyCOZDVOe9ydzt9zt3GjTmxYs7MVB8J8FkRjIcNj0ucqNVy4yp2r1dzc/J75+Eo6cp0BZJtPjzLke9YcVj2oxyK5XIrlVb0Xl5eRfev5gOGnTHIcdlobGrHnEmkdJzKtckNGoiY8Puc5yX6FLsdbF+Dk8dxxn6YtLLJ1Owkq52OsKnzDFd2lVHQ+b3jkx0KXY62L8HJ47gPpwAAAAAAAAAAAAAAAAAAAAAddvTA+yCieCZb+M7Ejrt6YH2QUTwTLfxgYHQTdkvZb9K/dYp2YnWd0E3ZL2W/Sv3WKdmIAxjZMYAWUzOat5GWUzOat4FoAAxgABZTM5q3lpFTM5q3loAxjZMYAWUzOat5GWUzOat4FoAAxgAAAAFmQrpdniMhXS7PEtAEPWffMfVdd5zzly6Pa4CpZvXuIwLMuXR7XAZCul2eJGbIEWQrpdnieOs++Y+q67zlxFUs3r3AMuXR7XAZcuj2uBGALMhXS7PEZCul2eJaAIes++Y+q67znnLl0e1wFSzevcRgWZcuj2uAyFdLs8SM2QIshXS7PE8dZ98x9V13nLiKpZvXuAZcuj2uB1T4c3Y+Gm2zrrr6/Or/wB952mHVjhw92W2nh6d8u8DkT0tH20Wy+JS3jvObxwh6Wj7aLZfEpbx3nN4AS1j2JnPzD/FUqJax7Ezn5h/iqB5pnsZK/mWf6IUk1M9jJX8yz/RCkAZlmOWgyyLypc7n/5lNMzLL+wMt8DvGUDAg4O6BL4Qp63Eq6dlqvOyLJGIsGKjYSQ2uRyKjLrlW9OW+9PePUoWBixlOs/VbOTkCfWi1GpJU4DoU0sNtNm0W9IkDFRFgLevOiq3kuuRORfr5/Lmo5qtciK1UuVFTkUD59QsENjqfQq9S52BP111oGtZVpyrTbpiZm2tS5jXRFuVEb/VxbrufnPxs3gZspRos7MOnK7VpuZp76ZDmqpUXzMWUlHIqLBgq7kY3l7ir757rKqshOMknKqysa/JnL/UcnKsO/uXcrfeRU7SGoB6BSME9l6ZFsVFln1FXWLhR4VKx46KitjMxH9U9T6rk5rrrjZwfWMpFiabPyFFdNOgz1Qj1CNlERHr1WKqK67kS5vJyIezAAAAMyeRZKdSotT+Zc1GTSInM1PWv/w3rf7y39o0mqipeioqLzKh5MtWx6av8xCfMSXbhs5Xwf8AlT+s3+7zp2r+ZA1ATSU3LTcJYsvGZFai3LiryovcVOdF95SkAAAAAAAAAAAAAAAAAAAAAAAACWrexU3+Yf4qmVSpqbfS5KTkGQViQ5SC+I+Kq4rb28iIicqqty9y41aqirS5tES9VgP8VT1umTsFtNkpiTmYsGM6UhQ4rXyEV7HI1vJzIioqXry37gPYKdNujtjQ5hjIcxAddFai3t5UvRUXuKi/6k0CJVJyAyclo0rAgxEx4UKJCVyuaqciucjkuVefkRbvfPwp8/Iy6RXxI0zGjRnY0V+RRW3rciIiJi8iIic3KSwKlGlITZSUe10uxEbDfFlY+PDb2kVEZc65OTnTeBxC6Y3MpN1mxMdrFh3yk21zF52ubEY1yalRUOS/QpdjrYvwcnjuOMXTD3yy1mxkGVfGekOUmle6LCcxXOdEYqr6pE51VV5Dk70KXY62L8HJ47gPpwAAAAAAAAAAAAAAAAAAAAAddvTA+yCieCZb+M7Ejrt6YH2QUTwTLfxgeu9BZE6l0Sdl33X3ZVyX/wDCxTsny5dHtcDrU6DPsjrMfpX7tFOx8CzLl0e1wGQrpdniRmyBFkK6XZ4njrPvmPquu85cRVLN69wDLl0e1wGXLo9rgRgCzIV0uzxGQrpdniWgCHrPvmPquu855y5dHtcBUs3r3EYFmXLo9rgMhXS7PEjNkCLIV0uzxPHWffMfVdd5y4iqWb17gGXLo9rgMuXR7XAjAFmQrpdniMhXS7PEtAEWQrpdniC0AAYwAsqWb17iMspmc1by0DGNkGMBskVSzevcRllMzmreBGDZAAGMALKlm9e4jLKZnNW8tAxjZBjAbJFUs3r3EZZTM5q3gRnVjhw92W2nh6d8u87Zzqcw8e7Zbfw/O+XeByF6Wj7aLZfEpbx3nN46pMEGFe1uC2bqE1ZOLJw4tQhshx1mJdIqKjFVUuvXk51PovpvsMf33RPm5PpA7FiWsexM5+Yf4qnXn6b7DH990T5uT6T843Rc4YYsF8KJN0VWvarXf+nN5lT4QOxGmexkr+ZZ/ohSdcsLousMMOG2G2bouKxqNT/05vMms/r032GT78ovzc36QOxgzLL+wMt8DvGU+E9CFhQtfhVoFenbU1iXgRZCahQoKSstDhorXMVVvxkW/lQ+52Sv+56UvidVXFX1fJ6r1S8vJyfqA1gABJVJZZuRiwWOxYl2NCd/Zei3tXUqIeaZMpOSECaRMXqjEcrf7K9tNS3oVHpLo9RlKTaOOyrrLrIx5l8tDSHDxUTE6ol+Ml68rl7YHuwOuf032GT78ovzc36R6b7DJ9+UX5ub9IHYwDrn9N9hk+/KL83N+kem+wyfflF+bm/SB2MA65/TfYZPvyi/NzfpHpvsMn35Rfm5v0gdhM3TJSZi9WfDdDj3XJGhPWHE/abcqp7y8hmJL1r0ZiS0rW1bLwoEN2LMSrYjnK5z09cit5sVO7znAn032GT78ovzc36T0nCDhuwj22qcvUqjaCYkI0CD1FEpkR8q1zcZXJjIx3Kt6ryqB2f0OYjzNKgxphWrGVFR6tbioqoqpfdet3NzXl56J0P8aNM4D7FzEeNEjRotFlXxIkRyuc9yw0VVVV5VVV7Z72AAAAAAADKq1folIqVNptTqctKTlUiugyMGK+50w9qXq1qdtURUA1QetTlubIydXqVImbQ0+HP0uUdOz8BYqK6VgNRHLEiXetS5UXl7qGlT63SKjBkY8jUpSPDqMukzJqyKl8xCVEXHYnO5tzkW9O6gGmAZdnK9RrRSD56h1GXqEqyM+A6LAfjNSIxbnNv7qKBqAAADOqNYpchUqfTZyfgQJypPfDkoD3XPjuYxXuRqdu5qKq+8aIAAAfhP9YzH5p3+in5UT2Gkvi8PxUP1n+sZj807/RT8qJ7DSXxeH4qAWAADhF0y72y2M+JzXjwzkf0KXY62L8HJ47jjh0y72y2M+JzXjwzkf0KXY62L8HJ47gPpwAAAAAAAAAAAAAAAAAAAAAddvTA+yCieCZb+M7Ejrt6YH2QUTwTLfxges9Bn2R1mP0r92inY+dc/QTdkvZb9K/dYp2YgYxsgxgNkiqWb17iMspmc1bwIwbIAAxgBZUs3r3EZZTM5q3loGMbIMYDZIqlm9e4jLKZnNW8CMGyAAMYAbIMYAAWZCul2eIyFdLs8QFMzmreWkPWffMfVdd5zzly6Pa4AWmMWZcuj2uAyFdLs8QIyymZzVvGQrpdnieOs++Y+q67zgXAiy5dHtcBly6Pa4ARgsyFdLs8RkK6XZ4gKZnNW8tIes++Y+q67znnLl0e1wAtMYsy5dHtcBkK6XZ4gRllMzmreMhXS7PE8dZ98x9V13nAuOpzDx7tlt/D875d52rZcuj2uB1T4c3Y+Gm2zrrr6/Or/AN94H37pcchI1C01sIc/Iys21knLK1I8Fr8Vcd/NenIc0vubs9+AaV8jh/QcNelo+2m2XxKW8d5zfAyvubs9+AaV8jh/QPubs9+AaV8jh/QaoAyvubs9+AaV8jh/QPubs9+AaV8jh/QaoAzoVCokJFSFSKfDRedGyzEv/wAi2FDhwYbYUJjWMalzWtS5ETuIh+gAAAARx6bTo73RJiQlYr3euc+C1yr2uVVQsAGV9zdnvwDSvkcP6B9zdnvwDSvkcP6DVAGV9zdnvwDSvkcP6B9zdnvwDSvkcP6DVAGV9zdnvwDSvkcP6B9zdnvwDSvkcP6DVAGV9zdnvwDSvkcP6Dg90xWQkZDCPZyHIyUtKsdSFc5sGE1iKvVn8q3Ic9jgj0yX3S7M+Bl8s8Dlj0OnuDWH8BSnkmnvp6F0OnuDWH8BSnkmnvoAAAAAAOPHRbJaJbc4KWWSWUSuvq80ySfNpfChvdCamO5O2jUVXXcvNzLzHIcyqrQKNVqjTqjUqZKzc3TIrosjFisRzpd6pcrmL2lVEQDjZgrqLbJ4JMLNm5uGkphIoctPzdXnYi9Vi1FVhvfBm0V6LjMuVLmqlyXoqp6s/KyzKlUcN+DavTNoqms5M4PIM+6DDdCY2M9qQ8aAiYnrIjr3OROW/mVE5DkXVbF2UqlYmKxUbP06aqExJPkI8xEgor4ss9FR0Jy/1mqiqlyn8xbD2QixaLGi2apb4lBa1lKe6WarpNrbsVIa3XtRMVLkTuIB8PwJ12oVqRsfby0GGGdgVWvVGPLzNn4qQ3ykZ2O9rZaFBREdBc1GtXHVVXlS/nS/0Gx8a0dmMGMlbOj2uq8rdb+JI+hbVhpJRIEWZVsRIjMXGe5eX1Su5E5EROc5W06wtjKfaaNaeRsrR5atRlcsSehSbGxnK71y4yJfevbXnXtnlLC2PSjNo6Wcpvoc2dy9st1BOppMY2N1W7+1fy3k0cZ7ZW5wkTVtLbVKlVyapUWzlfZT6fAj1mTlKY2EjmoiTECLdEirGRXKj0XnVLlS5btu3lYtrVLU4aUgW5r1GlbIU2TqFNk5B0NrWxlk1iua5ysVzoeM1b2ovLjX9pD75UrC2NqlpYNpalZajTdZgK1Yc9Gk2OjNVvrVxlS9VTtL2u0fvGslZmNHrceLQpB8WvQmwas9YKXzrGsVjWxP7SI1VTl7SjDXyjB5VJy3GFSxdWqTmxolEsHAqMw9qXIk7UMRF5E5E/m4L1+Bx91Maz9m6BQYkWJRaRJyD40GBAiOgQkarocFmJCYt3aY3kRO0hslmUgAAV+E/wBYzH5p3+in5UT2Gkvi8PxUP0qPsfM/mndu7tL2zFo0v1OnykvMTU21rpdjIMXKL0cnIqIru3E7V6c6c3bRA9iBGskiq5cpmkvV68kVeTGTd2u4fnHgwpeEsxFmZvFa5ioiPc69UTFRLk5Vvv5U7agcMumXe2WxnxOa8eGcj+hS7HWxfg5PHccZumLS8eDXrFvmIsRXrJTLepujdURiJEZct9yKqrfyr7yInNevJnoUux1sX4OTx3AfTgAAAAAA+QW5wkW4lcMETB5YuyVKrExCorKtEiztSWWuYsVYatT1K38uL+tQPr4PjdEwzTFVsdOz0SkU+h2gpNbh0ir06rVJIcKBEc669kZGqj709byJeqKnvr7baPCxg4s/PRpCtWypEjNwZhJaNBiRvVwoioi3PROVqXKnqluTl5wPdwelzdtoElbuepU9OUKBSJOg+i0WYdP/AO0saj7le6FdckFG3r1S/n5Lj+7M4TLA2ktCtAoNraXUan1BI7YECNjK9l197V5nXIvKiKqp27rgPcQeiQsLuDOLXY9FZbajLUYEw2WfByhEVYrnYqMavM9cZURUaq3Lz3HvYAAAAAAOu3pgfZBRPBMt/GdiR129MD7IKJ4Jlv4wMDoJuyXst+lfusU7MTrL6CyJ1Lok7Lvuvuyrkv8A+FinZPly6Pa4AWmMWZcuj2uAyFdLs8QIyymZzVvGQrpdnieOs++Y+q67zgXAiy5dHtcBly6Pa4ARgsyFdLs8RkK6XZ4gKZnNW8tIes++Y+q67znnLl0e1wAtMYsy5dHtcBkK6XZ4gRllMzmreMhXS7PE8dZ98x9V13nAuBFly6Pa4DLl0e1wAjBZkK6XZ4jIV0uzxAjBZkK6XZ4gC0AARVLN69xGWVLN69xGANkxjZAEVSzevcWkVSzevcBGAANkAARVLN69xGWVLN69xGANkxjZAEVSzevcWkVSzevcBGdWOHD3ZbaeHp3y7ztOOrHDh7sttPD075d4HIjpaPtptl8SlvHec3zhB0tH202y+JS3jvOb4AAAAAAAAAAAAAAAAAAAAAAOCPTJfdLsz4GXyzznccEemS+6XZnwMvlngcseh09waw/gKU8k099PQuh09waw/gKU8k099AAAAAAMm2KqlkKy5rla5JCOqKi3Ki9TccFbOtnZDBDZ610vQrbUSfZMwHzFsnVaLGkoUPKMV8R0u17lczF9Ri4qXr+peetUk2T9MmpCI5zYczBfBe5vOiOaqKqe/wAp8Wp/Q20WDZ+XszOW/t3P2agq2+jxahDbLRGo7HRjkZDRcXG5bkVBHJMVzuFG1sbCraagUmm0JbOWXlZWpVGoRosV0aJKRIHVXNhMbyLEW5cVVXFRG8t9569gnw+V61FraHLVGl0uJSq8kVYTKfBmur0tUaroeUxIjUhPR6Jdey5EX3j6vRcHlCplsrTWlY6YivtFKS0nNSkTFWAyFAhrDa1jUS+5Wry3quowrG4GaLZioSz4Fo7VT9MkIEaXp1Jm6jjSkrDioqPajWtRz0uW5MdXYvJdyoiogeiWPw7V+o4V6HZmbWydRp1Zm5iWvoqzUVZJ0NjnMvmXtSDHvxeVId13+vr3QxYTqnPVeBg3oqQJueZUqjPVebqcZ/8AMy6R7mQ4CX3xIioqL3Gpy8vLd9LsvgEoFn6nZyclrT2pmYVm5uJHpMpMzMN8CWY9HI+Ejeppei43rlXG5EuUro+A+zNJgUNadU6rAnaHWY9VlJ5rofVlWOt8aA/1FzoT0uRUuvuROUQS+RYM67ayiRMK2ESuTNmPRaSrsekw5mpVmbZKwHJEh3wkYqK1YLUuxMVvVHL6nkQ9ks7h6tfPWLt5NwLPSFcq9mXyay8SnSk3BgTMKYvvirAip1ZGw0RXLd65OVLk5T3uoYELMT9nq/R4lQrEP0YtC60aTMKMxsaUnFVFRYS4t2Kl3Ijkdzry8138yGBGiS8K0yx7UWrm5m0jJXLp2JPo2ZSLL39TisiMa1Wrct2L6y5ETFu5CYs+vnk5hhtZaTAdb2qUav2PmKlSJRIkGcpMSZgRYcNyL1RXS8ZvVIURt1zVVVa5b+a4+1YIY9dmsGVnZm0j5WJUoshCfEfLRHva9qtRWOVz0xlercVXf3r7r0PXJDApZ5klaZlYq9dr0/aaRSQn6jPR4fV0gIlzWsxGNa27nvxVVVRL7z3OwtnvuVspT7PNq1RqrJGH1KHMTzmOjKxF9S1VY1qXNS5qcnMiX385fqN8AAT1G/0Pmbr7+pO5kv7S9onkIUOLR5SHFYq/zMNfVNRqtVES5bk5lRe5zKfvUrvQ6Zvuu6k/nS9OZSaQmIMvRZN7nsa1YMNrETkxlVqXNai8t69pFAMmnSCJAnoq4qKjYUZb1WJ61qI5brsdXLzJz9rt3f3LQnxIjZucYjY1383C5F6heiIqXpzqt3PqT3/4ZKrM/wC0T8NHuX+jgqnJBRcVbluVUVyKl+N2u17/APcvEiS8WHJzLnxFX+iiryrEuTlxrkRGr/r+sDhp0y29K9YrnuyWb7XJ6+EcjOhS7HWxfg5PHcccumW3fdDYte3kk32v78PtnI3oUux1sX4OTx3AfTgAAAAHhEPg9tWWws10TExbek2CrFpqXHstDpqOkYsJmLFyhYi347k5kRP1ofeT0/ChhBs/g7pcjUbQNnnw56dbJS0OTlljRIkZzXOa1Gpy8uKuu4D4TVMGlvKhYe0NenqA6DXrT2xkas6kwY7IrpKUgxEuR770arkbeq3e9270TUtHg9tPM0/D3iWdiRZi0b4CUhfUK6ba2Fd6lb+S53du5T6hYLC5ZO2FootnZJtWp9YhwMobJVSnxJWLEhItyvYj09UiLrPoKEmOUROuNlasHbGNXK9MQqFNPhzOCRKLBcjmeqnuX+Y5/XcvPze+WUewNpJa0GAqK2iRpODQaBOytYjMxEyKLEkmsTGuXlVYmNzX8t69u85EAvpHHCJXz9OwUYObExbPSEZlKtrKpDr0pUJaPLzyumXuR0BGOWI5zkd6q9ExUby8qoic3T1CnYNbAU20i2jkLHUOVq6PWIk3CkmNiI9edyKicjl5eVOXlXunt4wAAAAAA67emB9kFE8Ey38Z2JHXb0wPsgongmW/jA9Z6DPsjrMfpX7tFOx864Ogz7I6zH6V+7RTsfAGyYxsgCKpZvXuLSKpZvXuAjAAGyAAIqlm9e4jLKlm9e4jAGyYxsgCKpZvXuLSKpZvXuAjAAGyAAAAAxgABZTM5q3lpFTM5q3loAxjZMYAWUzOat5GWUzOat4FoAAxgABZTM5q3lpFTM5q3loAxjZMYAWUzOat5GWUzOat4Fp1OYePdstv4fnfLvO2M6nMPHu2W38Pzvl3gchOlo+2m2XxKW8d5zfOEHS0fbTbL4lLeO85vgAAAAAAAAAAAAAAAAAAAAAA4I9Ml90uzPgZfLPOdxwR6ZL7pdmfAy+WeByx6HT3BrD+ApTyTT309C6HT3BrD+ApTyTT30AAAAAAAAD430U9tbQWKs3ZqPQK9K0B1TtBAp81UJmWZHZLwHsiK6IrXclzcVHLzcic56zglwm2ii4VI1nJ3CDR7f2dh0aLUJysyVNbKMpz2O5GvcxVYqKiLyX38vau5foGHGwNRt4yyMOQjSDIdFtLK1WbZN3q2LAhY+MxqI1UVy43Mtyd1TE/khm6XhBr8ezkzJylibW06LLV6kYzoawphzHMyiWRGq1FVF9Ui3c6ry8iIgaFl8OVma5WKRJ+g1o6bIV2M6DRarPSSQpSfel/qWOxlc1XXLi47W43aPynMPNk5SpzPVKXX32flKh6GzNomSaLToMxjYqtc/GxsVHKjVejVbeqcpg2bwS28etibP2rrtn41mLETsKcp8SQgxWzk6+A1WwEio71ENGovLiq7G97nIJ7AlbaJZqpYM5Wv0JmD+pVV07FjugxfRKFBdGSM6Xan9GvqkS6Iq33X8naA9sthh4sxZuqWgkIlEtLPrZyPBh1iYlJJr4MoyKiK2K5yvS9vquZPVci8lyXmxYPCvQ7XWuj2Zl6VXKVPJT21SVSoyqQUnJNzsVI0O5yqjVVU5HI13Lzc93p9psD1oanJ4XZeXn6Wz7tcjbTsd8S6AkGGjF6r6nk5uTFxj2OiYPKvI4bKfbiJOST6fK2PZQ3wmud1VY7YyPV6Ji3Ylyd2+/tCPR9QAAAAAfhOsdElIzGJe50NyIl93Kqd3tGXSmzcKFBdNyUwsWHD6m1qRWuaxEai3re/wBU5V5Ma5NScq7YAkZMxVVEWRmeVWJeqs5L05V9d2u3/lefjMPyiVdDjUyYfDc1HKxVh334113ruf8Arb7+Q0QBwa6Y1EmVtDY+XmYcRUhS03ixnq1OqosRnLit5EuRE5e33E5jkv0KXY62L8HJ47ifC9g8wbW9tPJNt+yC90lJrkiPqLpa7HeuPyNcmN61vwaz2/BnSKXQbDyFGoSYlMk+qwZROqrEuhpFfi+qW/G5O2B7OAAAAAHwToyYE1M0zBzKyM++nTca3EhDgTjISRHS71bERsRGu5HK1bluXkW4+9n5xYUOJi48Nj8VcZMZt9y91PfA4tUGXtRQcN9pKdbauzlet8yzkyliKhEhQoErNQlY5ytbCY1ESMj05UVV5Ed2rlXAwaTNH9GcGEexE/WJjCHNVFqW0hxo8d8VZfFdlazbXritxXXYl6J2rr1OYboMJ72vfCY5zPWOVqKrfg7gZBhtiPiNYxHvuxnInK67mvXtiODhVWZuA+iVucmZ6sJh5baZYVOl0jR0j4uUN6nDhw78RZXqOMt92L7/ADGlhVprKnMYe6zPTlSdO2cj02PScSeisZJRnQm40SG1rkTGW669U5ubnU5h9Sh9WSLiM6oiXI7F5bu5eFl4DkiXwYa9U9fe1PVfD3SVyifbcd8FFNg2Y6JmBR6VMTqSlVsDBqdQbGmokZZqcyhGrHer3L6tUv5ffXunI0/JIUNHpESGxHo3FR2Kl93cv7h+pZkAAAAAA67emB9kFE8Ey38Z2JHXb0wPsgongmW/jAwOgm7Jey36V+6xTsxOs7oJuyXst+lfusU7MQBjGyYwAspmc1byMspmc1bwLQABjAACymZzVvLSKmZzVvLQBjGyYwAspmc1byMspmc1bwLQABjAAAAALMhXS7PEZCul2eJaAIes++Y+q67znnLl0e1wFSzevcRgWZcuj2uAyFdLs8SM2QIshXS7PE8dZ98x9V13nLiKpZvXuAZcuj2uAy5dHtcCMAWZCul2eIyFdLs8S0AQ9Z98x9V13nPOXLo9rgKlm9e4jAsy5dHtcBkK6XZ4kZsgRZCul2eJ46z75j6rrvOXEVSzevcAy5dHtcDqnw5ux8NNtnXXX1+dX/vvO0w6scOHuy208PTvl3gciOlo+2m2XxKW8d5zfOEHS0fbTbL4lLeO85vgAAAAAAAAAAAAAAAAAAAAAA4I9Ml90uzPgZfLPOdxwR6ZL7pdmfAy+WeByx6HT3BrD+ApTyTT309C6HT3BrD+ApTyTT30AAAAAAAAAAAAAAAAAAAAAAAEVQmnQGshQEa6ZjOxITF5lXnVV95E5V/VzqgHienUgubBhQ3zE09L2QmLdyd1y8zW++uq9T8PQ6ZmlxqlNvc1cxLuWHDT3lVPVO1qie8VU+VZKscl6xIr1vixXJ6p7u6u5O0hWBJLU2ny3LAkpeH77YaIv6ypEREuRLkQ8gAAAAAAAAAAAAAAAAAAAAAAHXb0wPsgongmW/jOxI67emB9kFE8Ey38YHrvQWROpdEnZd9192Vcl/8AwsU7J8uXR7XA61Ogz7I6zH6V+7RTsfAsy5dHtcBkK6XZ4kZsgRZCul2eJ46z75j6rrvOXEVSzevcAy5dHtcBly6Pa4EYAsyFdLs8RkK6XZ4loAh6z75j6rrvOecuXR7XAVLN69xGBZly6Pa4DIV0uzxIzZAiyFdLs8Tx1n3zH1XXecuIqlm9e4Bly6Pa4DLl0e1wIwBZkK6XZ4jIV0uzxLQBFkK6XZ4gtAAGMALKlm9e4jLKZnNW8tAxjZBjAbJFUs3r3EZZTM5q3gRg2QABjACypZvXuIyymZzVvLQMY2QYwGyRVLN69xGWUzOat4EZ1Y4cPdltp4enfLvO2c6nMPHu2W38Pzvl3gchOlo+2m2XxKW8d5zfOEHS0fbTbL4lLeO85vgAAAAAAAAAAAAAAAAAAAAAA4I9Ml90uzPgZfLPOdxwR6ZL7pdmfAy+WeByx6HT3BrD+ApTyTT309C6HT3BrD+ApTyTT30AAAAAAAAAAAAAAAAAAAAAAGZTv9pqU3POvxWOWWge81q+rXW+9P8AAhoRHoyG6IvM1FVdRFZ1mJQpK/1zoLXu99zkxl/zVQNAAAAAAAAAAAAAAAAAAAAAAAAAAADrt6YH2QUTwTLfxnYkddvTA+yCieCZb+MD1noM+yOsx+lfu0U7Hzrn6Cbsl7LfpX7rFOzEDGNkGMBskVSzevcRllMzmreBGDZAAGMALKlm9e4jLKZnNW8tAxjZBjAbJFUs3r3EZZTM5q3gRg2QABjADZBjAACzIV0uzxGQrpdniApmc1by0h6z75j6rrvOecuXR7XAC0xizLl0e1wGQrpdniBGWUzOat4yFdLs8Tx1n3zH1XXecC4EWXLo9rgMuXR7XACMFmQrpdniMhXS7PEBTM5q3lpD1n3zH1XXec85cuj2uAFpjFmXLo9rgMhXS7PECMspmc1bxkK6XZ4njrPvmPquu84Fx1OYePdstv4fnfLvO1bLl0e1wOqfDm7Hw022dddfX51f++8DkN0tH202y+JS3jvOb5wg6Wj7abZfEpbx3nN8AAAAAAAAAAAAAAAAAAAAAAHBHpkvul2Z8DL5Z5zuOCPTJfdLsz4GXyzwOWPQ6e4NYfwFKeSae+nCHBt0X9LslYCg2YiWHnJt9LkIMo6M2oNakRWMRuMiYi3X3cx7B6eOkfk9nvnNn2YHL4HEH08dI/J7PfObPsx6eOkfk9nvnNn2YHL4HEH08dI/J7PfObPsx6eOkfk9nvnNn2YHL4HEH08dI/J7PfObPsx6eOkfk9nvnNn2YHL4HEH08dI/J7PfObPsz2PBj0Wclbu3tKsjJ2IjycxUYqwmR41RRWMVGq69USHf/VA5NgzZGemolSjSU1LQYT4cJkVroUVXoqOVyXLe1Ll9T/maQAAAAZtSn48vPSknKwIUWNM46p1SKrEajURV5mrfzofBsM3RQS2DK3kzZKo2Miz8xLwYUVY8Coo1jke1HIiIsO/kvA5Fg4g+njpH5PZ75zZ9mPTx0j8ns985s+zA5eOajmq1yIqKlyovbM1tAo7Wo1tPgNREuRES5EOKvp46R+T2e+c2fZj08dI/J7PfObPswOVfoDR/wfB/Uo9AaP8Ag+D+pTip6eOkfk9nvnNn2Y9PHSPyez3zmz7MD7XhEtbgxsDaKWhW1n5SlsnJXGlWxIEWIj1a9cZUxGrdzt5z3HBzUqXWbHyVUosw2Yps0sWJKRWo5EdCWI7FuR3KiXXcinXf0UGGiUwxVKiTsrQY9HSmQYsJzYsykXqmO5q3pc1LrsX/ADPpeCTotqZYfBvRLJRbFTc6+mSyQHTDZ9rEiLeq3o3EW7n7oHOcHEH08dI/J7PfObPsx6eOkfk9nvnNn2YHL4HEH08dI/J7PfObPsx6eOkfk9nvnNn2YHL4HpGBG38HCZg7krXy9Ni02HNRIsNJeJFSIrepvVl+MiJffdfzHu4AAAAAAAAAAAAAAOu3pgfZBRPBMt/GdiR129MD7IKJ4Jlv4wMDoJuyXst+lfusU7MTrL6CyJ1Lok7Lvuvuyrkv/wCFinZPly6Pa4AWmMWZcuj2uAyFdLs8QIyymZzVvGQrpdnieOs++Y+q67zgXAiy5dHtcBly6Pa4ARgsyFdLs8RkK6XZ4gKZnNW8tIes++Y+q67znnLl0e1wAtMYsy5dHtcBkK6XZ4gRllMzmreMhXS7PE8dZ98x9V13nAuBFly6Pa4DLl0e1wAjBZkK6XZ4jIV0uzxAjBZkK6XZ4gC0AARVLN69xGWVLN69xGANkxjZAEVSzevcWkVSzevcBGAANkAARVLN69xGWVLN69xGANkxjZAEVSzevcWkVSzevcBGdWOHD3ZbaeHp3y7ztOOrHDh7sttPD075d4HIjpaPtptl8SlvHec3zhB0tH202y+JS3jvOb4AAAAAAAAAAAAAAAAAAAAAAOCPTJfdLsz4GXyzznccEemS+6XZnwMvlngfV8DPQ6YIbQYJ7K12r2VdMT8/SZeYmYvohMNx4joaK5bmxERL1XmRD270rOA/8Tn/ADnNfaHtnQ6e4NYfwFKeSae+gfCU6GLAr6OrK/cg/qWSpEu9Epn12MqX/wBIW+lZwH/ic/5zmvtD6nUIE7DqXohLZKrEl+pxEjOc2652NeioildMmIk1TZeZiwkhPiw2vViOvRL0v5+QD5A3oWsCC332Men/APs5r7Qmq3QwYE5ekzkeFZB7YkOA97V9EprkVGqqZw+5mHU3VKdiz9Kl4coxnUUbjxYjsZWvaqY1yJ3UcnP2gPmEPoWsB7obXfcc/lRF9k5r7Q/r0rOA/wDE5/znNfaH2eG3FYjb77kuP6A6vOiXsnQLH4e6vZez0isnSZZ0qkKAsV8TFx4MNzvVOVXLerlXn7Zzqsv0PGCazVdla7QbNxpCpyjseXmGVGYc6G5UVL0Rz1TmVedDhh0ZfZUWg/OSX7tBOydvrU+ADFpso2VtJNIkeYiqsnC5Y0RXqnq4nNebZnQvbNMfE4XjxDRAAE83MQpWXfHjLcxiXrdzr7yd1V7gGTPyEGpWkhvdEjQ1kJZUa+DFVio6KqXpye9DT9aHpts8AmDC2VdiV209Bj1OpRWNY+YiVCYa5WtS5qXNeicie8e1WYpvVZKPMzsadSbjzcZ8dGzkREavVFRrUuVEua1Gt5O4a/oTLaaf+XRvrAfJfSs4D/xOf85zX2h8F6NbA7g8wdWAo9UshQnU6cmaqkvFiLNxouND6lEddc9yonK1OVDmp6Ey2mn/AJdG+sfjMUGmzLUZMtmJhqLejYs1EeiL3blcBxJ6EDAjgzt9gfZX7VWedP1FahHgrFSdjw/UNxbkxWPRO33D7F6VnAf+Jz/nOa+0Pr9OkZaQlsnk4SQoV6uxUVV5V+EqA+LelZwH/ic/5zmvtB6VnAf+Jz/nOa+0PtIA+LelZwH/AInP+c5r7QelZwH/AInP+c5r7Q+0gD4t6VnAf+Jz/nOa+0HpWcB/4nP+c5r7Q+0n5zEaHLwXRoz0ZDYl6qoHxeY6F/AVLwXRo1kFZDYl6qtTmvtDjj0aGCmxWD2z9nJ+ytCfSHz81HhxGumosVXMaxqtxsdzrlvVeROY50y0KLNxmzc0xWMat8CCv9X+87+973a+E4r9Ms9qtjfj0z4jAPo3QJ9jZRPjM35d59zPhnQJ9jZRPjM35d59zAAAAAAAAAAAAAAB129MD7IKJ4Jlv4zsSOu3pgfZBRPBMt/GB6z0GfZHWY/Sv3aKdj51wdBn2R1mP0r92inY+ANkxjZAEVSzevcWkVSzevcBGAANkAARVLN69xGWVLN69xGANkxjZAEVSzevcWkVSzevcBGAANkAAAABjAACymZzVvLSKmZzVvLQBjGyYwAspmc1byMspmc1bwLQABjAACymZzVvLSKmZzVvLQBjGyYwAspmc1byMspmc1bwLTqcw8e7Zbfw/O+XedsZ1OYePdstv4fnfLvA5CdLR9tNsviUt47zm+cIOlo+2m2XxKW8d5zfAAAAAAAAAAAAAAAAAAAAAABwR6ZL7pdmfAy+Wec7jgj0yX3S7M+Bl8s8Dlj0OnuDWH8BSnkmnvp6F0OnuDWH8BSnkmnvoEFolVKBUVTnyWJ4qlrGtaxGtREaiXJd3D+JiCyYlosvE5WRWKx3wKlyktDiviU5jY39PB/mYyf328irr5FT3lQC8zV5LUNu/rSS42p6Xf6qaRm07/aKnOzyesTFloS91GKquX9pyp/hA0gAB1r9GX2VFoPzkl+7QTsnb61PgOtjoy+yotB+ckv3aCdk7fWp8AGfC9s0x8ThePENEyI7pmBXIkzDkI8zCfLMhosJzEucjnKqLjOT+0h+nVqxHS6HKS8ml/r40Tqjk/wt5NoC6YjwZaA6NMRGw4bedzlIoEOLORmzUzDdDgsXGgQXJc5V/tuTtL3E7XOvLzeZamsSMkxNxYk5MJ618S7FYv8AcanI34ef3zRAzJBMnrE7KqiI2NdMw/fvRGvTUqIv+M0yCqS8SI1kxLXZVLux4aKtyPTmcxV7ip+pbl7R+8nMQ5qA2NCvxXc6LyK1e2ip2lReRUAoAAAAAAAAAPzmI0OXgujRnoyGxL1VQPxWdlOpTERJiGrZZVSMqOv6mqJeqL3FuPwloUWbjNm5pisY1b4EFf6v953973u18JmupMxM0ydWC5JWZm3RVRIjeRWPvua9E7fb7qfrRfYnKjWq5yoiJyqq9oDycRumWe1Wxvx6Z8RhyhWrrMu6nSJdZ5yLcsbGxIDf8f8AW+BqLqOKfTGZech2WshFnp3q8R87MeoaxGQ2eoZyNTlXWqrqA+o9An2NlE+Mzfl3n3M+GdAn2NlE+Mzfl3n3MAAAAAAAAAAAAAAHXb0wPsgongmW/jOxI67emB9kFE8Ey38YGB0E3ZL2W/Sv3WKdmJ1ndBN2S9lv0r91inZiAMY2TGAFlMzmreRllMzmreBaAAMYAAWUzOat5aRUzOat5aAMY2TGAFlMzmreRllMzmreBaAAMYAAAABZkK6XZ4jIV0uzxLQBD1n3zH1XXec85cuj2uAqWb17iMCzLl0e1wGQrpdniRmyBFkK6XZ4njrPvmPquu85cRVLN69wDLl0e1wGXLo9rgRgCzIV0uzxGQrpdniWgCHrPvmPquu855y5dHtcBUs3r3EYFmXLo9rgMhXS7PEjNkCLIV0uzxPHWffMfVdd5y4iqWb17gGXLo9rgdU+HN2Phpts666+vzq/9952mHVjhw92W2nh6d8u8DkR0tH202y+JS3jvOb5wg6Wj7abZfEpbx3nN8AAAAAAA9Ew228XB9YlavLSC1Kpzc3BkKZJ4+KkeZircxqr2k5FVfgu7ZgWfnMOtLtTR4VqJCyteo1QerZ99Ix4EWmLdejv51/86y/k5ExuT9aOj60D53EwyWDh2rSzr6hOtjrUUpSTS0+PkeWL/u/V8XqePfyXXn9PwxWAbaWoWfbV4z56mOmG1HEkYyw5PqLFe9Yr8XFalyLct9zlRUS9QPoQPQLH4XLE2nnpmSk56ck5iXkPRJWVGQjSePJ33ZQxYrWo6H/eQls5htwd16r06lSFXm0mqrGdCpzY9OmITZ1ERVV8JzmI1zPUr6q+6/k7aAfSQfP6ThfsHVLVts5J1aK6ZizL5SXmHSkVspMzDPXwYcdW9Te9OXkReW7kvPoAAAAAAAOCPTJfdLsz4GXyzznccEemS+6XZnwMvlngcseh09waw/gKU8k099PlWAyPUZPAVYNWTEJ6RqNKshQmSTnv/oUdyr1RE5EReXkPc4VYnoUdjJiEyJjrcjHQXy71XuNxlVj197GRQPYjPnJON1dZuTjNgx1REej2YzIqJzI5L05U7Spy/DzFEpMwpmCkWC5XIqqi3pcrVTnRUXlRU7hQBldRq0wuJMxpeVhLyOydXOe74HKiYv6lXuKnOaMCFDgwWQYTEZDYiNa1OZEQ/QAAAB1r9GX2VFoPzkl+7QTsnb61PgOtjoy+yotB+ckv3aCdk7fWp8AHkAAAAAM6Ylo0OK6bkbkiu/pYTuRkX6rru3qXtXaIAhk6jLzMVZdznQJpE9VBipiv+FO05PfS9C4nm5SWnIXUpqBDisRb0R7UW5e6ncU+RdEhhIXA3ZWn12UkJ2pJOTySiQFn8RsP+bc7GveyJf6267k5wPsoPm3Q54Ro2FDBy21MenukHLNxZfqSxkicjLuW9GtTt9w+kgACObqMhJqrZqdl4LkTGxXxER13wc6gUTEaHLwXRoz0ZDYl6qpFBhOmYjZycZiQ2eqgwXf1P77v73+nwmVDqEapTCRpOUdN9Td/MorsWBDX+09/LjO95qOxfh5S5KQ+aXqlYmFnVuvSAjcSA3/Bf6r/ABKuoAtXWYXqdIl1nnJyLGxsSA3/AB3eq+BqLqCUh0yvVKxMrOrdekBG4ku3/Bf6r/Eq6jWY1GtRrURGolyIiciH9AfyxqNajWoiNRLkRE5EOJHTLParY349M+Iw5cnEbplntVsb8emfEYB9G6BPsbKJ8Zm/LvPuZ8M6BPsbKJ8Zm/LvPuYAAAAAAAAAAAAD410T+GibwO02iTkrQYNYWpxosJzYkysLqeI1q3pc1b78b/ID7KddvTA+yCieCZb+M949PHVvyeSPzo77M+A4eMJUbCpbx1qpilQ6W9ZWHLdQhxlip6i/lxlROe/uAeydBZE6l0Sdl33X3ZVyX/8ACxTsny5dHtcDrU6DPsjrMfpX7tFOx8CzLl0e1wGQrpdniRmyBFkK6XZ4njrPvmPquu85cRVLN69wDLl0e1wGXLo9rgRgCzIV0uzxGQrpdniWgCHrPvmPquu855y5dHtcBUs3r3EYFmXLo9rgMhXS7PEjNkCLIV0uzxPHWffMfVdd5y4iqWb17gGXLo9rgMuXR7XAjAFmQrpdniMhXS7PEtAEWQrpdniC0AAYwAsqWb17iMspmc1by0DGNkGMBskVSzevcRllMzmreBGDZAAGMALKlm9e4jLKZnNW8tAxjZBjAbJFUs3r3EZZTM5q3gRnVjhw92W2nh6d8u87Zzqcw8e7Zbfw/O+XeByE6Wj7abZfEpbx3nN84QdLR9tNsviUt47zm+AAAAAAfO8Pthp+3dhYclRZqDK1umT8CqUyJHv6llEFVVrX3cuKqK5L+1einyaqYP7eW+wt2YtXVsGlOshO0qpys3VKu+v5Us7CgKn81ChM5GotyXK5EXmvXnv5OgRybJ7FOKlo8FWFmt2rgz1akUq8an2tg1SDUYton9SfIti3pBgSaokOG5rbr3O5eS5L7z36gWEt7SqVhcdSIspSqzaKrx5uiTfVUX1LmIjXOVL1YvOiXpyKt9x9tUITKNtxSo2CW2LKrWq7aunvotPnrDT1HqE7MV+LVplkZ1zljvxuXFVEW6HDvRETuqZFj7R1Gv23wJWdc6y00yz8SNLtiUartnYkeHDlcTq7mNaiwGXNTkf6pXX8iXHMQy6XQKFS5uNOU2jU6SmY/wDTRpeVZDfE5b/VOaiKvL3SmOOGDjAjaug1ez1nqrQZafo1ArDqjDrEa0k2sJ7WxHPhOhSLXIyHHRXcqqit9dz3rfyi7R5Aw2xAAAAAA4I9Ml90uzPgZfLPOdxwR6ZL7pdmfAy+WeB9+wB2knomCaxkqtm6jLsptPlocGLHa7Fn0yS/Gg4jXXt9UvPcvqV5D7O1rJySakxAubFYivhREvuvS+5ffQ+L4BKnah2CaxsGNZ2HLS0tISzadGbMpGWeZknr1RFTqXKrvUrf633z7EknDmZiTn5qE+HNQGLcxsRVa1XJ6pOTkUDMk3vkq6so973NiOSGqqvK9Farobl7qpiPYq9u5t57EeuxVyu0rFZytbFal6dtITYmMv7cVrfhRe4exAAAAAPX7aVCuS9AqLLJyMtUa8yWc+VgTEXEg493qcd3avXmTkv7qJeqB179GZ2U9oP+eS/doJ2Tt9anwHXNgqwT4QMNWF2qVK1z56SZKzt9dn5qFixGRWqn8xDaqXY9yIiJzMbd7yL2NIlyXAAAAAAAAADi30yJFXBTZ25FX/1xOb8xFOUh/ESHDiNuiMa9E7TkvA6ucHOHPCXg+s39z9lqvBk6ckZ8ZIb5GFFXHddeuM9qr2kPY/TWYcPxllvmqX+odhcKpU6I3HhU2aisvVEe2ScqOuW69OTmPEarUuXYkSako8tCVyNWJGlVa1FVbkvVUA69fTWYcPxllvmqX+ocgOhXt5avCrZe0US2U3KTj4dTkoDoiSbYb3Q3r61FZiol2KvLcq+qX3jk62HJORFayXVF5UVEbymBVYsnCrawWRZeG97pG5iOaiu/nona7YGm2hSbURrY9SRES5ESox0RNs8+gcr98VT5xj/XNQAZfoHK/fFU+cY/1x6Byv3xVPnGP9c1ABl+gcr98VT5xj/XOKHTHJCDJ2XsgsKLNPV07MX9WmYkW71DObGVbjmGcRumWe1Wxvx6Z8RgH0boE+xsonxmb8u8+5nw3oFE/wD8a6Fyf7zN/vDz7kAAAAAAAAAAAA4idMu9rVi/jk14kM5dnETpl3tasX8cmvEhgcIgAB9g6DPsjrMfpX7tFOx865+gm7Jey36V+6xTsxAxjZBjAbJFUs3r3EZZTM5q3gRg2QABjACypZvXuIyymZzVvLQMY2QYwGyRVLN69xGWUzOat4EYNkAAYwA2QYwAAsyFdLs8RkK6XZ4gKZnNW8tIes++Y+q67znnLl0e1wAtMYsy5dHtcBkK6XZ4gRllMzmreMhXS7PE8dZ98x9V13nAuBFly6Pa4DLl0e1wAjBZkK6XZ4jIV0uzxAUzOat5aQ9Z98x9V13nPOXLo9rgBaYxZly6Pa4DIV0uzxAjLKZnNW8ZCul2eJ46z75j6rrvOBcdTmHj3bLb+H53y7ztWy5dHtcDqnw5ux8NNtnXXX1+dX/vvA5DdLR9tNsviUt47zm+cIOlo+2m2XxKW8d5zfAAAAAAAAAAAAAAAAAAAAAABwR6ZL7pdmfAy+Wec7jgj0yX3S7M+Bl8s8DkpgRqUq3Ajg+WBMSqxZWkyznw4r3MTrdWryo1eW93cPdVqc/PqsKVamIvJ/sqPcq/+69rWtT4EVe4Y/Q6e4NYbwFKeSae+gZtIp+RtVz8VYzmo1cRPUsal9zG39pL15edVVVU0gAAAAGHWoMzKRnVSnxWwmuuScY5quRWXXdVRP7bU/WiXLzJduHhURUVFS9F50AnkZaBKwMSByo5cdz1W9XuXncq9tVKTMoN8KHHp7lvyOJiM5c2qI5n6kXF/wAJpgAAAAAAAAAABmWX9gZX/lXxlI7YQ4rZSBPQUlnvlYqXMmIWOx2OqM7SpcqX3lll/YGV/wCVfGU/O1vsFG/OQfKtAzqdZVZORgyqRaZESExG4zqYy9bu3649ftNR5yQnFhS8anw4c6iRo0eFJdTjS7YKsVXQ8V3Pct+pfePpBiVVEdaqjtdcqLBmUVF7fIwDNyaJJ3+isarJBu5JqWnYr4Sp3XNvxmf5p75pS9IlJiCkaBVqnFhPS9r2VB7mqnvKin60FVllj0l6qqyip1JV/rQXX4n6rlb/AIb+2eZmjw0jPmqfGiU+Yct7nQUTEiL/AH2L6l3w8i++B/PoFC/CNW+XP+kegUL8I1b5c/6Tx6JTcj6mrSl0NP8Ae5dFfD+FzfXM/wA09805eNCmILY0CKyLCel7XscjmqnvKgGb6BQvwjVvlz/pOKPTG6eySsvZFWzU5Gxp2Y5I8d0RE9Qzmv5jmKcRumWe1Wxvx6Z8RgHHGwWD7DVXrLwKnY2m2gj0WI56Qnyk71OGqo5Udc3HT+si9o514NadM0vBHZeRrdInoFoJeDJw5uLGgOV7YqRGYyuict/b5bzI6BPsbKJ8Zm/LvPsVovYz9IgeVYBogAAZtpYroFnalGhNc57ZWKrGtW5Vdircie/eaRm1r+ffLU5OXq8VHxPehsVHL+tcVv8AiA+IdE3Z20FewRS1NsDQqq2utnID3rKw3S8TqaMcj73qrb0vVOS/lOK38knRJ/ga1vzl/wDsOyoAdav8knRJ/ga1vzl/+wfySdEn+BrW/OX/AOw7KgB1q/ySdEn+BrW/OX/7CSp4EMP1UaxlTsraGebDVVYkxNtiI1V57sZ63HZqAOrv0u+Gf8QKn+3C+uek20snaKxda9BrT0qNTKh1JsXqEVWq7EdfcvIqpy3KdvR129MD7IKJ4Jlv4wMDoJuyXst+lfusU7MTrL6CyJ1Lok7Lvuvuyrkv/wCFinZPly6Pa4AWmMWZcuj2uAyFdLs8QIyymZzVvGQrpdnieOs++Y+q67zgXAiy5dHtcBly6Pa4ARgsyFdLs8RkK6XZ4gKZnNW8tIes++Y+q67znnLl0e1wAtMYsy5dHtcBkK6XZ4gRllMzmreMhXS7PE8dZ98x9V13nAuBFly6Pa4DLl0e1wAjBZkK6XZ4jIV0uzxAjBZkK6XZ4gC0AARVLN69xGWVLN69xGANkxjZAEVSzevcWkVSzevcBGAANkAARVLN69xGWVLN69xGANkxjZAEVSzevcWkVSzevcBGdWOHD3ZbaeHp3y7ztOOrHDh7sttPD075d4HIjpaPtptl8SlvHec3zhB0tH202y+JS3jvOb4AAAAAAAAAAAAAAAAAAAAAAOCPTJfdLsz4GXyzznccEemS+6XZnwMvlngcseh09waw/gKU8k099PQuh09waw3gKU8k099AAHyToiMN9AwSUeE2M1KjXZu5ZWnsiI12Jfc6K9eXFanLdyeqXkTtqgfWUc1VVqORVTnRF5UP6Pn2D21VBtxZun2lsRMrMujpfHiReRzVT18KYu/r38yJzcip6nn93kJlkzDxmorHsXFiQ3euY7uL/wD3LzgVAADMhLiWmjNROSLJscvwte5P4jTMyGmPaaM5F5IUoxq/C57l/hT9ZpgAAAAAAAAAABmWX9gZX/lXxlPztb7BRvzkHyrT9LL+wMr/AMq+Mp+drfYKN+cg+VaBrmLVPbbRvzUz/ow2jFqntto35qZ/0YB+leRZZ0GrMRb5S9I6J/WgOux/1XI7/Cqds1WqioioqKi8qKh4c1HNVrkRUVLlRe2ZdBVZZY9JeqqsoqdSVf60F1+J+q5W/wCG/tgaxlTNHhpFfNU+M+nzDlvc6CiYj1/vsX1Lvh5F981QBj+iU3I+pq0pdDT/AHuXRXw/hc31zP8ANPfOLXTI40KYshYyNAisiwnzsyrXscjmqmIzmVDl6cPumRScrLWdslGl4DIT4s9MrExORHLiM5VROS/3+cD6d0CfY2UT4zN+XefYrRexn6RA8qw+O9An2NlE+Mzfl3n2K0XsZ+kQPKsA0QDPj1WVZFWXgY83MpzwYKYyp/zLzN/xKgFMzHhS8F8aK9GMYl6r/wD3OvvE1NgxXRYk/MtVsePdisXNQ05m/Dyqq++vvIfzLy0ePGbM1DFV7VvhQGreyEvdv/rO9/tdpO2ukAAAAAAAAAOu3pgfZBRPBMt/GdiR129MD7IKJ4Jlv4wPWegz7I6zH6V+7RTsfOuDoM+yOsx+lfu0U7HwBsmMbIAiqWb17i0iqWb17gIwABsgACKpZvXuIyypZvXuIwBsmMbIAiqWb17i0iqWb17gIwABsgAAAAMYAAWUzOat5aRUzOat5aAMY2TGAFlMzmreRllMzmreBaAAMYAAWUzOat5aRUzOat5aAMY2TGAFlMzmreRllMzmreBadTmHj3bLb+H53y7ztjOpzDx7tlt/D875d4HITpaPtptl8SlvHec3zhB0tH202y+JS3jvOb4AAAAAAAAAAAAAAAAAAAAAAOCPTJfdLsz4GXyzznccEemS+6XZnwMvlngfNLN4E8ONYs/T6tRKBU41MnJdkaUiMqUJjXQnJe1UasRFRLlTkVEL/wCQDoh/xbq/ztB+1OdvQ6e4NYfwFKeSae+gdav8gHRD/i3V/naD9qbuDvoWMJ9o7ZS0K3EhMUSkNufNzsWbhRormJm4aNc5cZeZFXkTn5eZew0AYtjrNUWyNm5Sz9nqfCkKdJsxIUKGn63KvO5yryqq8qqWTctEWLlUqrWTDEu5fWxG/wBl25e1+tFuAE0lNQ5qErm3sexcWJDd65ju4v8A/cp+7nI1qucqIiJeqr2iObloixcplcVkwxLuX1sRv9l25e1+tFlfFfVf9jSFFhQUX/bMdLl/NJ3b+2qcl3wgfrQWrEhR55UudOROqNRUuVIaIjWbKIvwqpphEuS5AAAAAAAAAAAAGZZf2Blf+VfGU/O1vsFG/OQfKtP0sv7Ayv8Ayr4yn52t9gY35yD5VoGuYtU9ttG/NTP+jDaMWqe22jfmpn/RgG0ZNc/2Z0GrsRb5S9I6J/WgOux/2bkd/hVO2ax/Lmo5qtciKipcqL2wPLVRURUVFReVFQ8mTQVWWWNSXqt8oqdRVf60F1+J+q5W/wCG/tmsAOI3TLParY349M+Iw5cnEbplntVsb8emfEYB9G6BPsbKJ8Zm/LvPtU/Kw5yVdLxlejXKi3scrXIqKioqKnNyoh8V6BPsbKJ8Zm/LvPuYGZ6CyT2XTCzUwnbbGmYj2r/hVbv8i6WgQJeEkKXgw4LE5mMajUTUh+oAAAAAAAAAAAAddvTA+yCieCZb+M7Ejrt6YH2QUTwTLfxgYHQTdkvZb9K/dYp2YnWd0E3ZL2W/Sv3WKdmIAxjZMYAWUzOat5GWUzOat4FoAAxgABZTM5q3lpFTM5q3loAxjZMYAWUzOat5GWUzOat4FoAAxgAAAAFmQrpdniMhXS7PEtAEPWffMfVdd5zzly6Pa4CpZvXuIwLMuXR7XAZCul2eJGbIEWQrpdnieOs++Y+q67zlxFUs3r3AMuXR7XAZcuj2uBGALMhXS7PEZCul2eJaAIes++Y+q67znnLl0e1wFSzevcRgWZcuj2uAyFdLs8SM2QIshXS7PE8dZ98x9V13nLiKpZvXuAZcuj2uB1T4c3Y+Gm2zrrr6/Or/AN952mHVjhw92W2nh6d8u8DkR0tH202y+JS3jvOb5wg6Wj7abZfEpbx3nN8AAAAAAAAAAAAAAAAAAAAAAHBHpkvul2Z8DL5Z5zuOCPTJfdLsz4GXyzwOWPQ6e4NYfwFKeSae+noXQ6e4NYfwFKeSae+gAAAAAAAAAAAAAAAAAAAAPwm3R2ysV8rDbEjoxVhsc65HOu5EVQPluHXCFZDBLZJ9RqCzEaoR8ZKdTIM9FY6Yicq8yO9TDRV5XXXJzJeqoi8ImYTsPNtpyfm6HVrXTcBY2PEl6U2PEgy163tYiNxsVEu5L1v5O2cwMOWBqzGGOlyMSHORZO0kvExPRDqOM+HDR385CjMvTkTlxUv5FuuvRXX/AE7BrYiz+D+ykrZuzUmktJQEve9eWJHiL66JEd/Wct3P8CJciIgHX5903RRffGE35LNfVP5dX+icfGZGdEwlrEhoqMcsrNXtRbr7vU9u5DstAHWp903RRffGE35LNfVH3TdFF98YTfks19U7KwB1praDonVjJFWLhM6o1qtR2SzV6ItyqnrfeQ8/dN0UX3xhN+SzX1TsrAHWp903RRffGE35LNfVMS2Elh3thAl4FqKPb2sQpZyvgNm6fMxEhuVLlVL28l9yHaMAPjHQX0qp0XofqNT6xTpynTjJiaV8vNQHQojUWO9UVWuRFS9OU+zgAAAAAAAAAAAAAAA67emB9kFE8Ey38Z2JHXb0wPsgongmW/jA9d6CyJ1Lok7Lvuvuyrkv/wCFinZPly6Pa4HWp0GfZHWY/Sv3aKdj4FmXLo9rgMhXS7PEjNkCLIV0uzxPHWffMfVdd5y4iqWb17gGXLo9rgMuXR7XAjAFmQrpdniMhXS7PEtAEPWffMfVdd5zzly6Pa4CpZvXuIwLMuXR7XAZCul2eJGbIEWQrpdnieOs++Y+q67zlxFUs3r3AMuXR7XAZcuj2uBGALMhXS7PEZCul2eJaAIshXS7PEFoAAxgBZUs3r3EZZTM5q3loGMbIMYDZIqlm9e4jLKZnNW8CMGyAAMYAWVLN69xGWUzOat5aBjGyDGA2SKpZvXuIyymZzVvAjOrHDh7sttPD075d52znU5h492y2/h+d8u8DkJ0tH202y+JS3jvOb5wg6Wj7abZfEpbx3nN8AAAAAAAAAAAAAAAAAAAAAAHBHpkvul2Z8DL5Z5zuOCPTJfdLsz4GXyzwOWPQ6e4NYfwFKeSae+33Jep6F0OnuDWH8BSnkmntFqGtfRIzHta5rnw0VFS9FTqjeRQNRFRUvRUVDyZy0SlKqOZIwoLk5nQb4Tv1tuU/NJWoynqpScdMsRP6CaW9f8ADERL/wBpHagNUEclOQ5pXw7nwo8P+khREue3cqe+l6KWAAAAAAAAAAAAAAAAAZUZjZCrpNNajYU45sOPcmcuuY9fh9Z+z3DVI6xLrNUyZgN5HuhqsNe49OVq6lRFP1kJhJqRgTKJckaG2Iidy9LwP3AAAAAAAAAAAAAAAAAAAAAAAAAAA67emB9kFE8Ey38Z2JHXb0wPsgongmW/jA9Z6DPsjrMfpX7tFOx865+gm7Jey36V+6xTsxAxjZBjAbJFUs3r3EZZTM5q3gRg2QABjACypZvXuIyymZzVvLQMY2QYwGyRVLN69xGWUzOat4EYNkAAYwA2QYwAAsyFdLs8RkK6XZ4gKZnNW8tIes++Y+q67znnLl0e1wAtMYsy5dHtcBkK6XZ4gRllMzmreMhXS7PE8dZ98x9V13nAuBFly6Pa4DLl0e1wAjBZkK6XZ4jIV0uzxAUzOat5aQ9Z98x9V13nPOXLo9rgBaYxZly6Pa4DIV0uzxAjLKZnNW8ZCul2eJ46z75j6rrvOBcdTmHj3bLb+H53y7ztWy5dHtcDqnw5ux8NNtnXXX1+dX/vvA5DdLR9tNsviUt47zm+cIOlo+2m2XxKW8d5zfAAAAAAAAAAAAAAAAAAAAAABwR6ZL7pdmfAy+Wec7jgj0yX3S7M+Bl8s8Dlj0OnuDWH8BSnkmntVpvYaL+cheUaeq9Dp7g1hvAUp5Jp7Vab2Gi/nIXlGgaYAAjnJVI6I5jupR4fLCionK1e4vdRe2m+5RTZpZmE7qjEhx4TsSNDvvxXe93UVLlRe4pYZk//ALJUpedb6yIqS8f4FX1DtTlu/wAagaYAAAAAAAAB83w84W7PYKLJuqlVckzUphHNp1OY+6JMvTt/3WJemM7tc3Kqoih71OzboapAlWtjTT0vaxVuRqf2nL2m/wCvaPNPnEmceE9iwZmFckaCq3q1V5l99q3Lcvb+FFROBnQ7Wiw0YSuiEi2xpNSVFRWtq8aM1yyMGUvW6BiIvL28RqLjX3uv9c452rTEYnVpeIqTiLesd3KsT+67ut97tdoDTBJJzLZhitc1YUeEt0WEq8rV3ovaXt/rQrAGbZi/7npH8w274LuQ/Wsx3S1LmYzOWIkNUhp3XryNTWqoh+0jASVkoEs1b0gw2sRe7clwH7gAAAAAAAAAAAAAAAAAAAAAAAAAAddvTA+yCieCZb+M7Ejrt6YH2QUTwTLfxgYHQTdkvZb9K/dYp2YnWX0FkTqXRJ2XfdfdlXJf/wALFOyfLl0e1wAtMYsy5dHtcBkK6XZ4gRllMzmreMhXS7PE8dZ98x9V13nAuBFly6Pa4DLl0e1wAjBZkK6XZ4jIV0uzxAUzOat5aQ9Z98x9V13nPOXLo9rgBaYxZly6Pa4DIV0uzxAjLKZnNW8ZCul2eJ46z75j6rrvOBcCLLl0e1wGXLo9rgBGCzIV0uzxGQrpdniBGCzIV0uzxAFoAAiqWb17iMsqWb17iMAbJjGyAIqlm9e4tIqlm9e4CMAAbIAAiqWb17iMsqWb17iMAbJjGyAIqlm9e4tIqlm9e4CM6scOHuy208PTvl3nacdWOHD3ZbaeHp3y7wORHS0fbTbL4lLeO85vnCDpaPtptl8SlvHec3wAMaJLrOVyahxJmbZDhQIKsZCjuYl7lfevIvKvIn6j9/QeD9+VH5ZE+kDSBm+g8H78qPyyJ9I9B4P35UflkT6QNIGb6Dwfvyo/LIn0j0Hg/flR+WRPpA0gZvoPB+/Kj8sifSPQeD9+VH5ZE+kDSBm+g8H78qPyyJ9I9B4P35UflkT6QNIGb6Dwfvyo/LIn0j0Hg/flR+WRPpA0gZvoPB+/Kj8sifSPQeD9+VH5ZE+kDSBm+g8H78qPyyJ9JM+WWTrEgkKam3NiuiNe2LMOe1URiqnIq91ANs4I9Ml90uzPgZfLPOdxwR6ZL7pdmfAy+WeB8HpuFDCNTafL0+nW6tJKSctDSFAgQalFYyGxEuRrWo65ERO0dg2Bmo2hqvQ/WWqdUnIc9EmJSA+NMTER748T+dTlc5edfhOufB5ZqNbG3FHstLzUOUi1SbZLMjRGq5sNXLdeqJyqdm2CawkCz+DCj2ZqE1MTkSmwllor4c1GZDiOhxHJjI1HciXpfcB9CBn+hErpp/5dG+sPQiV00/8ALo31gNAzrStc6z8/1NuNEZLvfDS+71bUxm/5oh59CJXTT/y6N9Y/l9GlHscx8Sec1yKios9GuVF/xAejYQqnV/QyykeZitlZSdrcmyZZKRIqPfDe16qxcXlVL7r0949hhQrMRHxWQ2zz3Q1Rr0as0uKtyLcupUXWZWECzSvhWcWlPnEfI1mXjo10aLHRGMY++5jnXLch+8SWunZmbmXzMSLMuRyqtMiJditRtyXP94DTyWzioidRqPJzck0erYTY9DksHVrJmmTFQl6lJUeaiwYjHzLXwYqQHOY6/tKi3Kimt1OB/Zj/ADZG+uZFp6THnrI2mo1PmpiFErcjGlkR9MejWvfBWEi3q7kTlS8Drt/lewp/lFtX86xvrD+V7Cn+UW1fzrG+sffvSPWm/HmkfJIn0j0j1pvx5pHySJ9IHwH+V7Cn+UW1fzrG+sU2JkLQ4YsK1EoNctLOzU7UYqS+Xz8Z8w+FCa1z1RMZb1uRHXJeiXr2r7z9MPWC+dwT2ygWan6rLVOLGkWTiRYENzGojnvbi3L2/UX6zU6D/skbG/GovkIgHYzg2sRZ/B/ZOVs3ZqTSWkoCXvevLEjxF9dEiO/rOXu/AiXIiIezgARTkssdWx4D+pzMNPUPu5FTttcnbavFD+pKZSYYrXNWFHhrdFhKvK1d6L2l7f60KyKdk1juSLBiul5hiKjIrWoqoi86Ki8ip7y9vlA/CKmW1VkBvLLybkiRV7Tot3qW6r8ZffxTUJ5OXhS0BsKEi4qKqqqrerlXlVVXtqq8t5QAAAAAAAAAAAAAAAAAAAAAAAAAAJqg90KnzMVi3PZCc5q3cyoi3AUnXb0wPsgongmW/jMH00uHD8cm/Nsr9mfO8INtrSW9tAtftVUEn6isFsHq3UWQ/UNvuS5iInbXtAe+dBn2R1mP0r92inY+dcHQZ9kdZj9K/dop2PgDZMY2QBFUs3r3FpFUs3r3ARgADZAAEVSzevcRllSzevcRgDZMY2QBFUs3r3FpFUs3r3ARgADZAAAAAYwAAspmc1by0ipmc1by0AYxsmMALKZnNW8jLKZnNW8C0AAYwAAspmc1by0ipmc1by0AYxsmMALKZnNW8jLKZnNW8C06nMPHu2W38Pzvl3nbGdTmHj3bLb+H53y7wOQnS0fbTbL4lLeO85vnU7gswoWxwaTU9NWPqMKSiz0NkOYWJLQ4uM1qqqevRbuVV5j3z02GG38ZZP5rl/qAdisn7YZ/4vA/1iGiceOgnwi2swkUC0tVtdPwp2blpuDLwnsl2QkRmI511zERF5VU5DgAAAAAAAAAAAAAAAADMqXsxSvzkTybjTPhHRo27tNg9weUa0FlJ2HJz7qu2XWI+AyKmI6DFVUucipztTlA+7nBHpkvul2Z8DL5Z56P6bDDb+Msn81y/wBQ+fYUcJFrcJNVlKna+ehTs1KQOoQXQ5dkJEZjK665iIi8qqBf0OHu72L8LwPGOzF9Jp7nuess3Ge5XOuVUvVVvVefunWd0OHu72L8LwPGOz8D86dRaW/HxpRrrrudy+/75V6BUr7yZ+tfpP2pmc1by0DM9AqV95M/Wv0mV6EU772T9p30ntBjARwKZIwYzI0OXakRiqrXKqrcqoqcl/vKqazYpmc1byMspmc1bwLQABjAADgT0wP3bZLwHA8rGPTug/7JGxvxqL5CIe49MD922S8BwPKxj07oP+yRsb8ai+QiAdoAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAM20LojKW/qUWJCc6LCZjsW5yI6I1FuXtciqS1WkQ0pc2uXVLkgP8A97f/AGV98rtF7F/+/A8qw/er+xU5+Yf4qgdOIAA+z9BN2S9lv0r91inZidZ3QTdkvZb9K/dYp2YgDGNkxgBZTM5q3kZZTM5q3gWgADGAAFlMzmreWkVMzmreWgDGNkxgBZTM5q3kZZTM5q3gWgADGAAAAAWZCul2eIyFdLs8S0AQ9Z98x9V13nPOXLo9rgKlm9e4jAsy5dHtcBkK6XZ4kZsgRZCul2eJ46z75j6rrvOXEVSzevcAy5dHtcBly6Pa4EYAsyFdLs8RkK6XZ4loAh6z75j6rrvOecuXR7XAVLN69xGBZly6Pa4DIV0uzxIzZAiyFdLs8Tx1n3zH1XXecuIqlm9e4Bly6Pa4HArCj0NmFav4SrTV2n0qnuk6jVpqal3OqENFWG+K5zVVFW9FuVOQ50gDr59KRho/A1N+coX0j0pGGj8DU35yhfSdj4A4+dBbg1tVgzoVo6Ra2Wl5eampqDMQmwY7YqKzFc2+9vNytU5BmPVZeabPLNSk91BYsJsN7VhI9PUq5UXl/wCdf8ibGrP4VZ8mb9IHsIPXsas/hVnyZv0l+SVX8L//ABmgaQM3JKr+F/8A4zSebhVeDi4tWRb7+eWb9IG0D17GrP4VZ8mb9Ixqz+FWfJm/SB7CDNySq/hf/wCM0ZJVfwv/APGaBpAxZuFV4OLi1ZFvv55Zv0n4Y1Z/CrPkzfpA9hB69jVn8Ks+TN+kvySq/hf/AOM0DSPhfRoWDtFhCwdUihWZl4EedZWGR1bFjNhpiNgxUXlX4UPsWSVX8L//ABmks5JzSR5eJM1B0dsJzntakFreXFVvOnvOUDr09Kphi/BFN+cYX0j0qmGL8EU35xhfSdhwA4T4Guhmwr2bwqWbr1XpdPhSEhUYUeYeyfhvc1jV5VREW9fgOcmQrpdniWgCHrPvmPquu855y5dHtcBUs3r3EYFmXLo9rgMhXS7PEjNkCLIV0uzxPHWffMfVdd5y4iqWb17gGXLo9rgMuXR7XAjAFmQrpdniMhXS7PEtAHXr0wuF1HDjINxsb/0KAvNdnYx6T0H/AGSNjfjUXyEQ976Yp7ukj4BgeWjHonQf9kjY341F8hEA7QAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAZ1ovYv/wB+B5Vh+9X9ipz8w/xVPwtF7F/+/A8qw/er+xU5+Yf4qgdOIAA+ydBZE6l0Sdl33X3ZVyX/APCxTsny5dHtcDrU6DPsjrMfpX7tFOx8CzLl0e1wGQrpdniRmyBFkK6XZ4njrPvmPquu85cRVLN69wDLl0e1wGXLo9rgRgCzIV0uzxGQrpdniWgCHrPvmPquu855y5dHtcBUs3r3EYFmXLo9rgMhXS7PEjNkCLIV0uzxPHWffMfVdd5y4iqWb17gGXLo9rgMuXR7XAjAFmQrpdniMhXS7PEtAEWQrpdniC0AAYwAsqWb17iMspmc1by0DGNkGMBskVSzevcRllMzmreBGDZAAGMALKlm9e4jLKZnNW8tAxjZBjAbJFUs3r3EZZTM5q3gRg2QABjACypZvXuIyymZzVvLQMY2QYwGyRVLN69xGWUzOat4EYNkAAYwAsqWb17iMspmc1by0DGNkGMBskVSzevcRllMzmreBGDZAAGMALKlm9e4jLKZnNW8tAxjZBjAbJFUs3r3EZZTM5q3gRg2QABjADgn0xT3dJHwDA8tGPROg/7JGxvxqL5CIe49MD922S8BwPKxj07oP+yRsb8ai+QiAdoAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAM60XsX/78DyrD96v7FTn5h/iqfhaL2L/9+B5Vh+9X9ipz8w/xVA6cQAB9g6DPsjrMfpX7tFOx865+gm7Jey36V+6xTsxAxjZBjAbJFUs3r3EZZTM5q3gRg2QABjACypZvXuIyymZzVvLQMY2QYwGyRVLN69xGWUzOat4EYNkAAYwA2QYwAAsyFdLs8RkK6XZ4gKZnNW8tIes++Y+q67znnLl0e1wAtMYsy5dHtcBkK6XZ4gRllMzmreMhXS7PE8dZ98x9V13nAuBFly6Pa4DLl0e1wAjBZkK6XZ4jIV0uzxAUzOat5aQ9Z98x9V13nPOXLo9rgBaYxZly6Pa4DIV0uzxAjLKZnNW8ZCul2eJ46z75j6rrvOBcCLLl0e1wGXLo9rgBGCzIV0uzxGQrpdniApmc1by0h6z75j6rrvOecuXR7XAC0xizLl0e1wGQrpdniBGWUzOat4yFdLs8Tx1n3zH1XXecC4EWXLo9rgMuXR7XACMFmQrpdniMhXS7PEBTM5q3lpD1n3zH1XXec85cuj2uAFpjFmXLo9rgMhXS7PECMspmc1bxkK6XZ4njrPvmPquu84FwIsuXR7XAZcuj2uAEYLMhXS7PEZCul2eICmZzVvLSHrPvmPquu855y5dHtcALTGLMuXR7XAZCul2eIEZZTM5q3jIV0uzxPHWffMfVdd5wLgRZcuj2uAy5dHtcAIwWZCul2eIyFdLs8QOv3pgfu2yXgOB5WMendB/2SNjfjUXyEQ926YXC6jhxkG42N/6FAXmuzsY9J6D/ALJGxvxqL5CIB2gAAAAAAAAAAAAAPQ8Llvn2E+5fFpTah6PWglqOt8fqfUUjY38561ca7F9byX909xqM5KU6Rjz0/NQJSVgMWJFjxoiMZDanKrnOXkRE7qnyPoqKTXahSLFT1CoVQrb6PayTqUzLSTEdF6jCbEVyoiqidxPhVDJwpTVqsLeCyu0Cm4P7SUWclokrNslqy2FAh1FrIyPdAa5HuS9Ub27kvuGL8fVLM4QLE2kp8/UKDamk1CUp7FfORYMy1Ul2oiqrn/2W3Iq3rycil0G1Fm4jqQ2FXac9a01z6YjZhq5a1rcZVhcvq0RqovJfyHw/7mrS26t3XrTyFip2x8itipmgsgVFIUGLPTMW/ETFhucnUmciI9feuS7mxrBUq287aTAnJz2D+u0iVsbAmpSpzk2kPqaxFleporEa9VViq1PVKiIquuS+4I+5QMJmD6NWJOkS9taDFn557octLsnmOdEejlarUuX12MipcvKqpch+ldwjWDoNcdQq1a+iU6ow4Sxny8zOMY9jETGvdevJyJfcvKqcpx7kcHFpoOA6lSDbJzTa03CAyoxoaQESMkBJhy9WVefFxLuXuEOE2BOWfs9hvpczZZLQMrM7EqEKtQI8u+BKQ8Vt0KOqvx4cSEqLiMxVVy8yInKTLK65K2jwiWGs6lP9HbWUanJUmJEk+rzTW9WYvM9vL63lT1XN757PCiMiw2xIb2vY5Ec1zVvRUXmVFOJFfsTa5lQ9GoVHtXWKZaKxdPp0CHQ0k1Vr2wEa+XmMpY5YUJyrjY7E5L151Tk5L4NaI+z2D6g0J7JiG6Qp8GAsONMNjvh4rETEWI1rUfi816IiLdzGqS3sgAIoAAAAAzrRexf/AL8DyrD96v7FTn5h/iqfjXIMaYpr4cvDSJFSJDejFdi42K9rlS/tciEdVnamtLm0WjPROoP/AN4Z/ZX3wOoMAAfZ+gm7Jey36V+6xTsxOsvoLInUuiTsu+6+7KuS/wD4WKdk+XLo9rgBaYxZly6Pa4DIV0uzxAjLKZnNW8ZCul2eJ46z75j6rrvOBcCLLl0e1wGXLo9rgBGCzIV0uzxGQrpdniApmc1by0h6z75j6rrvOecuXR7XAC0xizLl0e1wGQrpdniBGWUzOat4yFdLs8Tx1n3zH1XXecC4EWXLo9rgMuXR7XACMFmQrpdniMhXS7PECMFmQrpdniALQABFUs3r3EZZUs3r3EYA2TGNkARVLN69xaRVLN69wEYAA2QABFUs3r3EZZUs3r3EYA2TGNkARVLN69xaRVLN69wEYAA2QABFUs3r3EZZUs3r3EYA2TGNkARVLN69xaRVLN69wEYAA2QABFUs3r3EZZUs3r3EYA2TGNkARVLN69xaRVLN69wEYAA2QABFUs3r3EZZUs3r3EYA2TGNkARVLN69xaRVLN69wEYAA2QAB19dMU93SR8AwPLRj0ToP+yRsb8ai+QiHI7om8BVr8LuE+XrtBnKNIy8KmZLizsxER7lhR4iK65sNURFx0u5e0eu4CehttrYTCXZW3FWqlBjU6BMoroctGiuir1SG5jbkWGic7kv5QOagAAAAAAAAAAAAAAAAAAHo9oME2Div2jW0VZsbR56qOc1z5iLARViK25EV6cz1uRE9Ui8yHvAA/lrUa1GtREREuRE7R/QAAAAAAAAAA/CehOjyUeCxUR0SG5iKvNeqXH7gDgF6SrCZ+H7KfKI/wBkfGcMWDqs4MLYLZiuzUjMziS0OYx5N7nQ8V99yXua1b+Re0dsZ129MD7IKJ4Jlv4wPWegz7I6zH6V+7RTsfOuDoM+yOsx+lfu0U7HwBsmMbIAiqWb17i0iqWb17gIwABsgACKpZvXuIyypZvXuIwBsmMbIAiqWb17i0iqWb17gIwABsgAAAAMYAAWUzOat5aRUzOat5aAMY2TGAFlMzmreRllMzmreBaAAMYAAWUzOat5aRUzOat5aAMY2TGAFlMzmreRllMzmreBaAAMYAAWUzOat5aRUzOat5aAMY2TGAFlMzmreRllMzmreBaAAMYAAWUzOat5aRUzOat5aAMY2TGAFlMzmreRllMzmreBaAAMYAAWUzOat5aRUzOat5aAMY2TGAFlMzmreRllMzmreBaAAMYAAeuxJSFMxJNYroyK1zmorIz4a3OnWo5PUql96LdymoxqNstQGt5kjSiJy39tCOX/AKSV/wCf/wD7mlye1mg/npX/AFQD2UAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAADrt6YH2QUTwTLfxnYkddvTA+yCieCZb+MDA6Cbsl7LfpX7rFOzE6zugm7Jey36V+6xTsxAGMbJjACymZzVvIyymZzVvAtAAGMAALKZnNW8tIqZnNW8tAGMbJjACymZzVvIyymZzVvAtAAGMAAAAAsyFdLs8RkK6XZ4loAh6z75j6rrvOecuXR7XAVLN69xGBZly6Pa4DIV0uzxIzZAiyFdLs8Tx1n3zH1XXecuIqlm9e4Bly6Pa4DLl0e1wIwBZkK6XZ4jIV0uzxLQBD1n3zH1XXec85cuj2uAqWb17iMCzLl0e1wGQrpdniRmyBFkK6XZ4njrPvmPquu85cRVLN69wDLl0e1wGXLo9rgRgCzIV0uzxGQrpdniWgCHrPvmPquu855y5dHtcBUs3r3EYFmXLo9rgMhXS7PEjNkCLIV0uzxPHWffMfVdd5y4iqWb17gGXLo9rgMuXR7XAjAFmQrpdniMhXS7PEtAEPWffMfVdd5zzly6Pa4CpZvXuIwLMuXR7XAZCul2eJGbIEWQrpdnieOs++Y+q67zlxFUs3r3AMuXR7XAZcuj2uBGALMhXS7PEZCul2eJaAIes++Y+q67znnLl0e1wFSzevcRgWZcuj2uAyFdLs8SM2QIshXS7PE8dZ98x9V13nLiKpZvXuAZcuj2uAy5dHtcCMAWZCul2eIyFdLs8S0AenQ24keWbffdEu/wDnNLEVUszQbtNK/wCqGfMzEvLzMuseYgwUWKt3VHo2+6ebfdeXIqLZigqioqLGlFRU7fKgHs4AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAHXb0wPsgongmW/jOxI67emB9kFE8Ey38YHrvQWROpdEnZd9192Vcl//AAsU7J8uXR7XA61Ogz7I6zH6V+7RTsfAsy5dHtcBkK6XZ4kZsgRZCul2eJ46z75j6rrvOXEVSzevcAy5dHtcBly6Pa4EYAsyFdLs8RkK6XZ4loAh6z75j6rrvOecuXR7XAVLN69xGBZly6Pa4DIV0uzxIzZAiyFdLs8Tx1n3zH1XXecuIqlm9e4Bly6Pa4DLl0e1wIwBZkK6XZ4jIV0uzxLQBFkK6XZ4gtAAGMALKlm9e4jLKZnNW8tAxjZBjAbJFUs3r3EZZTM5q3gRg2QABjACypZvXuIyymZzVvLQMY2QYwGyRVLN69xGWUzOat4EYNkAAYwAsqWb17iMspmc1by0DGNkGMBskVSzevcRllMzmreBGDZAAGMALKlm9e4jLKZnNW8tAxjZBjAbJFUs3r3EZZTM5q3gRg2QABjACypZvXuIyymZzVvLQMY2QYwGyRVLN69xGWUzOat4EYNkAAYwA+DYc8PEhgkt/L0Cq2R9G3vkXzUOLDm0YiNix3qiKjoa3KmJy3KvOZGCbonKdb219mLBQLITNPfHjw2tmnTzXtb1Jiv9ajE58S7n5Lz4z0wP3bZLwHA8rGPTug/7JGxvxqL5CIB2gAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAddvTA+yCieCZb+M7Ejrt6YH2QUTwTLfxges9Bn2R1mP0r92inY+dc/QTdkvZb9K/dYp2YgYxsgxgNkiqWb17iMspmc1bwIwbIAAxgBZUs3r3EZZTM5q3loGMbIMYDZIqlm9e4jLKZnNW8CMGyAAMYAbIMYAAWZCul2eIyFdLs8QFMzmreWkPWffMfVdd5zzly6Pa4AWmMWZcuj2uAyFdLs8QIyymZzVvGQrpdnieOs++Y+q67zgXAiy5dHtcBly6Pa4ARgsyFdLs8RkK6XZ4gKZnNW8tIes++Y+q67znnLl0e1wAtMYsy5dHtcBkK6XZ4gRllMzmreMhXS7PE8dZ98x9V13nAuBFly6Pa4DLl0e1wAjBZkK6XZ4jIV0uzxAUzOat5aQ9Z98x9V13nPOXLo9rgBaYxZly6Pa4DIV0uzxAjLKZnNW8ZCul2eJ46z75j6rrvOBcCLLl0e1wGXLo9rgBGCzIV0uzxGQrpdniApmc1by0h6z75j6rrvOecuXR7XAC0xizLl0e1wGQrpdniBGWUzOat4yFdLs8Tx1n3zH1XXecC4EWXLo9rgMuXR7XACMFmQrpdniMhXS7PEBTM5q3lpD1n3zH1XXec85cuj2uAFpjFmXLo9rgMhXS7PECMspmc1bxkK6XZ4njrPvmPquu84FwIsuXR7XAZcuj2uAEYLMhXS7PEZCul2eIHX70wP3bZLwHA8rGPTug/wCyRsb8ai+QiHu3TC4XUcOMg3Gxv/QoC812djHpPQf9kjY341F8hEA7QAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAOu3pgfZBRPBMt/GdiR129MD7IKJ4Jlv4wMDoJuyXst+lfusU7MTrL6CyJ1Lok7Lvuvuyrkv/AOFinZPly6Pa4AWmMWZcuj2uAyFdLs8QIyymZzVvGQrpdnieOs++Y+q67zgXAiy5dHtcBly6Pa4ARgsyFdLs8RkK6XZ4gKZnNW8tIes++Y+q67znnLl0e1wAtMYsy5dHtcBkK6XZ4gRllMzmreMhXS7PE8dZ98x9V13nAuBFly6Pa4DLl0e1wAjBZkK6XZ4jIV0uzxAjBZkK6XZ4gC0AARVLN69xGWVLN69xGANkxjZAEVSzevcWkVSzevcBGAANkAARVLN69xGWVLN69xGANkxjZAEVSzevcWkVSzevcBGAANkAARVLN69xGWVLN69xGANkxjZAEVSzevcWkVSzevcBGAANkAARVLN69xGWVLN69xGANkxjZAEVSzevcWkVSzevcBGAANkAARVLN69xGWVLN69xGANkxjZAEVSzevcWkVSzevcBGAANkAAdfXTFPd0kfAMDy0Y9E6D/ALJGxvxqL5CIe99MU93SR8AwPLRj0ToP+yRsb8ai+QiAdoAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAHXb0wPsgongmW/jOxI67emB9kFE8Ey38YHrPQZ9kdZj9K/dop2PnXB0GfZHWY/Sv3aKdj4A2TGNkARVLN69xaRVLN69wEYAA2QABFUs3r3EZZUs3r3EYA2TGNkARVLN69xaRVLN69wEYAA2QAAAAGMAALKZnNW8tIqZnNW8tAGMbJjACymZzVvIyymZzVvAtAAGMAALKZnNW8tIqZnNW8tAGMbJjACymZzVvIyymZzVvAtAAGMAALKZnNW8tIqZnNW8tAGMbJjACymZzVvIyymZzVvAtAAGMAALKZnNW8tIqZnNW8tAGMbJjACymZzVvIyymZzVvAtAAGMAALKZnNW8tIqZnNW8tAGMbJjACymZzVvIyymZzVvAtAAGMAAOBPTA/dtkvAcDysY+OYM7Xz9g7c0y1lMlpaZnKdEdEhwphHLDcqsc3lxVReZy8ynJXozMF9v7Z4WZSqWXsrUKrJQ6RBgujQEarUekSKqt5V57lT9Z8T9L/hk/J9WP2W/WA+p+nZwi/izZX/px/tR6dnCL+LNlf+nH+1Plnpf8Mn5Pqx+y36x+X8g+F78Qqv8AsN+kD6x6dnCL+LNlf+nH+1Hp2cIv4s2V/wCnH+1Pk/8AIPhe/EKr/sN+k/qHgDwwRL8SwFYddz3Nb9IH1b07OEX8WbK/9OP9qe34GOiutvbXClQLK1GgWdl5SpzSQYsSAyMkRqYqre2+IqX8nbQ48Q8BGF6I/EZYOsK5ca5MRv8AVXFd2+0vIe/dDrgiwlUDDPZOv1mx1TkqZLz7HRZmKxEYxFRWoq8vdVE1gdiAAAAAAAAAAAAAAAAAAAHHfotMOtpsEVaoMlQaVSJ2HUZeLFiLOtiKrVY5qIiYj28nL2zkQcR+jwwfWztxamzC2Ts9O1hJOSjJMLLtRep4z0xb71TnxV/UB6D6dnCL+LNlf+nH+1Hp2cIv4s2V/wCnH+1Pk6YCMLqo1UsDWFx3rDb6hvK5L705/eX9QgYB8L0eGkSDYGsPaqIqKjG8y83bA+senZwi/izZX/px/tR6dnCL+LNlf+nH+1Plnpf8Mn5Pqx+y36w9L/hk/J9WP2W/WA+p+nZwi/izZX/px/tT4phlwj1XChbNbUVqSkZOaWXhy/U5RHJDxWX3L6pyrfy900/5B8L34hVf9hv0j+QfC9+IVX/Yb9IG70E3ZL2W/Sv3WKdmJwF6E3BJhIs1h6s/XK7ZCpSFNlso6vMxWtRkPGl4jW38vbVUTWc+gBjGyYwAspmc1byMspmc1bwLQABjAACymZzVvLSKmZzVvLQBjGyYwAspmc1byMspmc1bwLQABjAAAAALMhXS7PEZCul2eJaAIes++Y+q67znnLl0e1wFSzevcRgWZcuj2uAyFdLs8SM2QIshXS7PE8dZ98x9V13nLiKpZvXuAZcuj2uAy5dHtcCMAWZCul2eIyFdLs8S0AQ9Z98x9V13nPOXLo9rgKlm9e4jAsy5dHtcBkK6XZ4kZsgRZCul2eJ46z75j6rrvOXEVSzevcAy5dHtcBly6Pa4EYAsyFdLs8RkK6XZ4loAh6z75j6rrvOecuXR7XAVLN69xGBZly6Pa4DIV0uzxIzZAiyFdLs8Tx1n3zH1XXecuIqlm9e4Bly6Pa4DLl0e1wIwBZkK6XZ4jIV0uzxLQBD1n3zH1XXec85cuj2uAqWb17iMCzLl0e1wGQrpdniRmyBFkK6XZ4njrPvmPquu85cRVLN69wDLl0e1wGXLo9rgRgCzIV0uzxGQrpdniWgCHrPvmPquu855y5dHtcBUs3r3EYFmXLo9rgMhXS7PEjNkCLIV0uzxPHWffMfVdd5y4iqWb17gGXLo9rgMuXR7XAjAFmQrpdniMhXS7PEtAEPWffMfVdd5zzly6Pa4CpZvXuIwLMuXR7XAZCul2eJGbIEWQrpdnieOs++Y+q67zlxFUs3r3AetPdNLFk4spMulnOjTTXKjGvvR87DavOncVS2URW2SpTXOVypHlkVypdevVW8pJC/3L4xG/f4RbLe1WmfGJfyzQPYwAAAAAAAAAAAAAAAAAAM2H7aI3xKH47zSM2H7aI3xKH47wPXJDK1qssx8450syedEbB6m1ERXPmU57r+TFQ26C7JKFIOux+qS0Ne5d6lPpMen+ykv8aTyk4a8h7AUv4szxWgXZcuj2uAy5dHtcCMAWZCul2eIyFdLs8S0AQ9Z98x9V13nPOXLo9rgKlm9e4jAsy5dHtcBkK6XZ4kZsgRZCul2eJ46z75j6rrvOXEVSzevcAy5dHtcBly6Pa4EYAsyFdLs8RkK6XZ4loAh6z75j6rrvOecuXR7XAVLN69xGBZly6Pa4DIV0uzxIzZAiyFdLs8Tx1n3zH1XXecuIqlm9e4Bly6Pa4DLl0e1wIwBZkK6XZ4jIV0uzxLQBFkK6XZ4gtAAGMALKlm9e4jLKZnNW8tAxjZBjAbJFUs3r3EZZTM5q3gRg2QABjACypZvXuIyymZzVvLQMY2QYwGyRVLN69xGWUzOat4EYNkAAYwAsqWb17iMspmc1by0DGNkGMBskVSzevcRllMzmreBGDZAAGMALKlm9e4jLKZnNW8tAxjZBjAbJFUs3r3EZZTM5q3gRg2QABjACypZvXuIyymZzVvLQMY2QYwGyRVLN69xGWUzOat4EYNkAAYwAsqWb17iMspmc1by0DGNkGMBskVSzevcRllMzmreB65C/wBy+MRv3+EWy3tVpnxiX8s0mi9cyvxmP+/wimW9qtM+MS/lmgexgAAAAAAAAAAAAAAAAAAZsP20RviUPx3mkZsP20RviUPx3gev0/2Ul/jSeUnDXkPYCl/FmeK0yKf7KS/xpPKThtWQ9hpb4vC8UDwDZAAGMALKlm9e4jLKZnNW8tAxjZBjAbJFUs3r3EZZTM5q3gRg2QABjACypZvXuIyymZzVvLQMY2QYwGyRVLN69xGWUzOat4EYNkAAYwA2QYwAAsyFdLs8RkK6XZ4gKZnNW8tIes++Y+q67znnLl0e1wAtMYsy5dHtcBkK6XZ4gRllMzmreMhXS7PE8dZ98x9V13nAuBFly6Pa4DLl0e1wAjBZkK6XZ4jIV0uzxAUzOat5aQ9Z98x9V13nPOXLo9rgBaYxZly6Pa4DIV0uzxAjLKZnNW8ZCul2eJ46z75j6rrvOBcCLLl0e1wGXLo9rgBGCzIV0uzxGQrpdniApmc1by0h6z75j6rrvOecuXR7XAC0xizLl0e1wGQrpdniBGWUzOat4yFdLs8Tx1n3zH1XXecC4EWXLo9rgMuXR7XACMFmQrpdniMhXS7PEBTM5q3lpD1n3zH1XXec85cuj2uAFpjFmXLo9rgMhXS7PECMspmc1bxkK6XZ4njrPvmPquu84FwIsuXR7XAZcuj2uAEYLMhXS7PEZCul2eICmZzVvLSHrPvmPquu855y5dHtcALTGLMuXR7XAZCul2eIEZZTM5q3jIV0uzxPHWffMfVdd5wLgRZcuj2uAy5dHtcAIwWZCul2eIyFdLs8QFMzmreWkPWffMfVdd5zzly6Pa4AWmMWZcuj2uAyFdLs8QIyymZzVvGQrpdnieOs++Y+q67zgYMXrmV+Mx/3+EVyUvMR7KyLZZsN0VjoUVGvcrUXFiI5UvuW7kTuGbGgQ5qJKRI8afl4KRZxcaUYrvVJNNc1Fua7+zf2uYlosSoQKZLwXRqk1WNuuesVF5+2mTrcusD2vKKz+DJT5Yv2Yyis/gyU+WL9mYOUz2mn/wBuN/4wyme00/8Atxv/ABgN7KKz+DJT5Yv2Yyis/gyU+WL9mYOUz2mn/wBuN/4wyme00/8Atxv/ABgN7KKz+DJT5Yv2Yyis/gyU+WL9mYOUz2mn/wBuN/4wyme00/8Atxv/ABgN7KKz+DJT5Yv2Yyis/gyU+WL9mYOUz2mn/wBuN/4wyme00/8Atxv/ABgN7KKz+DJT5Yv2Yyis/gyU+WL9mYOUz2mn/wBuN/4wyme00/8Atxv/ABgN7KKz+DJT5Yv2Yyis/gyU+WL9mYOUz2mn/wBuN/4wyme00/8Atxv/ABgN7KKz+DJT5Yv2Yyis/gyU+WL9mYOUz2mn/wBuN/4wyme00/8Atxv/ABgN7KKz+DJT5Yv2Z/EhCnXVeNOzcCDAasBsJrYcZYirc5yqq+pS7nQxMpntNP8A7cb/AMYZTPaaf/bjf+MB/NP9lJf40nlJw2rIew0t8XheKeuWek35TIR3x6s+ayuIsaFFhv6kjEWMqLesNv8AbvReS+9D2GguyShSDrsfqktDXuXepT6QNoEWXLo9rgMuXR7XACMFmQrpdniMhXS7PEBTM5q3lpD1n3zH1XXec85cuj2uAFpjFmXLo9rgMhXS7PECMspmc1bxkK6XZ4njrPvmPquu84FwIsuXR7XAZcuj2uAEYLMhXS7PEZCul2eICmZzVvLSHrPvmPquu855y5dHtcALTGLMuXR7XAZCul2eIEZZTM5q3jIV0uzxPHWffMfVdd5wLgRZcuj2uAy5dHtcAIwWZCul2eIyFdLs8QIwWZCul2eIAtAAEVSzevcRgADZAAEVSzevcABGAANkAARVLN69xGAANkAARVLN69wAEYAA2QABFUs3r3EYAA2QABFUs3r3AARgADZAAEVSzevcRgADZAAEVSzevcABGAANkAARVLN69xGAANkAARVLN69wAEYAA2QABFUs3r3EYAA2QABFUs3r3AAZDZCC3G6nFnIaOc56tZNxWtvcqqtyI65OVVU/rI2ffM/8ujfWAA0/QqW0k/8ALo31x6FS2kn/AJdG+uABLPU6DDxMSPPpfff/ALdG97+8TZGz75n/AJdG+sAAyNn3zP8Ay6N9Y0/QqW0k/wDLo31wAHoVLaSf+XRvrks9ToMPExI8+l99/wDt0b3v7wAE2Rs++Z/5dG+sMjZ98z/y6N9YADT9CpbST/y6N9cehUtpJ/5dG+uABLPU6DDxMSPPpfff/t0b3v7xNkbPvmf+XRvrAAMjZ98z/wAujfWNP0KltJP/AC6N9cAB6FS2kn/l0b65/EeBDlpWXl4TVbChMxGIqqtyIiInKvKAB+AAA2QABFUs3r3EYAA2QABFUs3r3AARgADZAAEVSzevcRgADZAAEVSzevcABGAANkAAAAB//9k="
}
```


***Status Code:*** 200

<br>



### 5. Get Level


Op name: 

> scgrids.readLevel

This gets a given Level for a valid Project


***Endpoint:***

```bash
Method: POST
Type: RAW
URL: /v1/actions
```


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Authorization | {{access_token}} | (Required) The Login Acces Token |
| x-sc-identity | external | (Required) |



***Query params:***

| Key | Value | Description |
| --- | ------|-------------|
| op | scgrids.readLevel | (Required) Operation Name |
| org | {{org}} | (Required) Organisation ID |
| pid | {{pid}} | (Required) Project ID |
| propid | {{propid}} | (Optional) Property ID |



***Body:***

```js        
{
    "LID": "{{lid}}"
}
```



***More example Requests/Responses:***


##### I. Example Request: Get Level


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Authorization | {{access_token}} | (Required) The Login Acces Token |
| x-sc-identity | external | (Required) |



***Query:***

| Key | Value | Description |
| --- | ------|-------------|
| op | scgrids.readLevel | (Required) Operation Name |
| org | {{org}} | (Required) Organisation ID |
| pid | {{pid}} | (Required) The Project ID |



***Body:***

```js        
{
    "LID": "{{lid}}"
}
```



##### I. Example Response: Get Level
```js
{
    "status": 200,
    "message": "Success",
    "data": {
        "Name": "New Name",
        "Level": "L1",
        "Area": 5000,
        "FloorPlan": "https://smartclean-images-staging.s3-ap-southeast-1.amazonaws.com/7da2a1b48bf144c6b5a3f6dd64704ed1/06ecedab24104909bde7497a397fd4c4/floorplans/4df01e9e2fb548a0b7afe1892543b390/plan.jpg",
        "LID": "{{lid}}"
    }
}
```


***Status Code:*** 200

<br>



### 6. List Zones By Level


Op name: 

> scgrids.listZonesByLevel

This lists all the Zones for a given Level


***Endpoint:***

```bash
Method: POST
Type: RAW
URL: https://console.smartclean.io/api/scgrids/v1/actions
```


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Authorization | {{access_token}} | (Required) Login Access Token |
| x-sc-identity | external | (Required) |



***Query params:***

| Key | Value | Description |
| --- | ------|-------------|
| op | scgrids.listZonesByLevel | (Required) Operation Name |
| org | {{org}} | (Required) Organisation ID |
| pid | {{pid}} | (Required) Project ID |
| propid | {{propid}} | (Optional) Property ID |



***Body:***

```js        
{
    "LID": "{{lid}}",
    "ESK": "87590cfd0d5445668bb912d09fbf131d"
}
```



***More example Requests/Responses:***


##### I. Example Request: List Zones By Level


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Authorization | {{access_token}} |  |



***Query:***

| Key | Value | Description |
| --- | ------|-------------|
| op | scgrids.listZonesByLevel | (Required) Operation Name |
| org | {{org}} | (Required) Organisation ID |
| pid | {{pid}} | (Required) Project ID |



***Body:***

```js        
{
    "LID": "{{lid}}",
    "ZoneCategoryIDs": [
        "LABS"
    ],
    "ESK": "87590cfd0d5445668bb912d09fbf131d"
}
```



##### I. Example Response: List Zones By Level
```js
{
    "status": 200,
    "message": "Success",
    "data": [
        {
            "InsID": "4f74612817bf446f8a765a757b27d488",
            "LID": "0ca1a58621254754b45b7aa545770d0a",
            "ZoneCategoryID": "LABS",
            "Name": "New test name",
            "Area": 6000,
            "FloorType": "Test floor 2",
            "Status": "PENDING"
        },
        {
            "InsID": "87590cfd0d5445668bb912d09fbf131d",
            "LID": "0ca1a58621254754b45b7aa545770d0a",
            "ZoneCategoryID": "LABS",
            "Name": "Zone 5",
            "Area": 3000,
            "FloorType": "hardwood",
            "Status": "active"
        }
    ],
    "LEK": "87590cfd0d5445668bb912d09fbf131d"
}
```


***Status Code:*** 200

<br>



### 7. Update Level


Op name: 

> scgrids.updateLevel

This updates a Given Level details like FloorPlan, Area or Name.


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
| op | scgrids.updateLevel | (Required) Operation Name |
| org | {{org}} | (Required) Organisation ID |
| pid | {{pid}} | (Required) The Project ID |
| propid | {{prop_id}} | (Required) Property ID |



***Body:***

```js        
{
    "LID": "{{lid}}",
    "Area": 3000,
    "Level": "L10",
    "Name": "TestLevel"
}
```



***More example Requests/Responses:***


##### I. Example Request: Update Level


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Authorization | {{access_token}} | (Required) The Login Access Token |
| x-sc-identity | external | (Required) |



***Query:***

| Key | Value | Description |
| --- | ------|-------------|
| op | scgrids.updateLevel | (Required) Operation Name |
| org | {{org}} | (Required) Organisation ID |
| pid | {{pid}} | (Required) The Project ID |
| propid | {{prop_id}} | (Required) Property ID |



***Body:***

| Key | Value | Description |
| --- | ------|-------------|
| LID | {{lid}} |  |
| Name | New Name |  |
| file |  |  |
| Area | 5000 |  |
| Level | L10 |  |



##### I. Example Response: Update Level
```js
{
    "status": 200,
    "message": "Success",
    "data": {
        "Name": "New Name",
        "Level": "L10",
        "Area": 5000,
        "LID": "{{lid}}"
    }
}
```


***Status Code:*** 200

<br>



### 8. Update Level FloorPlan


Op Name:

> scgrids.updateLevelFloorPlan

This updates the FloorPlan of a Level


***Endpoint:***

```bash
Method: POST
Type: FORMDATA
URL: /v1/actions
```


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Authorization | {{access_token}} |  |



***Query params:***

| Key | Value | Description |
| --- | ------|-------------|
| op | scgrids.updateLevelFloorPlan | (Required) Operation Name |
| org | {{org}} | (Required) Organisation Name |
| pid | {{pid}} | (Required) Project ID |
| propid | {{prop_id}} | (Optional) Property ID |



***Body:***

| Key | Value | Description |
| --- | ------|-------------|
| file |  |  |
| LID | {{lid}} |  |



## Property
## This directory lists all the APIs regarding Property



### 1. Create Property


Op name

> scgrids.createProperty

This creates a new Property object given an Organisation and increments the Property Metrics counter


***Endpoint:***

```bash
Method: POST
Type: RAW
URL: /v1/actions
```


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Content-Type | application/json |  |
| Authorization | {{access_token}} | (Required) The Login Access Token |
| x-sc-identity | external | (Required) |



***Query params:***

| Key | Value | Description |
| --- | ------|-------------|
| op | scgrids.createProperty | (Required) Operation name  |
| org | {{org}} | (Required) Organisation ID |
| pid | scnoop | (Required) The pid will be scnoop it it's not known |



***Body:***

```js        
{
    "Name": "Test Property for getProperty query change to SUB1", 
    "TypeID": "TEST",
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
    "TimeZone": "Asia/Kolkata",
    "Country": "{{country}}",
    "CountryLocale": "{{country_locale}}"
}
```



***More example Requests/Responses:***


##### I. Example Request: Create Property


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Content-Type | application/json |  |
| Authorization | {{access_token}} | (Required) The Login Access Token |
| x-sc-identity | external | (Required) |



***Query:***

| Key | Value | Description |
| --- | ------|-------------|
| op | scgrids.createProperty | (Required) Operation name  |
| org | {{org}} | (Required) Organisation ID |
| pid | scnoop | (Required) The pid will be scnoop it it's not known |



***Body:***

```js        
{
    "Name": "Test Property 2", 
    "TypeID": "BANK",
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
    "TimeZone": "Asia/Kolkata",
    "Country": "{{country}}",
    "CountryLocale": "{{country_locale}}"
}
```



##### I. Example Response: Create Property
```js
{
    "status": 201,
    "message": "Successfully created a Property!",
    "data": {
        "OrgId": "{{org}}",
        "PropId": "{{prop_id}}",
        "Name": "Test Property 2",
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
        "Status": "Active"
    }
}
```


***Status Code:*** 200

<br>



### 2. Create PropertyType


Op name:

> scgrids.createPropertyType

This creates a type of Property at the system level


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
| op | scgrids.createPropertyType | (Required) Operation Name |
| org | {{org}} | (Required) Organisation ID |
| pid | scnoop | (Required) Project ID is scnoop when it's not known |



***Body:***

```js        
{
    "Name": "Commercial Buildings",
    "TypeID": "COMMERCIAL_BUILDINGS"
}
```



***More example Requests/Responses:***


##### I. Example Request: Create PropertyType


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Authorization | {{access_token}} | (Required) The Login Access Token |
| x-sc-identity | external | (Required) |



***Query:***

| Key | Value | Description |
| --- | ------|-------------|
| op | scgrids.createPropertyType | (Required) Operation Name |
| org | {{org}} | (Required) Organisation ID |
| pid | scnoop | (Required) Project ID is scnoop when it's not known |



***Body:***

```js        
{
    "Name": "Commercial Buildings",
    "TypeID": "COMMERCIAL_BUILDINGS"
}
```



##### I. Example Response: Create PropertyType
```js
{
    "status": 201,
    "message": "Success",
    "data": {
        "Name": "Commercial Buildings",
        "TypeID": "COMMERCIAL_BUILDINGS"
    }
}
```


***Status Code:*** 201

<br>



### 3. Get Property


Op name:

> scgrids.readProperty 

This gets a Property by ID


***Endpoint:***

```bash
Method: POST
Type: 
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
| op | scgrids.readProperty | (Required) Operation Name |
| org | {{org}} | (Required) Organisation ID |
| pid | scnoop | (Required) Project ID is scnoop when it's not known |
| propid | {{propid}} | (Optional) Property ID |



***More example Requests/Responses:***


##### I. Example Request: Get Property


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Authorization | eyJraWQiOiJLWWpCblh0WU1ZRWRLVUZ5Y3c2K2pIZUR5cG1GZ290V0kyUUFQb1RLcUZJPSIsImFsZyI6IlJTMjU2In0.eyJzdWIiOiJjZDhiMzVlNC0wYzcyLTQxNjgtYjZjYi03MjEwYmU2Yzg5ZWMiLCJldmVudF9pZCI6IjY1YjQ4NWNlLTJmMWUtNDA5MS1iOTM0LTVhMjM3ZjkyMDUwZSIsInRva2VuX3VzZSI6ImFjY2VzcyIsInNjb3BlIjoiYXdzLmNvZ25pdG8uc2lnbmluLnVzZXIuYWRtaW4iLCJhdXRoX3RpbWUiOjE2MDg2NDUyNjQsImlzcyI6Imh0dHBzOlwvXC9jb2duaXRvLWlkcC5hcC1zb3V0aGVhc3QtMS5hbWF6b25hd3MuY29tXC9hcC1zb3V0aGVhc3QtMV9xa0xjbXpFVmEiLCJleHAiOjE2MDg2NDg4NjQsImlhdCI6MTYwODY0NTI2NCwianRpIjoiMWNmNjg1ODMtNTJjYi00N2NiLWI4MDYtZDJjY2IzNTc5OTVlIiwiY2xpZW50X2lkIjoiMnA3ZmYxZDkwcnF0Zml1NHEyb21tZ2JvZTMiLCJ1c2VybmFtZSI6InNjX2tpcmFuIn0.ip1o8f_JdhWGuMVECTtWvk9FtzMY3fJadoNIAPVhzJdIuq3tPVGObyLH4wWGt4vjk3Hqb-xP7PQtfH3yNtVfjIB__VBX2NNCXvazflp5XahRwB6crd50cd88tyGkllYdtxR6BIqQ6TXXQxQJ9npBA59A8TaX7kI4udPfVgesyXhF23ih1tKBGJKy-AeFiaezRw96WWyQ8WQh7HBd7TgBQosCJXzJUZ9_wFzZI3ZjT-Y_23QI7giIlQJ9z0yy2fLYYzfjIuZlX78XdHd4OBp1HAqIKEXX1dZSs10u7HHoKDBvPPLHbusyw2AIIRyI2eJnnJKt9u8Tg0hFZkVKyljDcQ |  |
| x-sc-identity | external |  |



***Query:***

| Key | Value | Description |
| --- | ------|-------------|
| op | scgrids.readProperty | (Required) Operation Name |
| org | {{org}} | (Required) Organisation ID |
| pid | scnoop | (Required) Project ID is scnoop when it's not known |
| propid | {{prop_id}} | (Required) Property ID |



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



### 4. Get Property Collaboration


Op name:

> scgrids.readPropertyCollaboration

This gets a Property to Org Collaboration object


***Endpoint:***

```bash
Method: POST
Type: 
URL: /v1/actions
```


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Authorization | {{access_token}} | (Required) Login Access Token |
| x-sc-identity | external | (Required) |



***Query params:***

| Key | Value | Description |
| --- | ------|-------------|
| op | scgrids.readPropertyCollaboration | (Required) Operation Name |
| org | {{org}} | (Required) Organisation Name |
| pid | scnoop | (Required) Project ID is scnoop when it's not known |
| propid | {{prop_id}} | (Required) Property ID |



***More example Requests/Responses:***


##### I. Example Request: Get Property Collaboration



***Query:***

| Key | Value | Description |
| --- | ------|-------------|
| op | scgrids.readPropertyCollaboration | (Required) Operation name  |
| org | {{org}} | (Required) Organisation ID |
| pid | scnoop | (Required) Project ID |
| propid | {{prop_id}} | (Required) Property ID |



##### I. Example Response: Get Property Collaboration
```js
{
    "status": 200,
    "message": "Success",
    "data": {
        "ID": "SCOrgs#{{org}}",
        "ATTR": "attr#projects#{{org}}",
        "Modules": [
            "*"
        ],
        "Status": "Accepted",
        "OrgId": "{{org}}",
        "OwnerOrgId": "{{org}}",
        "PropId": "{{prop}}",
        "SUB1": "{{prop_id}}",
        "NS": "ORG_COLLABORATORS",
        "SRN": "srn:scorgs:SMARTCLEAN:IND:BLR:{{prop_id}}:ORG_COLLABORATORS:{{org}}/{{prop_id}}",
        "CreatedBy": "sc_kiran",
        "CreatedOn": 1613377288
    }
}
```


***Status Code:*** 200

<br>



### 5. List Buildings By Property


Op name: 

> scgrids.listBuildingsByProperty

This lists all the buildings under a given listBuildingsByProperty


***Endpoint:***

```bash
Method: POST
Type: 
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
| op | scgrids.listBuildingsByProperty | (Required) Operation Name |
| org | {{org}} | (Required) Organisation ID |
| pid | scnoop | (Required) Project ID is scnoop when it's not known |
| propid | {{prop_id}} | (Required) Property ID |



***More example Requests/Responses:***


##### I. Example Request: List Buildings By Property


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Authorization | {{access_token}} | (Required) The Login Access Token |
| x-sc-identity | external | (Required) |



***Query:***

| Key | Value | Description |
| --- | ------|-------------|
| op | scgrids.listBuildingsByProperty | (Required) Operation Name |
| org | {{org}} | (Required) Organisation ID |
| pid | scnoop | (Required) Project ID is scnoop when it's not known |
| propid | {{prop_id}} | (Required) Property ID |



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
                    "Default": "corporate@isikhlassuci.com,abhishek@smartclean.sg"
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

<br>



### 6. List Owner Org Properties


Op name:

> scgrids.listOwnerOrgProperties

This lists all the owner Org properties


***Endpoint:***

```bash
Method: POST
Type: RAW
URL: /v1/actions
```


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Authorization | {{access_token}} | (Required) Login Access Token |
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



***Query:***

| Key | Value | Description |
| --- | ------|-------------|
| op | scgrids.listOwnerOrgProperties |  |
| org | {{org}} |  |
| pid | scnoop |  |



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
            "OrgId": "SMARTCLEAN",
            "PropId": "",
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
            "OrgId": "SMARTCLEAN",
            "PropId": "TESTPROP_1",
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
            "OrgId": "SMARTCLEAN",
            "PropId": "TESTPROP_2",
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
            "OrgId": "SMARTCLEAN",
            "PropId": "Test",
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
            "OrgId": "SMARTCLEAN",
            "PropId": "d78a2135cf2c4491b5b6b6bb3f281d17",
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
            "Status": "Active",
            "TimeZone": "Asia/Kolkata"
        },
        {
            "OrgId": "SMARTCLEAN",
            "PropId": "fe01b1c8876f443da4bc3eb88ab2eae2",
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
        },
        {
            "OrgId": "SMARTCLEAN",
            "PropId": "ff47033487244e17a6d96df2a233a1a0",
            "Name": "Test Property 10",
            "Address": {
                "Street": "16th Cross, J P Nagar",
                "City": "Bangalore 3",
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

<br>



### 7. List Properties


Op name: 

> scgrids.listProperties

This lists all the Properties for an Organisation and can filter them by type of Property


***Endpoint:***

```bash
Method: POST
Type: 
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
| op | scgrids.listProperties | (Required) Operation name |
| org | {{org}} | (Required) Organisation ID |
| pid | scnoop | (Required) Project ID is scnoop when it's not known |



***More example Requests/Responses:***


##### I. Example Request: List Properties


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Authorization | {{access_token}} | (Required) The Login Access Token |
| x-sc-identity | external | (Required) |



***Query:***

| Key | Value | Description |
| --- | ------|-------------|
| op | scgrids.listProperties | (Required) Operation name |
| org | {{org}} | (Required) Organisation ID |
| pid | scnoop | (Required) Project ID is scnoop when it's not known |



##### I. Example Response: List Properties
```js
{
    "status": 200,
    "message": "Success",
    "data": [
        {
            "OrgId": "SMARTCLEAN",
            "PropId": "ca63da2eddf04277a1105fb9f2868545",
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
            "OrgId": "SMARTCLEAN",
            "PropId": "fe01b1c8876f443da4bc3eb88ab2eae2",
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

<br>



### 8. List PropertyTypes


Op name: 

> scgrids.listPropertyTypes 

This lists all the system level Property types


***Endpoint:***

```bash
Method: POST
Type: 
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
| op | scgrids.listPropertyTypes | (Required) Operation Name |
| org | {{org}} | (Required) Organisation ID |
| pid | scnoop | (Required) Project ID is scnoop when it's not known |



***More example Requests/Responses:***


##### I. Example Request: List PropertyTypes



***Query:***

| Key | Value | Description |
| --- | ------|-------------|
| op | scgrids.listPropertyTypes | (Required) Operation Name |
| org | {{org}} | (Required) Organisation ID |
| pid | scnoop | (Required) Project ID is scnoop when it's not known |



##### I. Example Response: List PropertyTypes
```js
{
    "status": 200,
    "message": "Success",
    "data": [
        {
            "Name": "Bank",
            "TypeID": "BANK"
        },
        {
            "Name": "Commercial Buildings",
            "TypeID": "COMMERCIAL_BUILDINGS"
        },
        {
            "Name": "Corporate Buildings",
            "TypeID": "CORPORATE_BUILDINGS"
        },
        {
            "Name": "Restaurants",
            "TypeID": "RESTAURANTS"
        },
        {
            "Name": "School",
            "TypeID": "SCHOOL"
        }
    ]
}
```


***Status Code:*** 200

<br>



### 9. Update Property


Op name: 

> scgrids.updateProperty

This updates a given Property's Name or Status


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


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Authorization | {{access_token}} | (Required) The Login Access Token |
| x-sc-identity | external | (Required) |



***Query:***

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



##### I. Example Response: scgrids.updateProperty
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
        "Status": "Pending"
    }
}
```


***Status Code:*** 200

<br>



## Property V2



### 1. Create Property V2



***Endpoint:***

```bash
Method: POST
Type: RAW
URL: /v2/actions
```


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Authorization | eyJraWQiOiJqS0R4QUhkQ0V1Y3pzWVBza1BrOUIwM1k0R21ENSs0Sk4xdzUrWG81RnJRPSIsImFsZyI6IlJTMjU2In0.eyJzdWIiOiIwMzFlNGYzOC1hMzlhLTRiYWEtYWU0NC1jMDllYThmZTM1MDciLCJldmVudF9pZCI6IjRlZGJjZTgzLWUxZjItNDQyNC05NWJhLWFmYzkyMWY4MDljNCIsInRva2VuX3VzZSI6ImFjY2VzcyIsInNjb3BlIjoiYXdzLmNvZ25pdG8uc2lnbmluLnVzZXIuYWRtaW4iLCJhdXRoX3RpbWUiOjE2MjAwMzc3ODcsImlzcyI6Imh0dHBzOlwvXC9jb2duaXRvLWlkcC5hcC1zb3V0aGVhc3QtMS5hbWF6b25hd3MuY29tXC9hcC1zb3V0aGVhc3QtMV95clUzUnJlcXYiLCJleHAiOjE2MjAwNDEzODcsImlhdCI6MTYyMDAzNzc4NywianRpIjoiNjc5MzJiZDUtZGYzMy00Y2RiLTkyYTktZDczMmExYWMxMWQ3IiwiY2xpZW50X2lkIjoiMWo3ajM5Y2lnMHBvYWh2NzFwbDhycWRzcGYiLCJ1c2VybmFtZSI6InNjX2tpcmFuIn0.cY5fJAhltz2yqPA6NTw9nRR8bxAobG9xj3UrxvniwWQGVXopETXNn-M8kUqmShmy-kqX0b-hR0zE1_ozDsfFDKgwpViZHbZuhlTUrpdVUHeCfuHWzBZawUBrjrFnxPFW5FImqn5oZuqiAYp8v9TPbMjj3Vt4Ld0kn3hgNw0-jo0HTsN7Qe0OYqmw_fDU8Txw0BXZKmuvbWxvdGoLpoCooIrdEJR83EWWAXdOELIKGuvXDUZ29gPiyVx0jWdSQmlRWFGMgaCbFeze0jWHNxAnCKtJSNqaF_ZGqb9AiqO6BQIx5p-xcJHo-JaBnkgP8GK3WZktzJOIHP7fIHuN8gnxAg |  |



***Query params:***

| Key | Value | Description |
| --- | ------|-------------|
| op | scgrids.createPropertyV2 | (Required) Operation Name |
| org | {{org}} |  |
| pid | scnoop |  |
| propid |  |  |



***Body:***

```js        
{
    "Name": "Property V2", 
    "TypeID": "BANK",
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
    "PlanType": "FREEMIUM",
    "TimeZone": "Asia/Kolkata",
    "Country": "India",
    "CountryLocale": "BLR"
}
```



### 2. Get Subscription Plan



***Endpoint:***

```bash
Method: GET
Type: 
URL: localhost:8083/unauth/getSubscriptionPlan
```



***Query params:***

| Key | Value | Description |
| --- | ------|-------------|
| planType | ENTERPRISE |  |



### 3. Get Subscription Plan for a Property



***Endpoint:***

```bash
Method: POST
Type: 
URL: /v2/actions
```



***Query params:***

| Key | Value | Description |
| --- | ------|-------------|
| op | scgrids.readPropertySubscription |  |
| org | {{org}} |  |
| pid | scnoop |  |
| propid | TESTPROP_2 |  |



## Zone



### 1. Create Zone


Op name: 

> scgrids.createZone

This creates a Zone object for a given Level for a Building


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


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Authorization | {{access_token}} | (Required) The Login Access Token |
| x-sc-identity | external | (Required) |



***Query:***

| Key | Value | Description |
| --- | ------|-------------|
| op | scgrids.createZone | (Required) Operation Name |
| org | {{org}} | (Required) Organisation ID |
| pid | {{pid}} | (Required) Project ID |
| propid | {{prop_id}} | (Required) Ptoperty ID |



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

<br>



### 2. Create Zone Asset


Op name:

> scgrids.createZoneUnit

This creates a Zone Unit/Asset like door or window


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
| op | scgrids.createZoneAsset | (Required) Operation Name |
| org | {{org}} | (Required) Organisation ID |
| pid | {{pid}} | (Required) Project ID |



***Body:***

```js        
{
    "Name": "Door/Opening",
    "UnitID": "DOOR/CLOSING",
    "ImageURL": "https://dummyimage.com/5:5x250",
    "ZoneCategoryID": "CONFERENCE_ROOMS"
}
```



***More example Requests/Responses:***


##### I. Example Request: Create Zone Asset


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Authorization | eyJraWQiOiJLWWpCblh0WU1ZRWRLVUZ5Y3c2K2pIZUR5cG1GZ290V0kyUUFQb1RLcUZJPSIsImFsZyI6IlJTMjU2In0.eyJzdWIiOiJjZDhiMzVlNC0wYzcyLTQxNjgtYjZjYi03MjEwYmU2Yzg5ZWMiLCJldmVudF9pZCI6ImE0MjBhM2YyLTA5MjEtNGZmMS1iMWYyLTU4ZjEwMWVkNzUxYyIsInRva2VuX3VzZSI6ImFjY2VzcyIsInNjb3BlIjoiYXdzLmNvZ25pdG8uc2lnbmluLnVzZXIuYWRtaW4iLCJhdXRoX3RpbWUiOjE2MDc2Njc3MjIsImlzcyI6Imh0dHBzOlwvXC9jb2duaXRvLWlkcC5hcC1zb3V0aGVhc3QtMS5hbWF6b25hd3MuY29tXC9hcC1zb3V0aGVhc3QtMV9xa0xjbXpFVmEiLCJleHAiOjE2MDc2NzEzMjIsImlhdCI6MTYwNzY2NzcyMiwianRpIjoiNGQ2MjJiYTctZDljMi00OTg2LWFjZDktZDBjM2I0NzNkOTVmIiwiY2xpZW50X2lkIjoiMnA3ZmYxZDkwcnF0Zml1NHEyb21tZ2JvZTMiLCJ1c2VybmFtZSI6InNjX2tpcmFuIn0.faHhG80tZkk884exBLhufj1-nqli0p7VykEfgpWqANZMVUDmESF7CtYkVj3hPwkPXBY9Xy6YVeL8m71e3sx8zVUbOvRR8tpL5a_QOu5JzAgdsusZ3YCVoxsawkuwMHh-TBo-xVxAXYWw4fna7lDoluqhtUFefbZieMAvFklkVutfp1bczc9X-HEIigKXW8Mp_M6r4lpa_5RnxwRZnH5zhCIDhqQ2dkhKWC-iVNGzTYoBBKnhMUuGw54t_tJeEOmK4sw_IlxpQ2XrMhE_2hOmxPSwwohf8SX8qBrqaIuYWlvntba6NKRc5OB5myXMFspiiGSo12oUqCrSty5VLFxPyg |  |
| Authorization | {{access_token}} | (Required) The Login Access Token |
| x-sc-identity | external | (Required) |



***Query:***

| Key | Value | Description |
| --- | ------|-------------|
| op | scgrids.createZoneUnit | (Required) Operation Name |
| org | {{org}} | (Required) Organisation ID |
| pid | {{pid}} | (Required) The Project ID |



***Body:***

```js        
{
    "Name": "Door/Opening",
    "UnitID": "DOOR/OPENING",
    "ImageURL": "https://dummyimage.com/5:5x250",
    "ZoneCategoryID": "CONFERENCE_ROOMS"
}
```



##### I. Example Response: Create Zone Asset
```js
{
    "status": 201,
    "message": "Success",
    "data": {
        "Name": "Door/Opening",
        "ImageURL": "https://dummyimage.com/5:5x250",
        "ZoneCategoryID": "CONFERENCE_ROOMS",
        "UnitID": "DOOR/OPENING"
    }
}
```


***Status Code:*** 201

<br>



### 3. Create Zone Asset For Building


Op name:

> scgrids.createZoneUnitForBuilding

This creates a Zone Unit/Asset for only a given Building


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
| op | scgrids.createZoneUnitForBuilding | (Required) Operation Name |
| org | {{org}} | (Required) Organisation ID |
| pid | {{pid}} | (Required) Project ID |



***Body:***

```js        
{
    "Name": "New 4",
    "UnitID": "NEW_4",
    "ImageURL": "https://dummyimage.com/5:5x250",
    "ZoneCategoryID": "CONFERENCE_ROOMS"
}
```



***More example Requests/Responses:***


##### I. Example Request: Create Zone Asset For Building


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Authorization | {{access_token}} | (Required) The Login Access Token |
| x-sc-identity | external | (Required) |



***Query:***

| Key | Value | Description |
| --- | ------|-------------|
| op | scgrids.createZoneUnitForBuilding | (Required) Operation Name |
| org | {{org}} | (Required) Organisation ID |
| pid | {{pid}} | (Required) The Project ID |



***Body:***

```js        
{
    "Name": "New 4",
    "UnitID": "NEW_4",
    "ImageURL": "https://dummyimage.com/5:5x250",
    "ZoneCategoryID": "CONFERENCE_ROOMS"
}
```



##### I. Example Response: Create Zone Asset For Building
```js
{
    "status": 201,
    "message": "Success",
    "data": {
        "Name": "New",
        "ImageURL": "https://dummyimage.com/5:5x250",
        "ZoneCategoryID": "CONFERENCE_ROOMS",
        "UnitID": "NEW"
    }
}
```


***Status Code:*** 201

<br>



### 4. Create Zone Category


Op name: 

> scgrids.createZoneCategory

This creates a new Zone category at system level


***Endpoint:***

```bash
Method: POST
Type: RAW
URL: /v1/actions
```


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Authorization | {{access_token}} | (Required) Login Access Token |
| x-sc-identity | external | (Required) |



***Query params:***

| Key | Value | Description |
| --- | ------|-------------|
| op | scgrids.createZoneCategory | (Required) Operation Name |
| org | {{org}} | (Required) Organisation ID |
| pid | scnoop | (Required) Project ID |



***Body:***

```js        
{
    "Name": "Labs_2",
    "CategoryID": "LABS_2",
    "PropertyTypeID": "SCHOOL"
}
```



***More example Requests/Responses:***


##### I. Example Request: Create Zone Category


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Authorization | eyJraWQiOiJLWWpCblh0WU1ZRWRLVUZ5Y3c2K2pIZUR5cG1GZ290V0kyUUFQb1RLcUZJPSIsImFsZyI6IlJTMjU2In0.eyJzdWIiOiJjZDhiMzVlNC0wYzcyLTQxNjgtYjZjYi03MjEwYmU2Yzg5ZWMiLCJldmVudF9pZCI6ImE0MjBhM2YyLTA5MjEtNGZmMS1iMWYyLTU4ZjEwMWVkNzUxYyIsInRva2VuX3VzZSI6ImFjY2VzcyIsInNjb3BlIjoiYXdzLmNvZ25pdG8uc2lnbmluLnVzZXIuYWRtaW4iLCJhdXRoX3RpbWUiOjE2MDc2Njc3MjIsImlzcyI6Imh0dHBzOlwvXC9jb2duaXRvLWlkcC5hcC1zb3V0aGVhc3QtMS5hbWF6b25hd3MuY29tXC9hcC1zb3V0aGVhc3QtMV9xa0xjbXpFVmEiLCJleHAiOjE2MDc2NzEzMjIsImlhdCI6MTYwNzY2NzcyMiwianRpIjoiNGQ2MjJiYTctZDljMi00OTg2LWFjZDktZDBjM2I0NzNkOTVmIiwiY2xpZW50X2lkIjoiMnA3ZmYxZDkwcnF0Zml1NHEyb21tZ2JvZTMiLCJ1c2VybmFtZSI6InNjX2tpcmFuIn0.faHhG80tZkk884exBLhufj1-nqli0p7VykEfgpWqANZMVUDmESF7CtYkVj3hPwkPXBY9Xy6YVeL8m71e3sx8zVUbOvRR8tpL5a_QOu5JzAgdsusZ3YCVoxsawkuwMHh-TBo-xVxAXYWw4fna7lDoluqhtUFefbZieMAvFklkVutfp1bczc9X-HEIigKXW8Mp_M6r4lpa_5RnxwRZnH5zhCIDhqQ2dkhKWC-iVNGzTYoBBKnhMUuGw54t_tJeEOmK4sw_IlxpQ2XrMhE_2hOmxPSwwohf8SX8qBrqaIuYWlvntba6NKRc5OB5myXMFspiiGSo12oUqCrSty5VLFxPyg |  |



***Query:***

| Key | Value | Description |
| --- | ------|-------------|
| op | scgrids.createZoneCategory |  |
| org | {{org}} |  |
| pid | {{pid}} |  |



***Body:***

```js        
{
    "Name": "Labs",
    "CategoryID": "LABS",
    "PropertyTypeID": "SCHOOL"
}
```



##### I. Example Response: Create Zone Category
```js
{
    "status": 201,
    "message": "Success",
    "data": {
        "Name": "Labs",
        "PropertyTypeID": "SCHOOL",
        "CategoryID": "LABS"
    }
}
```


***Status Code:*** 201

<br>



### 5. Create Zone Category For Building


Op name: 

>scgrids.createZoneCategoryForBuilding

This creates a new Zone category for only a given Building


***Endpoint:***

```bash
Method: POST
Type: RAW
URL: /v1/actions
```


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Authorization | {{access_token}} | (Required) Login Access Token |
| x-sc-identity | external | (Required) |



***Query params:***

| Key | Value | Description |
| --- | ------|-------------|
| op | scgrids.createZoneCategoryForBuilding | (Required) Operation Name |
| org | {{org}} | (Required) Organisation ID |
| pid | {{pid}} | (Required) Project ID |



***Body:***

```js        
{
    "Name": "New 2",
    "CategoryID": "NEW_2",
    "PropertyTypeID": "SCHOOL"
}
```



***More example Requests/Responses:***


##### I. Example Request: Create Zone Category For Building


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Authorization | eyJraWQiOiJLWWpCblh0WU1ZRWRLVUZ5Y3c2K2pIZUR5cG1GZ290V0kyUUFQb1RLcUZJPSIsImFsZyI6IlJTMjU2In0.eyJzdWIiOiJjZDhiMzVlNC0wYzcyLTQxNjgtYjZjYi03MjEwYmU2Yzg5ZWMiLCJldmVudF9pZCI6IjU0NGI2N2VlLWYyOTMtNGI0ZS05NTRhLTAwMjkxYmM5NTc3YiIsInRva2VuX3VzZSI6ImFjY2VzcyIsInNjb3BlIjoiYXdzLmNvZ25pdG8uc2lnbmluLnVzZXIuYWRtaW4iLCJhdXRoX3RpbWUiOjE2MDk4NDUyNjEsImlzcyI6Imh0dHBzOlwvXC9jb2duaXRvLWlkcC5hcC1zb3V0aGVhc3QtMS5hbWF6b25hd3MuY29tXC9hcC1zb3V0aGVhc3QtMV9xa0xjbXpFVmEiLCJleHAiOjE2MDk4NDg4NjEsImlhdCI6MTYwOTg0NTI2MSwianRpIjoiZjc4OGRiYTktZDAyMC00ZWI3LThiNzUtZDI2OGQ4MDJlMGY2IiwiY2xpZW50X2lkIjoiMnA3ZmYxZDkwcnF0Zml1NHEyb21tZ2JvZTMiLCJ1c2VybmFtZSI6InNjX2tpcmFuIn0.QYT-Lr-Uo9i5AgVI_4d-711P_WEgq2njpKhoFRhOkF_wKttGaDB2tlJ0fMf2-8jBbTHNm42cNRKVJcwmLzuZeUEaiSn_pktxiUXIqXww5oWOJDN5IQc4WUm3ejRfTFDXTH0-GoKUOa_vyEhooQ659sJb1O1sPWXXmYump7ktaReMS2oCdcXqo5ChfwGy5d4WAuePTdWB16HpkIi96OZYT9_Nkp5uPDLjqidSq3Awpfr1aMEVwRPnBVgQRP9S72c6j8cVDjgbj3tc2yhs8T-0GF52A7gsMc8LE__2GUpLVs3mmSfYfbjiKahxOXH7_Sx-CbO-u__KtJPupAcRFPBTYQ | (Required) The Login Access Token |
| x-sc-identity | external | (Required) |



***Query:***

| Key | Value | Description |
| --- | ------|-------------|
| op | scgrids.createZoneCategoryForBuilding | (Required) Operation Name |
| org | {{org}} | (Required) Organisation ID |
| pid | {{pid}} | (Required) The Project ID |



***Body:***

```js        
{
    "Name": "New 3",
    "CategoryID": "NEW_",
    "PropertyTypeID": "CORPORATE_BUILDINGS"
}
```



##### I. Example Response: Create Zone Category For Building
```js
{
    "status": 201,
    "message": "Success",
    "data": {
        "Name": "New 3",
        "PropertyTypeID": "CORPORATE_BUILDINGS",
        "CategoryID": "NEW_"
    }
}
```


***Status Code:*** 201

<br>



### 6. Delete Zone


Op name:

> scgrids.deleteZone

This delete a given Zone


***Endpoint:***

```bash
Method: POST
Type: RAW
URL: localhost:8083/v1/actions
```


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Authorization | {{access_token}} | (Required) The Login Acces Token |
| x-sc-identity | external | (Required) |



***Query params:***

| Key | Value | Description |
| --- | ------|-------------|
| op | scgrids.deleteZone | (Required) Operation Name |
| org | {{org}} | (Required) Organisation ID |
| pid | {{pid}} | (Required) Project ID |



***Body:***

```js        
{
    "InsID": "{{insid}}"
}
```



***More example Requests/Responses:***


##### I. Example Request: Delete Zone


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Authorization | {{access_token}} | (Required) The Login Acces Token |
| x-sc-identity | external | (Required) |



***Query:***

| Key | Value | Description |
| --- | ------|-------------|
| op | scgrids.deleteZone | (Required) Operation Name |
| org | {{org}} | (Required) Organisation ID |
| pid | {{pid}} | (Required) The Project ID |



***Body:***

```js        
{
    "InsID": "{{insid}}"
}
```



##### I. Example Response: Delete Zone
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
            "PID": "{{pid}}",
            "CreatedOn": 1609928625
        },
        {
            "InsID": "{{insid}}",
            "LID": "{{lid}}",
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
                    "windows",
                    "stairs",
                    "railings"
                ]
            },
            "Status": "active",
            "OperatingHours": {
                "0": null,
                "1": null,
                "2": null,
                "3": null,
                "4": null,
                "5": null,
                "6": null
            },
            "PID": "{{pid}}",
            "CreatedOn": 1609928625
        }
    ]
}
```


***Status Code:*** 0

<br>



### 7. Get Zone


Op name: 

> scgrids.readZone

This gets the Zone given by it's ID for a Building


***Endpoint:***

```bash
Method: POST
Type: RAW
URL: /v1/actions
```


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Authorization | {{access_token}} | (Required) Login Access Token |
| x-sc-identity | external | (Required) |



***Query params:***

| Key | Value | Description |
| --- | ------|-------------|
| op | scgrids.readZone | (Required) Operation Name |
| org | {{org}} | (Required) Organisation ID |
| pid | {{pid}} | (Required) Project ID |



***Body:***

```js        
{
    "InsID": "{{insid}}"
}

```



***More example Requests/Responses:***


##### I. Example Request: Get Zone


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Authorization | {{access_token}} | (Required) The Login Access Token |
| x-sc-identity | external | (Required) |



***Query:***

| Key | Value | Description |
| --- | ------|-------------|
| op | scgrids.readZone | (Required) Operation Name |
| org | {{org}} | (Required) Organisation ID |
| pid | {{pid}} | (Required) The Project ID |



***Body:***

```js        
{
    "InsID": "{{insid}}"
}

```



##### I. Example Response: Get Zone
```js
{
    "status": 200,
    "message": "Success",
    "data": {
        "InsID": "{{insid}}",
        "LID": "{{lid}}",
        "BeaconID": "test",
        "ZoneCategoryID": "",
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
}
```


***Status Code:*** 200

<br>



### 8. List Zone Asset By Zone Category


Op name: 

> scgrids.listZoneUnitsByZoneCategory

This lists all the stayet level Zone Units/Assets


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
| op | scgrids.listZoneAssetsByZoneCategory | (Required) Operation Name |
| org | {{org}} | (Required) Organisation ID |
| pid | scnoop | (Required) Project ID |



***Body:***

```js        
{
    "ZoneCategoryID": "CONFERENCE_ROOMS"
}
```



***More example Requests/Responses:***


##### I. Example Request: List Zone Units By Zone Category


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Authorization | {{access_token}} | (Required) The Login Access Token |
| x-sc-identity | external | (Required) |



***Query:***

| Key | Value | Description |
| --- | ------|-------------|
| op | scgrids.listZoneUnitsByZoneCategory | (Required) Operation Name |
| org | {{org}} | (Required) Organisation ID |
| pid | scnoop | (Required) The Project ID |



***Body:***

```js        
{
    "ZoneCategoryID": "CONFERENCE_ROOMS"
}
```



##### I. Example Response: List Zone Units By Zone Category
```js
{
    "status": 200,
    "message": "Success",
    "data": [
        {
            "Name": "Door/Opening",
            "ImageURL": "https://dummyimage.com/5:5x250",
            "ZoneCategoryID": "CONFERENCE_ROOMS",
            "UnitID": "DOOR/OPENING"
        },
        {
            "Name": "Windows",
            "ImageURL": "https://dummyimage.com/5:5x250",
            "ZoneCategoryID": "CONFERENCE_ROOMS",
            "UnitID": "WINDOWS"
        }
    ]
}
```


***Status Code:*** 200

<br>



### 9. List Zone Categories


Op name: 

> scgrids.listZoneCategories

This lists all the system level Zone categories for a given Property type


***Endpoint:***

```bash
Method: POST
Type: RAW
URL: /v1/actions
```


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Authorization | {{access_token}} | (Required) Login Access Token |
| x-sc-identity | external | (Required) |



***Query params:***

| Key | Value | Description |
| --- | ------|-------------|
| op | scgrids.listZoneCategories | (Required) Operation Name |
| org | {{org}} | (Required) Organisation ID |
| pid | scnoop | (Required) Project ID is scnoop when it's not known |



***Body:***

```js        
{
    "PropertyTypeID": "{{property_type}}"
}
```



***More example Requests/Responses:***


##### I. Example Request: List Zone Categories


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Authorization | {{access_token}} | (Required) THe Login Access Token |
| x-sc-identity | external | (Required) |



***Query:***

| Key | Value | Description |
| --- | ------|-------------|
| op | scgrids.listZoneCategories | (Required) Operation Name |
| org | {{org}} | (Required) Organisation ID |
| pid | scnoop | (Required) Project ID is scnoop when it's not known |



***Body:***

```js        
{
    "PropertyTypeID": "{{property_type}}"
}
```



##### I. Example Response: List Zone Categories
```js
{
    "status": 200,
    "message": "Success",
    "data": [
        {
            "Name": "Auditoriums/Theaters",
            "PropertyTypeID": "SCHOOL",
            "CategoryID": "AUDITORIUMS/THEATERS"
        },
        {
            "Name": "Classrooms",
            "PropertyTypeID": "SCHOOL",
            "CategoryID": "CLASSROOMS"
        },
        {
            "Name": "Labs",
            "PropertyTypeID": "SCHOOL",
            "CategoryID": "LABS"
        },
        {
            "Name": "Swimming Pools",
            "PropertyTypeID": "SCHOOL",
            "CategoryID": "SWIMMING_POOLS"
        }
    ]
}
```


***Status Code:*** 200

<br>



### 10. List Zone Categories By Building


Op name: 

> scgrids.listZoneCategoriesByBuilding

This gets all the Building level Zone categories


***Endpoint:***

```bash
Method: POST
Type: 
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
| op | scgrids.listZoneCategoriesByBuilding | (Required) Operation Name |
| org | {{org}} | (Required) Organisation ID |
| pid | {{pid}} | (Required) Project ID |



***More example Requests/Responses:***


##### I. Example Request: List Zone Categories By Building


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Authorization | {{access_token}} | (Required) The Login Access Token |
| x-sc-identity | external | (Required) |



***Query:***

| Key | Value | Description |
| --- | ------|-------------|
| op | scgrids.listZoneCategoriesByBuilding | (Required) Operation Name |
| org | {{org}} | (Required) Organisation ID |
| pid | {{pid}} | (Required) The Project ID |



##### I. Example Response: List Zone Categories By Building
```js
{
    "status": 200,
    "message": "Success",
    "data": [
        {
            "Name": "New",
            "PropertyTypeID": "SCHOOL",
            "CategoryID": "NEW"
        },
        {
            "Name": "New 2",
            "PropertyTypeID": "CORPORATE_BUILDINGS",
            "CategoryID": "NEW 2"
        },
        {
            "Name": "New 3",
            "PropertyTypeID": "CORPORATE_BUILDINGS",
            "CategoryID": "NEW_"
        }
    ]
}
```


***Status Code:*** 200

<br>



### 11. List Zone Units By Building


Op name:

> scgrids.listZoneUnitsByBuilding

This lists all the Building level Zone Units/Assets


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
| op | scgrids.listZoneUnitsByBuilding | (Required) Operation Name |
| org | {{org}} | (Required) Organisation ID |
| pid | {{pid}} | (Required) Project ID |



***Body:***

```js        
{
    "ZoneCategoryID": "CONFERENCE_ROOMS"
}
```



***More example Requests/Responses:***


##### I. Example Request: List Zone Units By Building


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Authorization | {{access_token}} | (Required) The Login Access Token |
| x-sc-identity | external | (Required) |



***Query:***

| Key | Value | Description |
| --- | ------|-------------|
| op | scgrids.listZoneUnitsByBuilding | (Required) Operation Name |
| org | {{org}} | (Required) Organisation ID |
| pid | {{pid}} | (Required) The Project ID |



##### I. Example Response: List Zone Units By Building
```js
{
    "status": 200,
    "message": "Success",
    "data": [
        {
            "Name": "New",
            "ImageURL": "https://dummyimage.com/5:5x250",
            "ZoneCategoryID": "CONFERENCE_ROOMS",
            "UnitID": "NEW"
        }
    ]
}
```


***Status Code:*** 200

<br>



### 12. List Zones By IDs


Op name: 

> scgrids.listZoneByIDs

 This gets the details of given zones


***Endpoint:***

```bash
Method: POST
Type: RAW
URL: /v1/actions
```


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Authorization | {{access_token}} | (Required) Login Access Token |
| x-sc-identity | external | (Required) |



***Query params:***

| Key | Value | Description |
| --- | ------|-------------|
| op | scgrids.listZonesByIDs | (Required) Operation Name |
| org | {{org}} | (Required) Organisation Name |
| pid | {{pid}} | (Required) Project ID |



***Body:***

```js        
{
    "InsIDs": ["{{insid}}", "{{insid2}}"]
}

```



***More example Requests/Responses:***


##### I. Example Request: List Zones By IDs



***Query:***

| Key | Value | Description |
| --- | ------|-------------|
| op | scgrids.listZonesByIDs |  |
| org | {{org}} |  |
| pid | {{pid}} |  |



***Body:***

```js        
{
    "InsIDs": ["{{insid}}", "{{insid2}}"]
}
```



##### I. Example Response: List Zones By IDs
```js
{
    "status": 200,
    "message": "Success",
    "data": [
        {
            "InsID": "{{indid}}",
            "LID": "{{lid}}",
            "BeaconID": "test",
            "ZoneCategoryID": "{{zone_category_id}}",
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
            "IsBuildingOperatingHours": true,
            "PID": "{{pid}}"
        },
        {
            "InsID": "{{insid2}}",
            "LID": "{{lid}}",
            "BeaconID": "test",
            "ZoneCategoryID": "LABS",
            "Name": "New test name",
            "Area": 6000,
            "FloorType": "Test floor",
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
            "Status": "ACTIVE",
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
            "IsBuildingOperatingHours": true,
            "PID": "{{pid}}"
        }
    ]
}
```


***Status Code:*** 200

<br>



### 13. ListZoneByZoneCategory


Op name:

> scgrids.listZonesByZoneCategory

This lists all the Zones for a given ZoneCategory


***Endpoint:***

```bash
Method: POST
Type: RAW
URL: /v1/actions
```


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Authorization | {{access_token}} | (Required) Login Access Token |
| x-sc-identity | external | (Required) |



***Query params:***

| Key | Value | Description |
| --- | ------|-------------|
| op | scgrids.listZonesByZoneCategory |  |
| org | {{org}} |  |
| pid | {{pid}} |  |



***Body:***

```js        
{
    "ZoneCategoryID": "{{zone_category_id}}",
    "ESK": "{{insid}}"
}
```



***More example Requests/Responses:***


##### I. Example Request: ListZoneByZoneCategory



***Query:***

| Key | Value | Description |
| --- | ------|-------------|
| op | scgrids.listZonesByZoneCategory |  |
| org | {{org}} |  |
| pid | {{pid}} |  |



***Body:***

```js        
{
    "ZoneCategoryID": "{{zone_category_id}}",
     "ExclusiveStartKey": "{{insid}}"
}
```



##### I. Example Response: ListZoneByZoneCategory
```js
{
    "status": 200,
    "message": "Success",
    "data": [
        {
            "InsID": "{{insid}}",
            "LID": "{{lid`}}",
            "ZoneCategoryID": "{{zone_category_id}}",
            "Name": "Zone 5",
            "Area": 3000,
            "FloorType": "hardwood",
            "Status": "active",
            "PID": "{{pid}}"
        },
        {
            "InsID": "{{insid}}",
            "LID": "{{lid`}}",
            "ZoneCategoryID": "{{zone_category_id}}",
            "Name": "Zone 5",
            "Area": 3000,
            "FloorType": "hardwood",
            "Status": "active",
            "PID": "{{pid}}"
        }
    ],
    "LastEvaluatedKey": {
       "ID": "SCProjects#{{pid}}",
        "ATTR": "attr#installations#info#{{pid}}#{{insid}}"
    }
}
```


***Status Code:*** 200

<br>



### 14. Update Zone


Op name: 

> scgrids.updateZone

This updates the Zone's details like Nema, Area ro Status


***Endpoint:***

```bash
Method: POST
Type: RAW
URL: /v1/actions
```


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Authorization | {{access_token}} | (Requied) The Login Access Token |
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


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Authorization | {{access_token}} | (Requied) The Login Access Token |
| x-sc-identity | external | (Required) |



***Query:***

| Key | Value | Description |
| --- | ------|-------------|
| op | scgrids.updateZone | (Required) Operation Name |
| org | {{org}} | (Required) Operation Name |
| pid | {{pid}} | (Required) The Project ID |



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
        "PID": "06ecedab24104909bde7497a397fd4c4",
        "InsID": "011bb7ac9425476db405190d69291cb8",
        "LID": "4df01e9e2fb548a0b7afe1892543b390",
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

<br>



## Ungrouped



### 1. Get Media Attachment


Op name:

> scgrids.getMediaAttachment

This gets the uploaded media attachment


***Endpoint:***

```bash
Method: POST
Type: RAW
URL: /v1/actions
```


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Authorization | {{access_token}} | (Rrequired) Login Access Token |
| x-sc-identity | external | (Required) |



***Query params:***

| Key | Value | Description |
| --- | ------|-------------|
| op | scgrids.getMediaAttachment | (Required) Operation Name |
| org | scnoop | (Required) Organisation Name |
| pid | scnoop | (Required) Project ID |



***Body:***

```js        
{
    "URI": "/matrixprojectassets/Test/incident/29d6be74ffbf49cfb4fe1e7b17355bd5/uploadedmedia.jpeg"

}
```



### 2. Get Thumbnails


Op name:

> scgrids.getThumbnails

This gets the given thumbnail


***Endpoint:***

```bash
Method: POST
Type: RAW
URL: /v1/actions
```


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Authorization | {{access_token}} | (Required) Login Access Token |
| x-sc-identity | external | (Required) |



***Query params:***

| Key | Value | Description |
| --- | ------|-------------|
| op | scgrids.getThumbnails | (Required) Operation Name |
| org | scnoop | (Required) Organisation Name |
| pid | scnoop | (Required) Project ID |



***Body:***

```js        
{
    "URIs": [
        "/matrixprojectassets/Test/incident/f4aba48eb81e4396a909d7ee1b8037d6/uploadedmedia.jpeg",
         "/matrixprojectassets/Test/incident/30ed99bb4d794051a9b54f4e2e7b4fda/uploadedmedia.jpeg"
    ]
}
```



### 3. Upload Media Attachment


Op name:

> scgrids.uploadMediaAttachment

This uploads media attachments for a given entity and of a given type


***Endpoint:***

```bash
Method: POST
Type: FORMDATA
URL: /v1/actions
```


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Authorization | {{access_token}} | (Required) Login Access Token |
| x-sc-identity | external | (Required) |



***Query params:***

| Key | Value | Description |
| --- | ------|-------------|
| op | scgrids.uploadMediaAttachment | (Required) Operation Name |
| org | scnoop | (Required) Organisation Name |
| pid | scnoop | (Required) Project ID |



***Body:***

| Key | Value | Description |
| --- | ------|-------------|
| Type | excel | (Required) Supports image/video |
| Entity | incident | (Required) Supports incident/audits |
| File |  | (Required) File to upload |



***Available Variables:***

| Key | Value | Type |
| --- | ------|-------------|
| host |  |  |



---
[Back to top](#smartclean--scgrids-v10)
> Made with &#9829; by [thedevsaddam](https://github.com/thedevsaddam) | Generated at: 2021-08-26 13:50:31 by [docgen](https://github.com/thedevsaddam/docgen)
