---
layout: default
title: Building to Zone Map
parent: Grids Building
grand_parent: Grids
has_children: true
nav_order: 1
---


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
    "ESK": "{{ESK}}"
}
```