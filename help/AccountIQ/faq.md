---
title: Account IQ FAQs
description: Answers to frequently asked customer questions.
---

# Frequently asked questions {#faqs}

1. Who is the Account IQ designed for?

**Answer.** The account IQ is designed to serve Programmers and MVPDs. However, the versions are different for both the users different rights to the underlying data and different motivations.

Q: How far goes the data , in the back? One year, couple of months?
A:
Q: How often is the data updated?
A:
Q: Is it possible to filter out the test accounts?
A:






Q: Can I see the account sharing per each of my channels? (coming from NBCU & ESPN)
A:

Q – What is the data source?
R - Both programmer and MVPD / Todd explained that we have a 95% of the market and we can track all details about a specific account (from MVPD data, through user metadata, to programmer data - devices, IPs)

1. What is the source of the data in Account IQ?

    Answer. Adobe Pass and Adobe Authentication sit in the middle of all TV Everywhere transactions between Programmers and MVPDs. From there, we synthesize higher level analytics data of account sharing scores.

1. What is the industry average?

Answer. It is the score of all MVPDs versus all Programmers.

1. How effective is Concurrency Monitoring in mitigating sharing in industry?

Answer. Account IQ and Concurrency Monitoring detect different modes of sharing and are complimentary. Account IQ can be used with Concurrency Monitoring to measure the effect of Concurrency Monitoring, but that will take time and we will follow up.

1. Considering that it is not an enforcement tool, if we have insights then how do we use it to stop sharing?
Answer. We plan to leverage Snapshots as a way to track the effect of whatever action you take. Then when we create a Concurrency Monitoring rule base on some sharing profile, we’ll be able to track the effect.

1. Can we identify particular accounts?

Answer. Yes, we can provide the MVPD provided IDs back to them. We would like to provide that in real time.

1. How similar are Account IQ’s results to MVPDs who have built similar systems for themselves?

Answer.

1. For Programmers that have enabled Concurrency Monitoring, how do their sharing scores compare to us?  Does Concurrency Monitoring help or not, since they are both tackling the same problem?

Answer. CM identifies simultaneous use whereas AIQ is not dependent on that.  So, they compliment each other. Regarding comparison, there are a number of factors that drive sharing (e.g. live sports).  So, it’s hard just to compare one Programmer to another.  You’d want to try to compare as situations as similar as possible.  In general we’re looking at how AIQ can help measure the effectiveness of CM and we’re running an analysis on Olympics data that BG will follow up on.  Also, another Programmer has asked for reports on the impact of CM on AIQ scores and we’ll be working on that.

1. How do we use these insight, what do we use it for / how do we stop it?  CM seems to be a good application since we’re a customer for that.

Answer. We’re thinking along the same way.  We’re working on an integration between AIQ and CM for that exact purpose.  (I also talked about how Snapshots could be used to measure the effectiveness of these measures.)

1. Do we need to work with MVPDs to implement measures like smart CM?

Answer. No, we could make the data available to you to create your own CM rules based on AIQ data.  Or, we could possibly create these rules for you.

1. How will we be able to see how trends look over time?

Answer. The challenge is system performance and we’re working on that.  We have great designs for viewing data on time, but it’s a huge amount of data to process. Snapshots will help with this - involving smaller data sets and allowing us to compare two snapshots.

1. How can we identify different cohorts?  Answering questions like, “Is it related to a specific piece of content?”, or, “Have that just been sharing in general for a while?”

Answer. We have some filters available now for identifying cohorts (e.g. very high probability of sharing, usage patterns), and we’d like to hear back for other filters you’d like to apply.  From there you could decide specific actions to take on each.
