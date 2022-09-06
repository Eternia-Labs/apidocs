---
layout: default
title: TaskGroup
parent: Workforce
grand_parent: SmartClean Matrix API Docs
has_children: true
nav_order: 2
---

# TaskGroup

TaskGroup is a parent object that combines a set of work items or Tasks that are scheduled to be performed in a Shift. It can either be defined at the time of scheduling of the Shift or can be added to a scheduled Shift while updating it or can also be added to the Shift on an ad-hoc basis.

A typical TaskGroup object looks like this:-

```
{
 "ID": "SONY",
 "ATTR": "attr#SONY#3b749a681d14446292b6c79b48403bbd_002#25806c1c-23e4-43b7-b8a0-5cee8c720d12#1634828700000",
 "Delayed": 0,
 "End": 1634830500,
 "LocalTime": "20211021230500",
 "Name": "TG3- Clean Meeting Room",
 "NS": "TS",
 "Priority": "L",
 "PropID": "sony-test",
 "SeatId": "3b749a681d14446292b6c79b48403bbd_002",
 "ShiftId": "25806c1c-23e4-43b7-b8a0-5cee8c720d12",
 "SRN": "srn:sctasks:HELIX:::sony-test/SONY:TS:TASK/3b749a681d14446292b6c79b48403bbd_002/25806c1c-23e4-43b7-b8a0-5cee8c720d12/1634828700000",
 "Start": 1634828700,
 "Status": "UNPUBLISHED",
 "taskCount": 2,
 "TaskId": "1634828700000",
 "Tasks": [
  {
   "Done": 0,
   "Name": "Task 1- Clean floor",
   "T": 0
  },
  {
   "Done": 0,
   "Name": "Task 6- Clean doors",
   "T": 0
  }
 ],
 "TimeZone": "Asia/Singapore",
 "Type": "TASK",
 "Zone": "71d899661d5645acb0b8f8030e26fc35",
 "ZoneCatId": "MEETING_ROOMS",
 "ZoneName": "M Room 2",
 "EventSource": "sony-test#sensor"
}
```

## TaskGroup schema details

### TaskGroup

| Key              | Type    | Value                                                 |
|------------------|---------|-------------------------------------------------------|
| ID               | String  | partition key                                         |
| ATTR             | String  | sort key                                              |
| LocalTime        | String  | local time when TaskGroup should be addressed         |
| Delayed          | boolean | has Task not been addressed past its Start time ? |
| End              | number  | TG anticipated end time                         |
| Expiry           | number  | object TTL in epoch seconds                           |
| Name             | String  | TG name                                         |
| NS               | String  | Name-Space                                            |
| Priority         | String  | TG priority                                     |
| PropID           | String  | Property Id                                           |
| SeatId           | String  | SeatId this TG is assigned to                   |
| ShiftId          | String  | Shift this TG is part of                 |
| SRN              | String  | unique resource identifier                            |
| Start            | number  | anticipated TG start-by time                    |
| Status           | String  | current TG status                               |
| taskCount        | number  | number of tasks included in the TG              |
| TaskId           | String  | unique id of this TG                            |
| Tasks            | List    | list of Tasks included                                |
| Type             | String  | type of this TG                                 |
| TimeZone             | String  | time zone of the location                              |
| Zone             | String  | zone this TG belongs to                         |
| ZoneCatId        | String  | zone category id of the zone                          |
| ZoneName         | String  | zone name of the zone                                 |
| EventSource      | String  | source that raised the Incident                       |