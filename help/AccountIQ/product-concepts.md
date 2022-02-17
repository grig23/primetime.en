---
title: Account IQ glossary
description: A glossary of product terminologies.  
---
# Product concepts and glossary {#glossary}

Refer the following product terminologies and their definitions.

## Media Company {#media-company}

Media Company is a company that owns a group of media networks.

**Programmer**
Programmer, also known as Network, is a company that is subsidiary of a larger company (corporation) that owns and manages one or more channels.

**Channel**
Channel, also knows as Property, is a thematically related source of video content. Traditionally representing a distinct, numerically addressable continuous video feed from an MVPD. The channel directly maps to an accessible channel of content available to the subscribers through their Set Top Box (STB).

**MVPD**
MVPD, also known as Distributor, is aggregator, reseller, and distributor of Media Company video content.

<!--**Aggregated Risk Index**
Also known as Risk Index and Sharing Risk Index, it is a value that helps users understand the magnitude of password sharing on Programmer properties or by MVPD subscribers and provides them a sense of urgency to act upon it.-->

**Risk Index - Accounts**
Also known as Sharing Level or Shared Accounts Risk Index, it is a value calculated based on an average of the sharing probability computed for every account in the set of selected MVPDs that has streamed from a one of the selected Programmer Channels during the selected time frame.

**Risk Index - Usage**
Also known as Usage from Shared Accounts, it is a value calculated based on the number of play requests made by the each account weighted by each account's sharing probability. It is also known as Usage by Shared Accounts Risk Index.

<!--**Risk Index - Overall**
A value computed as an average of "Risk Index - Accounts" and the "Risk Index - Usage". Overall Sharing Risk Index-->

**Industry Average Index**
A value computed for each of the Risk Indices (Accounts, Usage, Overall) across all Programmers and MVPDs during the selected time frame.

**Metric**
Metric is an attribute of subscriber account (for example, their MVPD, the programmers and channels of the content they stream, the number of devices they use).

**Segment**
Segment is a set of accounts that meet the user defined conditions specified by the selected metrics (for example "users of MVPD A, B, C, D or E that have watched channels X, Y or Z").

**Top MVPDs in segment**
The top (at most 10) MVPDs in the selected segment as measure by either Sharing level, Usage from shared accounts, or Overall sharing score.

**Accounts Sharing Probability**
A dashboard panel with charts that divides the current segments sharing scores into sharing range categories of Very Low, Low, Moderate, High, and Very High.

**Sharing Probability Level**
A dashboard panel with charts that divides the current segments sharing scores into sharing range categories of Very Low, Low, Moderate, High, and Very High, along with each categories percentage of the total amount of streaming for the segment.

**AuthN**
Authentication, or the number of authentication attempts. An authentication attempt is the process whereby a user without a currently valid authentication state is redirected to their chosen MVPD, where they identify themselves to the MVPD - typically with a username and password.

**AuthN OK**
The number of successful authentications. A successful authentication occurs when a users identify is confirmed by an MVPD and results in the user being redirected back to the programmer app or site.

