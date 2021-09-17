---
layout: default
title: List Zones by IDs
parent: Grids Zone
grand_parent: Grids
has_children: true
nav_order: 1
---


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
        }
    ]
}
```


***Status Code:*** 200

<br>