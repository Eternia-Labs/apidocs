---
layout: default
title: Incident
parent: Workforce
grand_parent: SmartClean Matrix API Docs
has_children: true
nav_order: 2
---
# Incident
An Incident refers to an unplanned event that doesn't originally belong to any Shift or Seat. Incidents can either be directly reported without being assigned to any ongoing Shift or available Seat or, they can be assigned to available Shift or Seat right at the time of being reported. An Incident is specific to a Zone and by definition, it contains only one workable-item or Task that needs to be done.

A typical Incident object schema looks like this:-

```
{
 "ID": "SONY",
 "ATTR": "attr#SONY#zoneid99#1656058344842880217",
 "AutoAssigned": 1,
 "By": "KG",
 "Delayed": 0,
 "End": 1656060144,
 "EscalationLevel": "L0",
 "EscalationPolicy": "default",
 "EscalationType": "unassigned",
 "Expiry": 1687594344,
 "Name": "Washroom essentials.",
 "NS": "TS",
 "Org": "HELIX",
 "Priority": "L",
 "PropID": "testpropertyid",
 "SeatId": "tbp",
 "ShiftId": "tbp",
 "SRN": "srn:sctasks:HELIX:::testpropertyid/SONY:TS:INCIDENT/1656058344842880217",
 "Start": 1656058344,
 "Status": "NOT_ASSIGNED",
 "Subject": "Issue raised",
 "taskCount": 1,
 "TaskId": "1656058344842880217",
 "Tasks": [
  {
   "Done": 0,
   "Name": "Wipe mirror.",
   "T": 0
  }
 ],
 "Type": "INCIDENT",
 "Zone": "zoneid99",
 "ZoneCatId": "someid",
 "ZoneName": "zonename",
 "EventSource": "testpropertyid#sensor"
}
```

## Schema details

### Incident

| Key              | Type    | Value                                                 |
|------------------|---------|-------------------------------------------------------|
| ID               | String  | partition key                                         |
| ATTR             | String  | sort key                                              |
| AutoAssigned     | boolean | if auto-assigned ?                                    |
| By               | number  | Incident reported by                                  |
| Delayed          | boolean | has Incident not been addressed past its Start time ? |
| End              | number  | Incident anticipated end time                         |
| EscalationLevel  | String  | current escalation level                              |
| EscalationPolicy | String  | escalation policy associated                          |
| EscalationType   | String  | escalation type currently violated                    |
| Expiry           | number  | object TTL in epoch seconds                           |
| Name             | String  | Incident name                                         |
| NS               | String  | Name-Space                                            |
| Org              | String  | Organisation name of the Property                     |
| Priority         | String  | Incident priority                                     |
| PropID           | String  | Property Id                                           |
| SeatId           | String  | SeatId this incident is assigned to                   |
| ShiftId          | String  | Shift this incident is assigned to                    |
| SRN              | String  | unique resource identifier                            |
| Start            | number  | anticipated Incident start-by time                    |
| Status           | String  | current Incident status                               |
| Subject          | String  | Subject of Incident                                   |
| taskCount        | number  | number of tasks included in the incident              |
| TaskId           | String  | unique id of this Incident                            |
| Tasks            | List    | list of Tasks included                                |
| Type             | String  | type of this Incident                                 |
| Zone             | String  | zone this incident belongs to                         |
| ZoneCatId        | String  | zone category id of the zone                          |
| ZoneName         | String  | zone name of the zone                                 |
| EventSource      | String  | source that raised the Incident                       |

### Task

| Key              | Type    | Value                                                 |
|------------------|---------|-------------------------------------------------------|
| Name             | String  | Task Name                                             |
| Done             | boolean | has the task been done ?                              |
| T                | number  | task value                                            |
| Attachments      | List    | list of file names                                    |