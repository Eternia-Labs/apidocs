---
layout: default
title: Availability
parent: Workforce
grand_parent: SmartClean Matrix API Docs
has_children: true
nav_order: 2
---

An availability object defines the availability of a given SeatId on a given day of the week. For any given SeatId there can be at max seven Availabilities defined, one for each day of the week. Within each Availability object time-slots defines the time range during which the SeatId is available, the name of the time-slot (eg: morning shift; evening shift etc.) and a boolean flag that highlights whether the time-slot spills over to the next day or not. A single availability object can't have more than two time-slots.

A typical Availability object schema looks like this:-

```
{
 "ID": "SonyTestProperty",
 "ATTR": "attr#scpropteams#availability#SonyTestProperty#3b749a681d14446292b6c79b48403bbd_003#6",
 "DayOfWeek": 6,
 "NS": "SEAT_AVAILABILITY",
 "SeatId": "3b749a681d14446292b6c79b48403bbd_003",
 "SRN": "srn:scteams:SONY:::SonyTestProperty:SEAT_AVAILABILITY:3b749a681d14446292b6c79b48403bbd_003/6",
 "TimeSlots": [
  {
   "EndTime": 26000,
   "Name": "night shift",
   "NextDay": 1,
   "StartTime": 56000
  },
  {
   "EndTime": 33000,
   "Name": "morning shift",
   "NextDay": 0,
   "StartTime": 26000
  }
 ]
}
```