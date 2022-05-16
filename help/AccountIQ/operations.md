---
title: Operations tab
description: Integrating with Concurrency Monitoring to take remedial actions towards password sharing and gauge the impacts of your actions.
---

# Operations {#operations-tab-next-steps}

When you select the Operations tab under Actions, Operations page is displayed which lists all the Operations that are currently running in the Account IQ system.

It has already created operations.
List of multiple operations that are created in the Account IQ.

## How to create an operation in Account IQ {#create-operation}

To create an operation:

1. Identify/define your segment(cohort) for analysis.

    1. Select the desired MVPD(s).
    2. Select the desired programmer Channel(s).
    3. Specify a time period from the **Granularity and Timeframe** option.

1. Select **Create new operation**. The **Create new operation** page is displayed.

    ![](assets/create-new-operations.png)

1. On the **Create new operation** page, fill in the details in the form fields:

    * **General Settings**

        Name the new operation in **operation name** field. For example: "Test the effect of multifactor authentication on MVPD X's subscribers" or "Limit the number of streams in CM".

    * **Segment**

        The **segment** here defines the users who will be operated on by this operation.
        The first segment entry in the **Segment** section, by default, shows the **segment** and the **segment evaluation period** selected in the step 1. This segment defines the subscribers that will be affected by the operation being created.

        ![](assets/operations-segment-selection.png)
        
        For an instance, your (default) segment (selected on the main dashboard or reports page) includes all the subscriber accounts of MVPD named 'C' who view the channel 'N Sports'.  
refine-segment-operations.png)
        You can refine your default segment by adding more metrics. For example: you might want to add Sharing Score that is above 80 as another metric.

        *   
