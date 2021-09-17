---
layout: default
title: Update Level FloorPlan
parent: Grids Level
grand_parent: Grids
has_children: true
nav_order: 1
---


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