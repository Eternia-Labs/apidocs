---
layout: default
title: TimeSheet
parent: Workforce
grand_parent: SmartClean Matrix API Docs
has_children: true
nav_order: 2
---

#TimeSheet
A timesheet is a record of the work effort put in by a User/Worker in a given Shift. It includes details about the clock-in/clock-out, breaks and their duration, actual start/end of the Shift, etc.

A typical TimeSheet object schema looks like this:-

```
{
 "ID": "SONY",
 "ATTR": "attr#SONY#3b749a681d14446292b6c79b48403bbd_002#59930f45-f3a8-4e52-afba-91e859068845",
 "ActualDurationInSeconds": 300,
 "AEnd": 1614673823,
 "ApprovedBy": "SC_MANGER_TEST",
 "ApprovedOn": 1639051660,
 "AStart": 1614673523,
 "Breaks": [
  {
   "ID": "1622189441000",
   "End": 1622189621,
   "Notes": "Afternoon lunch break.",
   "Start": 1622189441,
   "Type": "meal"
  }
 ],
 "Coordinates": {
  "ClockIn": {
   "Latitude": 3.165725,
   "Longitude": 101.646267
  },
  "ClockOut": {
   "Latitude": 3.165725,
   "Longitude": 101.646267
  }
 },
 "Duration": "PT5M",
 "Edited": 1,
 "End": 1645976000,
 "Expiry": 1666441400,
 "jobId": "tbp",
 "NS": "TS",
 "PropId": "sony-test",
 "RequestedOn": 1638442188,
 "RequestType": "TIMESHEET",
 "SeatId": "3b749a681d14446292b6c79b48403bbd_002",
 "ShiftId": "59930f45-f3a8-4e52-afba-91e859068845",
 "SRN": "srn:scshifts:HELIX:::sony-test/SONY:SHIFT_TS:ts/3b749a681d14446292b6c79b48403bbd_002/59930f45-f3a8-4e52-afba-91e859068845",
 "Start": 1645905400,
 "Status": "APPROVED",
 "Zones": {
  "71d899661d5645acb0b8f8030e26fc35": "M Room 2"
 }
}
```

## Schema Details

### TimeSheet

| Key       | Type   | Value                                                   |
|-----------|--------|---------------------------------------------------------|
| ID        | String | Partition key                                           |
| ATTR      | String | Sort key                                                |
| ActualDurationInSeconds | Long | Actual duration of Shift           |
| AEnd        | Long | actual shift end time                                             |
| ApprovedBy    | String | user name who approved the Shift                    |
| ApprovedOn       | Long | actual time in epoch seconds when TimeSheet was approved                              |
| AStart | Long   | actual start time of Shift |
| Breaks        | List | list of breaks availed during the Shift   |
| Coordinates      | Object | Object having clock-in/clock-out details of the Shift  |
| Duration | Long | scheduled Shift duration |
| Edited        | Boolean | boolean says if the TimeSheet has been edited or not |
| End    | Long | scheduled end time of shift      |
| Expiry       | Long | object ttl in the db  |
| jobId | String   | job id |
| NS        | String | name-space  |
| PropId      | String | property-id    |
| RequestedOn | Long | time in epoch seconds when the TimeSheet was raised or submitted |
| RequestType        | String | timesheet request type   |
| SeatId    | String | SeatId corresponding to the user   |
| ShiftId       | String | ShiftId of the shift  |
| SRN | String   | unique resource identifier |
| Start    | Long | scheduled start time of shift |
| Status       | String | timesheet status |
| Zones | Map   | map of zone-id/zoneName associated with the Shift |

### Break

| Key              | Type    | Value                                                 |
|------------------|---------|-------------------------------------------------------|
|ID|String|unique break identifier|
|End|Long|break end time|
|Notes|String|break info|
|Type|String|break type|
|Start|Long|break start time|

### Coordinates

| Key              | Type    | Value                                                 |
|------------------|---------|-------------------------------------------------------|
|ClockIn|Object|object defines latitude and longitude|
|ClockOut|Object|object defines latitude and longitude|