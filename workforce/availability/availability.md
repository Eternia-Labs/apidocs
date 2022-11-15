---
layout: default
title: Availability
parent: Workforce
grand_parent: SmartClean Matrix API Docs
has_children: true
nav_order: 2
---
# Availability
An availability object defines the availability of a given SeatId on a given day of the week. For any given SeatId there can be at max seven Availabilities defined, one for each day of the week. Within each Availability object time-slots defines the time range during which the SeatId is available, the name of the time-slot (eg: morning shift; evening shift etc.) and a boolean flag that highlights whether the time-slot spills over to the next day or not. A single availability object can't have more than two non-overlapping time-slots.

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

## Schema Details

### Availability

| Key       | Type   | Value                                                   |
|-----------|--------|---------------------------------------------------------|
| ID        | String | Partition key                                           |
| ATTR      | String | Sort key                                                |
| DayOfWeek | Number | nth day of week; 0 (Sunday) and 6 (Saturday)            |
| NS        | String | Name-Space                                              |
| SeatId    | String | SeatId this availability belongs to                     |
| SRN       | String | unique resource identifier                              |
| TimeSlots | List   | list of time-slots during which the seatId is available |

### Time-Slot

| Key       | Type    | Value                                    |
|-----------|---------|------------------------------------------|
| StartTime | number  | start time of this time-slot             |
| EndTime   | number  | end Tim elf this time-slot               |
| Name      | String  | name of this time-slot shift             |
| NextDay   | boolean | if this time-slot ends after mid-night ? |


# Availability Zones
Availability Zones defines all the zones belonging to different buildings where the given SeatId is available in. There will be only one Availability-Zone object defined for each SeatId.

A typical Availability-Zone object schema looks like this:-

```
{
 "ID": "SonyTestProperty",
 "ATTR": "attr#scpropteams#availabilityZones#SonyTestProperty#3b749a681d14446292b6c79b48403bbd_003",
 "NS": "SEAT_AVAILABILITY_ZONES",
 "SeatId": "3b749a681d14446292b6c79b48403bbd_003",
 "SRN": "srn:scteams:SONY:::SonyTestProperty:SEAT_AVAILABILITY_ZONES:3b749a681d14446292b6c79b48403bbd_003",
 "Zones": {
  "SONY": {
   "zoneid1": "zone122",
   "zoneid2": "zone2"
  },
  "TEST-PID": {
   "zoneid1": "zone1",
   "zoneid2": "zone2"
  }
 }
}
```

## Schema Details

| Key    | Type        | Value                                                             |
|--------|-------------|-------------------------------------------------------------------|
| ID     | String      | Partition key                                                     |
| ATTR   | String      | Sort key                                                          |
| NS     | String      | Name-Space                                                        |
| SeatId | String      | SeatId this availability-zones belongs to                         |
| SRN    | String      | unique resource identifier                                        |
| Zones  | Map of Maps | a map of <zone-id, zone-name> mapped to corresponding building id |