**AuthZ**
Authorization, or the number of authorization request. An authorization request is the process whereby a programmer requests permission from an MVPD through Adobe to begin streaming a user's requested content. The MVPD typically grants the request based on the content rights associated with the user's MVPD subscription (e.g. whether the channel associated with the content is in the user's subscription). Some authorization request responses are cached by Adobe, which allows Adobe to respond immediately without passing the request on to the MVPD.

**AuthZ OK**
The number of successful authorizations.

**Play Request**
A request made by a client app or site to Adobe to request a media token to record and secure a stream start.

**Unique Subscribers**
The number of unique MVPD accounts for a given period that have interacted with programmer TV Everywhere apps or sites involving Adobe Pass for a given period.  That interaction includes any activity on the programmer app or site that results in a call to an Adobe Pass service (e.g., checking authN or authZ state, authenticating, authorizing, etc.).  The total number of unique subscribers will also include the number of unique devices if a programmers use of Adobe TempPass (i.e. free preview) is part of the segment.

**Device**
A digital video hardware product capable of playing TV Everywhere content and supported by Adobe Pass (e.g., smart phones, laptop and desktop computers, game consoles, smart tv's, etc.).

**Location**
A unique point on earth.

**IP**
The Internet Protocol address assigned to a device by an Internet Service Provider (e.g., cable service provider, cell service provider, etc.).

**Zip Code**
The U.S. Postal code associated with locations within the U.S.

**Geographical Span**
The distance between the farthest points in a set of locations.

**Usage Pattern**
One of a finite set of category labels applied to an account that best characterizes the users of the account in terms of social groups or behaviors (e.g., a small family, a traveler or commuter, social sharing, etc.).

**Isolation Mode**
A type of sharing analysis where the evaluation of an account is limited to events that occurred directly on the programmers in the selected segment.  Normally, all account events are evaluated, which provides a much more accurate estimate of sharing.  Some MVPD data is structured in a way that only allows for Isolation Mode analysis.

**requestorID**
The ID a Media Company Uses to identify themselves or a subsidiary to an MVPD.  Depending on Programmer implementation, this could map to a Media Company, Programmer or Channel.  The most common The ID a Media Company Uses to identify themselves or a subsidiary to an MVPD.  Depending on Programmer implementation, this could map to a Media Company, Programmer or Channel.  Traditionally, this mapped to a Channel.  With the creation of pseudo-Channels like MML (March Madness Live) and technically driven moves to address MVPD-driven data limitations, requestorID is beginning to become more associated with the Media Company.

**resourceID**
The content requested by the end user.  Traditionally, this has identified the Channel associate with the content the user has requested.  System enhancements allow that ID to represent specific programs (e.g. with specific ratings), the ID continues to identify the associated Channel.

## Time frame {#time-frame}

Also known as Period or Time Slot, it is the window of time that contains the play request activity represented in the user interface and tables from start to finish.

**Granularity**
In reference to time frame, the size of the period; such as one week or one month.

**Trend**
The percentage difference in the associated metric (for example, percentage of total play requests) between the current and previous period.

## Usage pattern concepts {#usage-pattern}

**Static device**
A device that has very low mobility (example: GameConsole, SetTopBox, TV, etc.)

**Mobile device:**
A device that has high mobility(example: MobilePhone, Tablet, etc.)

**Location**
The geolocation for a specific play request, detected using the Pass data, with a precision of 1000mx1000m (one square km).

**Home location**
the precision is 0.01 ~ 2000mx2000m (4 square km) - at this moment the home location is detected using an ML algo, based on data provided by two mvpds. The probability is ~ 80%. We are not using the zip code for the majority of the users. Currently, this information is not used in assessing the sharing probability.

**Cluster** a cluster is a collection of locations and devices. The clusters are created by finding common locations between devices. The devices that have been seen in a common location will be considered to belong in the same cluster. Two devices can be in the same cluster even though they do not have common locations but can be connected through the locations of other devices.

**Mobile cluster**
a cluster that has no static devices

**Static cluster**
a cluster that has at least one static device

**Usage**
**Infrequent user** less than 9 play requests per month.
**Regular user** from 9 to 37 play requests per month.
**Avid user** more than 37 play request per month.

**Concurrency**
The concurrent is defined by two (or more) streams played at the same time or very close in time so that the interval between them cannot be justified by traveling at a normal speed.
Concurrent usage is calculated using the maximum speed(miles/hour) between 2 different clusters. A user is considered to have concurrent usage if he has a speed greater than 124 m/h on a distance lesser than 124 miles or if he has a speed greater than 400 m/h on a distance greater than 124 miles. The distance is calculated between locations from different clusters. Concurrent usage is allowed in the same cluster.
