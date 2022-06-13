---
title: How to define segment in Account IQ using segment and timeframe panel
description: How to view sharing reports for multiple MVPDs and multiple programmer channels.
---

# How to define segment in Account IQ: using segment and timeframe panel {#define-segment}

All analysis or viewing reports in Account IQ begin with defining segment and selecting timeframe for evaluation. [Segment](/help/AccountIQ/product-concepts.md#segmet-def) refers to all the subscribers or viewers that meet your criteria (subscribing to an MVPD and viewing sepcific channels) of evaluation.

![](assets/segment-panel.png)

*Figure: Segment and timeframe selection*

At the top of all the reports pages on Account IQ, there is a panel to define segment by selecting MVPDs, channel programmers, and granularity and time frame.

## Segment selection {#select-segment}

### Select MVPDs in segment {#select-segment-mvpds}

To select MVPDs from **MVPDs in segment** option:

1. Select the **MVPDs in segment** dropdown option.

   >[!NOTE]
   >
   >**All** industry MVPDs are selected by default. You can select either of the **Top 10 MVPDs by sharing score**, **Top 10 MVPDs by usage**, and **Top 10 MVPDs by accounts**. However, to select individual MVPDs you need to deselect **All**.

1. Select the desired MVPDs.
    To change your selection, then deselect the selected names of MVPDs.

1. Select **Apply selection** for your selection to take effect. Otherwise, you will loose your selection.

   >[!NOTE]
   >
   >If you select Isolation mode, then none of the other MVPDs can be selected.

### Select channels in segment {#select-segment-channels}

To select the desired programmer channels from the **Channels in segment** option:

1. Select the **Channels in segment** dropdown option.

   >[!NOTE]
   >
   >**All** programmer channels in the industry are selected by default. You can select either of the **Top 10 programmers by sharing score**, **Top 10 programmers by usage**, and **Top 10 programmers by accounts**. However, to select individual channels or programmers you need to deselect **All**.

1. To select the desired channels or programmers, deselect **All** (or deselect the existing selection).

1. Select the desired programmers or channels. You can either select individual channels the programmers.

   >[!NOTE]
   >
   >When you select a programmer, all the channels under that programmer are selected by default.

   >[!IMPORTANT]
   >
   >When you select all the individual channels under a programmer it displays the reports differently when you select the parent programmer (and all individual channels under it are selected by default due to this selection).

1. Select **Apply selection** for your selection to take effect.

>[!CAUTION]
>
>We cannot select more than 10 items in MVPD and programmer selectors.

## Granularity and timeframe selection {#granularity-timeframe}

To select a time period of evaluation:

1. Select the **Granularity and time frame** dropdown option.

1. Select either **Week** or **Month** from **Aggregate by** option. By selecting  the granularity

 for evaluation you select either a past month or a past week.

Once you have selected granularity, then use the forward or back arrows to move forward or backward in time.

If your granularity is in monnths.

1. Once you select a particular month or week make sure to select Apply Selection to make sure your selection takes effect.




Another way to change selection is to deselct the any of the previously selected MVPDs and channels. in the segment nd timeframe panel. Or you can clear the entire selection, and defaults you back to All.