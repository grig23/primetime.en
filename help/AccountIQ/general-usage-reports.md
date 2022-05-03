---
title: General Usage reports
description: General Usage reports
---

# General Usage reports {#general-usage-reports}

Account IQ reports are basic analytic tools and reports that let you drill into your data to isolate [cohorts](/help/AccountIQ/product-concepts.md#segmet-def), identify anomalies, and build an understanding of your account characteristics.

General Usage reports page provides tools to carve out subgroups metrics based on the number of account devices in use, IPs detected, and respective zip codes.

<!--Divide the content in cohorts.

Content filters
device filters

segment and definition replicate to cohorts. Number of people and number of account that ......
content consumption.....-->

To view General Usage Reports:

1. Select the desired MVPDs from the **MVPDs in Segment** option.

2. Select the desired programmer channels from the **Channels in Segment** Option.

3. Select an appropriate time frame from the **Granularity and time frame** option.

   Using the above options you have defined segments for your analysis. Based on your segment selection, following graphs and reports are displayed.

4. You can fine tune your selection and further narrow it down by specifying (number of devices, number of IPs, and number of zip codes) thresholds in [Snapshot Overview - Accounts above thresholds](#snapshot-overview) widget.

## AuthN OK / AuthZ OK / Play Requests / Unique Subscribers {#authn-authz-playreq-uniquesubs}

The line graph here gives you a view of the changes over time in values of AuthN OK, AuthZ OK, Play Requests, and Unique Subscribers in a selected time frame for a defined segment.

![](assets/general-usage.png)

The x-axis has time duration plotted on it and the y-axis has absolute numbers of subscribers, play requests, and authentication attempts plotted on it. The line graph lets you compare the following values for the subscribers of MVPDs you selected in the segment selection panel:

* **AuthN OK**

    AuthN OK is the number of successful authentications, or the users' identification that are confirmed by an MVPD and user is redirected to the programmer application or site.

* **AuthZ OK**
  
    AuthZ OK is the number of successful authorizations, or the streaming requests (to stream a user's requested content) made by programmers (through Adobe) that are approved by MVPDs. The MVPDs grant the request based on the content rights associated with the user's MVPD subscription — for examaple whether the channel associated with the content is in the user's subscription.

* **Play Requests**

    Play requests are the requests made by a client application (or site) to Adobe to request a media token to record and secure a activities.

* **Unique Subscribers**

    Unique subscribers are the number of unique accounts subscribed to an MVPD that have interacted with video service provider apps (or sites) for a given period. The interaction includes any activity on the programmer app (or site) resulting in a call to an Adobe service.

    >[!NOTE]
    >
    >The total number of unique subscribers also include the number of unique devices if a programmer's use of Adobe TempPass (i.e. free preview) is part of the segment.

## Snapshot Overview - Accounts above thresholds {#snapshot-overview}

### Accounts Segment - based on selected thresholds {#account-segments-basedon-segments}

## Devices per Week per Account {#devices-week-account}
 
## Locations per Week per Account {#locations-week-account}

## IPs per Week per Account {#ip-week-account}

## Accounts Segment - Historical View {#account-segment-historical-view}