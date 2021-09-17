---
layout: default
title: Get Property Collaboration
parent: Grids Property
grand_parent: Grids
has_children: true
nav_order: 1
---


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