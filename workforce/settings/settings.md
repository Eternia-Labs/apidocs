---
layout: default
title: Settings
parent: Workforce
grand_parent: SmartClean Matrix API Docs
has_children: true
nav_order: 2
---

# Settings
Settings are a set of key value pairs that allow the user to define and set preferences, enable or disable features etc. These are system level settings specific for each version of the SAAS platform and are generally backward compatible.

Incident Settings are applicable to Incident object and provides controlling the life-cycle related aspects of Incident object and Schedule Settings are applicable to shift object and provides controlling aspects of scheduled Shift objects.

A typical Schedule settings object looks like this:-

```
{
 "ID": "SONY",
 "ATTR": "attr#schedule#SONY",
 "ScheduleSettings": {
  "ABSENT_SHIFT_THRESHOLD": {
   "Description": "Elapsed time from delayed status after which a shift will be considered absent.",
   "LongValue": 3600,
   "Type": "Long",
   "Unit": "seconds"
  },
  "ALLOW_EARLY_CHECKOUT": {
   "BooleanValue": 1,
   "Description": "Allow early checkout.",
   "Type": "Boolean"
  },
  "AUTO_CLOCKOUT": {
   "BooleanValue": 1,
   "Description": "Allow auto check out.",
   "Type": "Boolean"
  },
  "BUILDING_AVAILBILITY": {
   "Description": "Building availability.",
   "Type": "Boolean",
   "Value": "0"
  },
  "DELAYED_SHIFT_THRESHOLD": {
   "Description": "Time elapsed before marking shift as delayed.",
   "LongValue": 1800,
   "Type": "Long",
   "Unit": "seconds"
  },
  "DISTANCE_THRESHOLD_CHECKIN": {
   "Description": "How far a person can be from the coordinates of the building in metres when they check in or check out for shifts.",
   "LongValue": 1000,
   "Type": "Long",
   "Unit": "meters"
  },
  "END_SHIFT_OVERSHOOT": {
   "Description": "Time after which a shift will be automatically ended if not checked out.",
   "LastModifiedOn": 1656493826967,
   "LongValue": 4200,
   "Type": "Long",
   "Unit": "seconds"
  },
  "TIME_FOR_UNSCHEDULED_SHIFT": {
   "Description": "The default time to use for clocking out unscheduled shifts.",
   "LongValue": 28800,
   "Type": "Long",
   "Unit": "seconds"
  }
 }
}
```

A typical Incident settings object looks like this:-

```
{
 "ID": "SONY",
 "ATTR": "attr#incidents#SONY",
 "IncidentsSettings": {
  "ALLOW_DELETION_OPEN_INCIDENTS": {
   "BooleanValue": 1,
   "Description": "Set to true to allow deletion of OPEN Incidents.",
   "Type": "Boolean"
  },
  "ALLOW_DELETION_PUBLISHED_INCIDENTS": {
   "BooleanValue": 1,
   "Description": "Set to true to allow deletion of PUBLISHED Incidents.",
   "Type": "Boolean"
  },
  "ALLOW_INCIDENT_REASSIGNMENT": {
   "BooleanValue": 1,
   "Description": "Set to true to allow reassignment of PUBLISHED Incidents.",
   "Type": "Boolean"
  },
  "ALLOW_REASSIGNMENT_RESOLVED": {
   "BooleanValue": 0,
   "Description": "Set to true to allow reopening of COMPLETED Incidents.",
   "Type": "Boolean"
  },
  "ALLOW_REASSIGNMENT_UNRESOLVED": {
   "BooleanValue": 1,
   "Description": "Set to true to allow reopening of INCOMPLETE Incidents.",
   "Type": "Boolean"
  },
  "AUTO_ASSIGN_INCIDENTS": {
   "BooleanValue": 1,
   "Description": "If this setting is true, when an incident is raised for a zone, the system will try to auto assign the incident to an available shift and do a round robin balancing of number of incidents between such availabilities. Set this to false if you want all the allocated shifts for the zone to receive notification about an incident, followed by a single person's acknowledgement and incident resolution subsequently.",
   "Type": "Boolean"
  },
  "INCIDENT_HIGH_TIMEOUT": {
   "Description": "Allowed elapsed time in seconds from due time by which an incident must be acted on (started or completed) for high priority incidents.",
   "LongValue": 900,
   "Type": "Long",
   "Unit": "seconds"
  },
  "INCIDENT_LOW_TIMEOUT": {
   "Description": "Allowed elapsed time in seconds from due time by which an incident must be acted on (started or completed) for low priority incidents.",
   "LongValue": 3600,
   "Type": "Long",
   "Unit": "seconds"
  },
  "INCIDENT_MEDIUM_TIMEOUT": {
   "Description": "Allowed elapsed time in seconds from due time by which an incident must be acted on (started or completed) for medium priority incidents.",
   "LongValue": 1200,
   "Type": "Long",
   "Unit": "seconds"
  },
  "INCIDENT_NORMAL_TIMEOUT": {
   "Description": "Allowed elapsed time in seconds from due time by which an incident must be acted on (started or completed) for normal priority incidents.",
   "LongValue": 1800,
   "Type": "Long",
   "Unit": "seconds"
  },
  "MAX_INCIDENT_REASSIGN_COUNT": {
   "Description": "The maximum number of times an Incident can be reassigned.",
   "LongValue": 8,
   "Type": "Long",
   "Unit": "counts"
  },
  "REASSIGNMENT_RESOLVED_MAX": {
   "Description": "Maximum time duration after the Incident due time till the Completed Incident can be reopened.",
   "LongValue": 86400,
   "Type": "Long",
   "Unit": "seconds"
  },
  "REASSIGNMENT_UNRESOLVED_MAX": {
   "Description": "Maximum time duration after the Incident due time till the Incomplete Incident can be reopened.",
   "LongValue": 259200,
   "Type": "Long",
   "Unit": "seconds"
  },
  "TASK_CLOSURE_PIC_COMPULSORY": {
   "BooleanValue": 1,
   "Description": "If this is set to true, users must upload a picture before they can close the task.",
   "LastModifiedOn": 1656493692522,
   "Type": "Boolean"
  }
 }
}
```