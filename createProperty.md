---
layout: default
title: Create Property
parent: Grids Property
grand_parent: Grids
has_children: true
nav_order: 1
---


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
    "Name": "Test Property", 
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
    "Name": "Test Property", 
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