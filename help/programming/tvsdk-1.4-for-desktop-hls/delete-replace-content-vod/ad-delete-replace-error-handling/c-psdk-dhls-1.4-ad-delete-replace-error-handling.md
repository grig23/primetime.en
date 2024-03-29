---
description: TVSDK handles time range errors according to the specific problem, either merging or reordering the improperly defined time ranges.
title: Ad deletion and replacement error handling
exl-id: 86970989-82e0-4e6f-81fb-beee70870c69
---
# Ad deletion and replacement error handling {#ad-deletion-and-replacement-error-handling}

TVSDK handles time range errors according to the specific problem, either merging or reordering the improperly defined time ranges.

TVSDK deals with `timeRanges` errors by doing default merging and reordering. First, it sorts customer-defined time ranges by the *begin* time. Based on this sorting order, it then merges adjacent ranges, and joins them if there are subsets and intersections among the ranges.

TVSDK handles time-range errors as follows:

* Out of order - TVSDK reorders the time ranges. 
* Subset - TVSDK merges the time-range subsets. 
* Intersect - TVSDK merges the intersecting time ranges. 
* Replace ranges conflict - TVSDK chooses the replace duration from the earliest appearing `timeRange` in the conflicting group.

TVSDK handles signaling-mode conflicts as follows:

* If REPLACE ranges are defined, TVSDK automatically changes the signaling mode to CUSTOM_RANGE. 
* If DELETE ranges or MARK ranges are defined and the signaling mode is CUSTOM_RANGE, TVSDK deletes or marks these ranges. There is no ad insertion in this case. 
* If a DELETE range or a MARK range defines a replacement duration, TVSDK ignores this duration.

When the server does not return valid `AdBreaks`:

* TVSDK generates and processes a `NOPTimelineOperation` for the empty `AdBreak`. No ad plays.

## Time range error examples {#time-range-error-examples}

TVSDK responds to erroneous time range specifications by merging or replacing the time ranges as appropriate.

In the following example, four intersecting DELETE time ranges are defined. TVSDK merges the four time ranges into one, so that the actual delete range is from 0-50s. 

```
"time-ranges": {
    "type": "delete",
    "time-range-list": [ {
        "begin": 10000,
        "end": 35000
    }, {
        "begin": 20000,
        "end": 50000
    }, {
        "begin": 0,
        "end": 30000
    }, {
        "begin": 30000,
        "end": 40000
    } ]
}

```

In the following example, four REPLACE time ranges are defined with conflicting time ranges. In this case, TVSDK replaces 0-50s with 25s of ads. It goes with the first replacement duration in the sort order, because there are conflicts in subsequent ranges. 

```
"time-ranges": {
    "type": "replace",
    "time-range-list": [ {
        "begin": 10000,
        "end": 35000,
        "replace-duration": 15000
    }, {
        "begin": 20000,
        "end": 50000,
        "replace-duration": 20000
    }, {
        "begin": 0,
        "end": 30000,
        "replace-duration": 25000
    }, {
        "begin": 30000,
        "end": 40000,
        "replace-duration": 30000
    } ]
}

```
