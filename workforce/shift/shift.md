---
layout: default
title: Shift
parent: Workforce
grand_parent: SmartClean Matrix API Docs
has_children: true
nav_order: 2
---

# Shift

A Shift object defines a Shift and all its aspects i.e: its time bounds, person assigned, building its associated to, zones that can report incidents and ad-hoc tasks to this shift, all the Tasks and work-items needed to be performed during the Shift, etc. 

A Shift object schema looks like this:-

```
{
 "ID": "SONY",
 "ATTR": "attr#SONY#3b749a681d14446292b6c79b48403bbd_007#1ef53f4f-09ad-4e5c-b5c8-bd354f735386",
 "ActualDurationInSeconds": 0,
 "AEnd": 0,
 "AStart": 0,
 "Breaks": [
  {
   "ID": "unplanned_0",
   "DurationInSeconds": 120,
   "IsPlannedBreak": 0,
   "Type": "meal_break"
  }
 ],
 "Coordinates": {
  "ClockIn": {
   "Latitude": -1,
   "Longitude": -1
  },
  "ClockOut": {
   "Latitude": -1,
   "Longitude": -1
  }
 },
 "Cost": {
  "U": "SGD",
  "V": 225
 },
 "CreatedBy": "system",
 "CreatedOn": 1659952287,
 "Delayed": 0,
 "Duration": "PT3H",
 "End": 1662292800,
 "Expiry": 1662541200,
 "jobId": "tbp",
 "LocalTime": "20220904170000",
 "ModifiedBy": "gaurav",
 "ModifiedOn": 1660834067,
 "NS": "SHIFT_TS",
 "PropID": "sony-test",
 "SeatId": "3b749a681d14446292b6c79b48403bbd_007",
 "ShiftDurationInSeconds": 10800,
 "ShiftId": "1ef53f4f-09ad-4e5c-b5c8-bd354f735386",
 "SRN": "srn:scshifts:HELIX:::sony-test/SONY:SHIFT_TS:ts/3b749a681d14446292b6c79b48403bbd_007/1ef53f4f-09ad-4e5c-b5c8-bd354f735386",
 "Start": 1662282000,
 "Status": "UNPUBLISHED",
 "TaskGroups": [
  "1662282000000",
  "1662283000000"
 ],
 "TaskGroupsCount": 2,
 "TimeZone": "Asia/Singapore",
 "Zones": {
  "71d899661d5645acb0b8f8030e26fc35": "M Room 2"
 }
}
```

## Schema details

### Shift

| Key              | Type    | Value                                                 |
|------------------|---------|-------------------------------------------------------|
|ID|String| Partition key|
|ATTR|String|sort key|
|ActualDurationInSeconds|number| actual duration of the shift (AEnd - AStart)|
|AEnd|number|actual time shift was ended in epoch seconds|
|AStart|number|actual time shift was started in epoch seconds|
|Breaks|List|list of breaks planned in the shift|
|Coordinates|Object|object defining location of Shift clock-in & clock-out|
|Cost|Object|object defines cost associated with the shift|
|CreatedBy|String|user or entity who created the Shift|
|CreatedOn|number|epoch time when the Shift was created|
|Delayed|boolean|has the Shift been delayed ?|
|Duration|String|shift duration|
|End|number|planned shift end time|
|Expiry|number|object TTL in epoch seconds|
|jobId|String|job identifier|
|LocalTime|String|local shift start time|
|ModifiedBy|String|user who updated the shift last|
|ModifiedOn|number|epoch time when shift was updated last|
|NS|String|Name-Space|
|PropID|String|property-id this shift belongs to|
|SeatId|String|seat assigned to this shift|
|ShiftDurationInSeconds|number|planned shift duration|
|ShiftId|String|Shift id|
|SRN|String|unique resource identifier|
|Start|number|planned shift start time in epoch seconds|
|Status|String|shift status|
|TaskGroups|List|TaskIds of task-groups included in this shift|
|TaskGroupsCount|number|number of task-groups included in the shift|
|TimeZone|String|timezone of the location where shift is planned|
|Zones|Map|map of ZoneId and ZoneName associated with the shift|


### Break

| Key              | Type    | Value                                                 |
|------------------|---------|-------------------------------------------------------|
|ID|String|unique break identifier|
|DurationInSeconds|number|break duration in seconds|
|IsPlannedBreak|boolean|is this a planned break|
|Type|String|break type|


### Coordinates

| Key              | Type    | Value                                                 |
|------------------|---------|-------------------------------------------------------|
|ClockIn|Object|object defines latitude and longitude|
|ClockOut|Object|object defines latitude and longitude|


### Cost

| Key              | Type    | Value                                                 |
|------------------|---------|-------------------------------------------------------|
|U|String|unit of cost|
|V|number|numeric value of cost|