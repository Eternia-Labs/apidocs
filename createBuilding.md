---
layout: default
title: Create Building
parent: Building
grand_parent: Grids
has_children: true
nav_order: 1
---


### 3. Create Building


Op name: 

> scgrids.createBuilding

This creates a Building object for a given Property


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
| op | scgrids.createBuilding | (Required) Operation Name |
| org | {{org}} | (Required) Organisation ID |
| pid | scnoop | (Required) Project ID is scnoop when it's not known |
| propid | {{prop_id}} | (Required) Property ID |



***Body:***

```js        
{
    "Name": "Test Building",
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
        "Default": "{{email}}"
    },
    "LevelsCount": 1,
    "TimeZone": "Asia/Hong_Kong",
    "PropID": "{{prop_id}}",
    "IsBeaconEnabled": false,
    "IsPropertyAddress": true,
    "Country": "{{country}}",
    "Area": 1200,
    "CountryLocale": "{{country_locale}}",
    "PID": "{{pid}}"
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
        "Default": "{{email}}"
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
                "Default": "{{email}}"
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


***Error codes:***

##### 400

##### Possible reasons:

###### 1. Missing op/org/pid/propid

###### 2. Invalid characters/improper input body

###### 3. Missing access_token in the header

###### 4. Missing Name/OperatingHours/LevelsCount/Country/CountryLocale in input body

###### 5. If the LevelsCount number is greater than 60

###### 6. If the building name is already taken under the given property

###### 7. If the system limit of buildings has reached for the given property


<br>