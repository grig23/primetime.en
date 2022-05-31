---
title: Account IQ FAQs
description: Answers to frequently asked customer questions.
---

# Frequently asked questions {#faqs}

1. Who is Account IQ designed for?

   **Answer.** Account IQ is designed to serve Programmers, MVPDs, and D2C services, however there are minor differences between these two versions. There are limitations and restrictions on what data can be showed to each group.

1. How far back does the data go?

   **Answer.** Two years. Data retention policies prevent keeping data older than that.

1. How often is the data updated?

   **Answer.** Weekly and monthly.

1. Is it possible to filter out the test accounts?

   **Answer.** The functionality to filter out the test accounts is not available in this version, but the feature will be available in a future release.

1. Can I see the account sharing for each of my channels?

   **Answer.** Yes.

1. What is the data source used to identify credential sharing?

   **Answer.** The service examines all of the subscriber streaming activity and enhances it with proprietary data sources. For TV Everywhere this includes all transactions between programmers and MVPDs. From there, higher level analytics data of account sharing scores is synthesized.

1. What is the industry average?

   **Answer.** Industry average is reflected in the three primary sharing indicators—Sharing level, Usage from shared accounts, and Overall sharing score. These values represent the averages of all subscribers for all services.

1. How effective is Concurrency Monitoring in mitigating sharing in industry?

   **Answer.** Account IQ and Concurrency Monitoring detect different modes of sharing and are complimentary. Account IQ can be used with Concurrency Monitoring to measure the effect of Concurrency Monitoring, but that will take time and we will follow up.

1. Considering that it is not an enforcement tool, if we have insights then how do we use it to stop sharing?

   **Answer.** We plan to leverage Snapshots as a way to track the effect of whatever action you take. Then when we create a Concurrency Monitoring rule base on some sharing profile, we’ll be able to track the effect.

1. Can we identify particular accounts?

   **Answer.** Yes, we can provide the MVPD provided IDs back to them. We would like to provide that in real time.

1. How similar are Account IQ’s results to MVPDs who have built similar systems for themselves?

   **Answer.**

1. For Programmers that have enabled Concurrency Monitoring, how do their sharing scores compare to us?  Does Concurrency Monitoring help or not, since they are both tackling the same problem?

   **Answer.** CM identifies simultaneous use whereas AIQ is not dependent on that.  So, they compliment each other. Regarding comparison, there are a number of factors that drive sharing (e.g. live sports).  So, it’s hard just to compare one Programmer to another.  You’d want to try to compare as situations as similar as possible.  In general we’re looking at how AIQ can help measure the effectiveness of CM and we’re running an analysis on Olympics data that BG will follow up on.  Also, another Programmer has asked for reports on the impact of CM on AIQ scores and we’ll be working on that.

1. How do we use these insight, what do we use it for or how do we stop it?  CM seems to be a good application since we’re a customer for that.

   **Answer.** We’re thinking along the same way.  We’re working on an integration between AIQ and CM for that exact purpose.  (I also talked about how Snapshots could be used to measure the effectiveness of these measures.)

1. Do we need to work with MVPDs to implement measures like smart CM?

   **Answer.** No, we could make the data available to you to create your own CM rules based on AIQ data.  Or, we could possibly create these rules for you.

1. How will we be able to see how trends look over time?

   **Answer.** The challenge is system performance and we’re working on that.  We have great designs for viewing data on time, but it’s a huge amount of data to process. Snapshots will help with this - involving smaller data sets and allowing us to compare two snapshots.

1. How can we identify different cohorts?  Answering questions like, “Is it related to a specific piece of content?”, or, “Have that just been sharing in general for a while?”

   **Answer.** We have some filters available now for identifying cohorts (e.g. very high probability of sharing, usage patterns), and we’d like to hear back for other filters you’d like to apply. From there you could decide specific actions to take on each.
