---
layout: default
title: Read Integration
parent: Attendance Third Party Integration
grand_parent: SmartClean Matrix API Docs
nav_order: 1
---

# **scattendance.readIntegration**

The op `scattendance.readIntegration` returns integration details for a given integration id created by a property.

## API details
### Input JSON

```json
{
    "IntegrationId": "<The integration id>"
}
```

### Output JSON

```json
{
    "Org": "<org>",
    "IntegrationId": "<The integration id>",
    "DefaultPID": "<The default building id to be used if _scnoop_ was sent as _pid_>",
    "ID": "<The property id>",
    "UserMap": {
        "SourceId": "SinkId"
    },
    "Description": "Attendance system integration example.",
    "Updated": 1631151741,
    "Created": 1631151741
}
```

The _UserMap_ must have been configured and maintained before the data for a given source seat id (_SourceId_) can be sent and processed.
