---
title: View reports in isolation mode
description: View reports in isolation mode for Xfinity. 
---

# View sharing reports in isolation mode {#report-isolation-mode}

Generally, Adobe Account IQ evaluates the various streaming events to identify the sharing probabilities of subscribers based on the same account identifier for each subscriber play request irrespective of the devices they use. However, some MVPDs (such as Xfinity) identify the play requests (made on different channel apps) by the same subscriber using different devices as separate. Such streaming requests are analyzed in Isolation Mode.

![](assets/isolation-diff-new.png)


*Figure: Differences in account identifiers for standard and isolation mode MVPDs.*  

In Isolation Mode all the computations made for obtaining the Sharing Scores and all the associated metrics are made using only the activity of the devices streaming from applications belonging to the selected Programmer and channels.

The sharing scores and probabilities are calculated only using the stream that starts from the currently selected channels.

To view metrics in isolation mode:

1. Select **isolation mode** from the **MVPDs in segment** drop-down option, and select **Apply Selection**.

   ![](assets/xfinity-in-segment.png)

2. Select the desired channels from the **Channels in segment** drop-down option, and select **Apply Selection**. Also, select a [time frame](/help/AccountIQ/product-concepts.md#granularity-def).

>[!IMPORTANT]
>
>Because account sharing is more relevant when measured for streaming across all Programmers’ apps, you will see lower Sharing Scores and some variation in the metrics when in Isolation Mode.

![](assets/aggregate-sharing-isolation.png)

Note that the above gauges show that only 6% of all the accounts are being shared; and only 8% of the content is being consumed by those 8%. So the channels can compare their scores in Isolation Mode with that across the other MVPDs. Therefore, the information obtained by using Isolation Mode should be interpreted differently from the other data.

<!-- The focus is on the 2 different types of MVPDs.  Isolation Mode MVPDs (i.e. Xfinity) identify subscribers differently based on the Programmer they’re interacting with. The result is that Standard MVPDs consistently identify subscribers across devices no matter which Programmer they’re interacting with, whereas Isolation Mode MVPDs consistently identify subscribers across devices only if they’re accessing the same Programmer.  In fact, Isolation Mode MVPDs will not consistently identify a subscriber even if they’re using the same device across different Programmers (see Subscriber B in the Isolation Mode MVPD case).  In the net result in the example above is that the Isolation Mode MVPD identifies four different subscribers instead of two.

To manage this distortion of the data, Isolation Mode limits the activity reported about a Programmer to the activity only on that Programmer’s apps.  Again using the example, Programmer L would only see two different users in both cases (i.e., R and S for the Standard MVPD and W and Y for the Isolation Mode MVPD).  The downside is that Programmer L is deprived of sharing information gathered about Subscriber A and B due to activity with any Programmer other than L.
-->