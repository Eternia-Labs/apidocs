---
layout: default
title: Log Attendance Event
parent: Attendance Third Party Integration
grand_parent: SmartClean Matrix API Docs
nav_order: 2
---

# **scattendance.attendanceEvent**

The op `scattendance.attendanceEvent` logs an attendance event in the system.

## API details
### Input JSON

```javascript
{
    "IntegrationId": "<The integration id>",
    "Event": "CLOCK_IN",
    "Time": 1631349131,
    "ID": "<The source seat id>"
}
```

### Event
Event can be either of `CLOCK_IN` or `CLOCK_OUT`.

### Time
This is an optional key, if not provided, the system will use the current epoch time.

### ID
The unique identifier of the person in source system. Note that the appropriate mapping must have been performed in Matrix by pointing the source id to a valid _SeatId_.

### IntegrationId
The unique integration id created for the integration in context.

### Output JSON

```javascript
{
    "input": {
        <The input request sent>
    },
    "output": {
        "ID": "<Sink Seat Id>",
        "Event": "<The event recorded as CLOCK_IN or CLOCK_OUT from the request>",
        "Time": <The epoch time>,
        "IntegrationId": "<The integration id in context>",
        "PropId": "<The property id>",
        "Org": "<The org id>",
        "PID": "<The building id>",
        "SourceSeatId": "<The source unique identifier for the person>",
        "MatrixSeatId": "<Sink Seat Id>"
    },
    "status": "OK"
}
```

The _UserMap_ must have been configured and maintained before the data for a given source seat id (_SourceId_) can be sent and processed.
