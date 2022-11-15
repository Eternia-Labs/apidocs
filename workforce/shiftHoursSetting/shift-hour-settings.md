---
layout: default
title: ShiftHourSetting
parent: Workforce
grand_parent: SmartClean Matrix API Docs
has_children: true
nav_order: 2
---

# ShiftHour Setting
ShiftHour object defines shifts for a given property within a span of 24 hours(not necessarily in the same day).  Shift hours are default shift definitions which are pre-configured for each day of the week(check operation: **scteams.createShiftDefinitionForProperty**). Each Shift hour object is defined independent of the other and hence their time span can overlap.

A ShiftHour object schema looks like this :-

```
{
 "ID": "SonyTestProperty",
 "ATTR": "attr#scpropteams#ShiftHour#SonyTestProperty",
 "NS": "SHIFT_HOURS",
 "ShiftHours": [
  {
   "ColorCode": "#fff123",
   "End": 12345,
   "NextDay": 1,
   "ShiftName": "Morning Shift",
   "Start": 23456
  },
  {
   "ColorCode": "#fff123",
   "End": 34456,
   "NextDay": 0,
   "ShiftName": "evening Shift",
   "Start": 23456
  }
 ],
 "SRN": "srn:scteams:SONY:::SonyTestProperty:SHIFT_HOURS:SonyTestProperty"
}
```

## Schema Details

|Key|Type|Value|
|---|---|---|
|ID|String|Partition Key|
|ATTR|String|Sort Key|
|NS|String|name space|
|ShiftHours|object|parent object|
|SRN|String|resource identifier|

### ShiftHour

|Key|Type|Value|
|---|---|---|
|ColorCode|String|hex color code of the shift|
|ShiftName|String|shift name|
|NextDay|boolean|whether shift spans across two days(starts before mid-night & ends after mid-night)|
|Start|Long|shift start time in epoch seconds|
|End|Long|shift end time in epoch seconds|