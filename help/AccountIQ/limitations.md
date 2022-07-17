---
title: Limitations and known issues
description: Known issues in the product. 
---

# Known issues and limitations {#known-issues}

Adobe strives to offer robust functionality and seamless user experiences through its offerings. The current version (version 1.0) of Account IQ provides usage and subscription sharing analytics to streaming providers with high degree of confidence. However, following limitations will be addressed in upcoming release versions.

* When defining cohorts in the dashboard or reports pages, there currently is no option to add metrics such as **number of devices** to refine the segment. This capability will be available in a future version.

* When estimating sharing scores for individual accounts, Account IQ takes a conservative approach that enables companies to act on sharing with great degree of confidence. However, this approach tends to underestimate the total amount of sharing when aggregated across many accounts.

* The [Overall Sharing Score](/help/AccountIQ/dashboard.md#overall-sharing-score) currently only factors in [Sharing Level](/help/AccountIQ/dashboard.md#sharing-level) and [Usage from Shared Accounts](/help/AccountIQ/dashboard.md#usage-from-shared-accounts). Future versions will factor in additional metrics.

* When defining cohorts in the dashboard or reports pages, the selectors for MVPDs and channels lack the search mechanism, as of now.

* When defining cohorts in the dashboard or reports pages, there is a limitation to select only up to 10 MVPDs and Programmers.

* The option to export account statistics is limited to export 1000 accounts, as of now.

* The option to select [Segment Type](#segment-type) when defining Operations is limited to **Fixed number of accounts**. The **Variable number of accounts** option will be available in a forthcoming version.

* The Benchmarking, Detection Models, Segments, Snapshots, and Rules sections in the left navigation are currently disabled and will be available in a forthcoming version.

* When creating [Operations](/help/AccountIQ/operation-affecting-user-segment.md), you can identify only two kinds of [Actions](/help/AccountIQ/operation-affecting-user-segment.md) as of now—Concurrency Monitory rules and External Actions.

* Currently, Operations can only be created and [scheduled](/help/AccountIQ/operation-affecting-user-segment.md#action). Future versions will allow you to pause, resume and fully manage them.

* Because of the more limited set of data used, Isolation mode does not truly reflect the amount of sharing. Therefore, MVPD in Isolation mode cannot be compared to any other MVPD.

* When you are defining a new [segment](/help/AccountIQ/segments-timeframe.md) for an operation you can add metrics. But if you select a saved segment then you cannot add more metrics to refine the segment.

* Granularity and timeframe selector is limited to one week or one month, which means data can be evaluated on a single week or a single month only.

* Predefined intervals are currently disabled in granularity and timeframe selector, and will be available in a future version.
