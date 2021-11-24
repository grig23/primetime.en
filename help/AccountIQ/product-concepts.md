---
title: Account IQ glossary
description: 
---

# Product concepts and glossary {#glossary}

**Media Company**

Media Company is a company that owns a group of media networks.

**Programmer**

Programmer, also known as Network, is a company that is subsidiary of a larger company (corporation) that owns and manages one or more channels.

**Channel**

Channel, also knows as Property, is a thematically related source of video content.  Traditionally representing a distinct, numerically addressable continuous video feed from an MVPD. This channel directly maps to an accessible channel of content available to the subscribers through their Set Top Box (STB).

**MVPD**

MVPD, also known as Distributor, is aggregator, reseller, and distributor of Media Company video content.

**Aggregated Risk Index**

Also known as Risk Index and Sharing Risk Index, it is a value that helps users understand the magnitude of password sharing on Programmer properties or by MVPD subscribers and provide them a sense of urgency to act upon it.

**Risk Index - Accounts**

Also known as Shared Accounts Risk Index, it is a value calculated based on an average of the sharing probability computed for every account in the set of selected MVPDs that has streamed from a one of the selected Programmer Channels during the selected time frame.

**Risk Index - Usage**
A value calculated based on the number of play requests made by the each account weighted by each account's sharing probability.	Usage by Shared Accounts Risk Index

**Risk Index - Overall**
A value computed as an average of "Risk Index - Accounts" and the "Risk Index - Usage".	Overall Sharing Risk Index

**Industry Average Index**
A value computed for each of the Risk Indices (Accounts, Usage, Overall) across all Programmers and MVPDs during the selected time frame.

**requestorID**
The ID a Media Company Uses to identify themselves or a subsidiary to an MVPD.  Depending on Programmer implementation, this could map to a Media Company, Programmer or Channel.  The most common The ID a Media Company Uses to identify themselves or a subsidiary to an MVPD.  Depending on Programmer implementation, this could map to a Media Company, Programmer or Channel.  Traditionally, this mapped to a Channel.  With the creation of pseudo-Channels like MML (March Madness Live) and technically driven moves to address MVPD-driven data limitations, requestorID is beginning to become more associated with the Media Company.

**resourceID**
The content requested by the end user.  Traditionally, this has identified the Channel associate with the content the user has requested.  System enhancements allow that ID to represent specific programs (e.g. with specific ratings), the ID continues to identify the associated Channel.

**Period**
The window of time that contains the play request activity represented in the UI and Tables from start to finish.	Time frame, time slot

**Trend**
The difference in the associated metric (e.g. Play Requests) between the current and previous period.

**Static device** 
A device that has very low mobility (example: GameConsole, SetTopBox, TV, etc.)

**Mobile device:**
A device that has high mobility(example: MobilePhone, Tablet, etc.)

**Location**
The geolocation for a specific play request, detected using the Pass data, with a precision of 1000mx1000m (one square km).

**Home Location**
the precision is 0.01 ~ 2000mx2000m (4 square km) - at this moment the home location is detected using an ML algo, based on data provided by two mvpds. The probability is ~ 80%. We are not using the zip code for the majority of the users. Currently, this information is not used in assessing the sharing probability.

**Cluster** a cluster is a collection of locations and devices. The clusters are created by finding common locations between devices. The devices that have been seen in a common location will be considered to belong in the same cluster. Two devices can be in the same cluster even though they do not have common locations but can be connected through the locations of other devices.
**Mobile Cluster**
a cluster that has no static devices

**Static Cluster**
a cluster that has at least one static device

**Usage**
Because the usage data at the user level can be inconsistent we are not using in this moment the usage in the patterns definitions. Even so, we can use it to have a programmer usage level overview. 
Infrequent User: less than 9 play requests per month (how were these levels defined? we need to update them? there are industry standards?)
**Regular user** from 9 to 37 
**Avid User** more than 37 play request per month
