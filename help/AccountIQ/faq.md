---
title: Account IQ FAQs
description: Answers to frequently asked customer questions.
---

# Frequently asked questions {#faqs}

1. Who is the Account IQ designed for?

Answer. The account IQ is designed to serve Programmers and MVPDs. However, the versions are different for both the users different rights to the underlying data and different motivations.

2. What is the source of the data?

[BB} It’s all first party data.  We sit in the middle of all TVE transactions.  From there we synthesize higher level 



[AT] What is the industry average?
[BB] It’s the score of all MVPDs versus all Programmers.



[MW] Two questions: 1) How confident are you in the data? 2) How effective is CM in mitigating sharing (in industry)? 

[BB] Answering #2 first, AIQ and CM detect different modes of sharing and are complimentary.  We’ve used AIQ to estimate the amount of sharing during Olympics and will share (though those estimates are based on AIQ specific data).  AIQ can be used with CM to measure the effect fo CM but that will take time and we will follow up.

[BB] Addressing how NBCU compares to others, there are a number of factors.  You have to take into account program content (e.g., entertainment, live sports, etc.), or you’re not comparing apples to apples.  There’s building feedback to understand how one system impacts the other.



[MW I get that this isn’t an enforcement tool.  If we have this insight how do we use it to stop sharing? 

[BB] We hope to have a way to apply this (e.g. CM) to action by end of year.  We also plan to leverage Snapshots as a way to track the effect of whatever action you take.  Then when we create a CM rule base on some sharing profile, we’ll be able to track the effect.



[MW] Can we identify particular accounts?

[TG] Yes, we can provide the MVPD provided IDs back to them.  We’d like to provide that in real time.



[MW] How similar are Account IQ’s results to MVPDs who have built similar systems for themselves (i.e. how confident are you in the data)?

[TG] The difference between what we’re able to do and what Comcast is able to do is that their solution is built more for the Xfinity experience (who’s data we don’t have access to) and less so for the TVE use cases.  They have some basic handling for TVE use cases.  We have a lot more event data available to us.  We’d be very interested in working with an MVPD to try to get a more holistic view.  AIQ can inform appropriate action.



[MW] For Programmers that have enabled CM, how do their sharing scores compare to us (NBCU)?  Does CM help or not, since they’re both tackling the same problem?

[BB] CM identifies simultaneous use whereas AIQ is not dependent on that.  So, they compliment each other. Regarding comparison, there are a number of factors that drive sharing (e.g. live sports).  So, it’s hard just to compare one Programmer to another.  You’d want to try to compare as situations as similar as possible.  In general we’re looking at how AIQ can help measure the effectiveness of CM and we’re running an analysis on Olympics data that BG will follow up on.  Also, another Programmer has asked for reports on the impact of CM on AIQ scores and we’ll be working on that.



[MW] How do we use these insight, what do we use it for / how do we stop it?  CM seems to be a good application since we’re a customer for that.

[BB] We’re thinking along the same way.  We’re working on an integration between AIQ and CM for that exact purpose.  (I also talked about how Snapshots could be used to measure the effectiveness of these measures.)



[TB] Do we need to work with MVPDs to implement measures like smart CM?

[BB] No, we could make the data available to you to create your own CM rules based on AIQ data.  Or, we could possibly create these rules for you.



[JO] How will we be able to see how trends look over time?

[BB] The challenge is system performance and we’re working on that.  We have great designs for viewing data on time, but it’s a huge amount of data to process. Snapshots will help with this - involving smaller data sets and allowing us to compare two snapshots.



[PC] How can we identify different cohorts?  Answering questions like, “Is it related to a specific piece of content?”, or, “Have that just been sharing in general for a while?”

[BB] We have some filters available now for identifying cohorts (e.g. very high probability of sharing, usage patterns), and we’d like to hear back for other filters you’d like to apply.  From there you could decide specific actions to take on each.



[PC] Could the score be connected with the specific play event (Omniture) related to the content to get a better insight into the type of sharing and intent?

[BB] We’d be interested in looking into this.

Disney - 24 May 2021 
Attendees:
Disney: Amber Z., Sean P., Jasmine R.G., Andrew D.
Adobe: Brian, Todd, Calin

Pre-meeting agenda:

Should we export month over month percent change in chart CSVs or let you calculate it?
Is there value in Number of Locations and Geographic Span graphs?
Would an export be useful and if so how should it be formatted?
Do you have any feedback on a feature to help display or represent the monetary impact of sharing?
Lost revenue per MVPD, etc.
Potential value of extra Ads for a segment (e.g. Accounts > 80% probability)
Do you have any preliminary priorities identified for Jun-Sep (I can guess but would prefer not to bias you with suggestions)
What does Disney+ plan to do about credential sharing?
Miscellaneous product feature feedback
Meeting notes:

At the question about the calculated percentage, they answered that yes, they can calculate it but would be also helpful to have it directly in the exported csv.
They used the geographical span a handful of times, it was nice to drill down. 
export - at the chart level vs the list with top 1k offenders
- they answered that both options are useful, in their own way. but mainly the high-level views, - the export at the chart level, as they use that data for execs presentations (this was an overarching theme, looks like the main use of AIQ at this moment for them is to make business presentations for their execs)
- flag! - the export functionality was not working for them, they just had a vague idea about what it is supposed to be there. 🙁
- talking about the export at the chart level, they mentioned that would be cool to have a "copy chart in the clipboard" capability.
- also mentioned that would be helpful to have the "download what is in current view" functionality (again, for building execs presentations)
At the question about a feature that can show them the money that they are losing (and informed that they could be required to input somehow, secured and anonymized, the value/subscription or something similar) the answer. was "yes, this will be really helpful!"
- ActionItem here - to prioritize a mockup prototype to include some sort of "lost $" functionality
They said they will be willing to participate in a 100$ test, "that would be great"
- note for us here - the 100$ test needs to be planned and prepared carefully in advance. we can let them add new features/or not, we can have a list of hi-level product areas or very clearly defined features. 
important personal insight - throughout the entire meeting, and not only on this one, when asked about their conversations/negotiations with MVPDs, and what will help them to be more persuasive in those conversations, Amber asked about ideas and guidance from Adobe on how to do this, on how to approach them. Seems that they are looking for more consistent support from our side, on how to talk with MVPDs about the credentials sharing perspective. Is there anything we can do here?
Related to the Disney + initiatives for limiting credential sharing, they had no information but Andrew promised to ask and come back with more info. 


AMC - 13 Apr 2021 
Attendees: NBC - Alfred Perry, Greg Granito, Emma Casley  \ Adobe:  Brian, Todd. 

Met with the lead of their Intellectual Property Protection team (Al) and their streaming product group.
Started off asking questions about AMC+, assuming that AIQ applied to their D2C offering as well.
After explanation, they understood it did not, but both parties were interested in exploring how it could (e.g. data import).
As often the case, there was confusion around interpreting the top line scores, prompting questions like, "Does a Shared Accounts Index of 30 mean that 30% of my users are sharing?"
The IP Protection team is entering budget review and asked for us to prepare slides to pitch AIQ.  Specifically, they asked for:
Numbers and data that would create "shock and awe", i.e. create an urgency for them to take action.
A list of top MVPD offenders.
Mention the use case of Programmers leveraging the data in MVPD negotiations.
Mention the use case of Researchers using the data to augment content consumption behavior .


WarnerMedia - 22 Mar 2021 
Attendees: WarnerMedia - Quincy John, Kristy. Evans, Victor Mercado, Byron Saltysiak \ Adobe:  Brian, Calin. 

Meeting notes CalinF (comments from Brian inline)

Questions about the test accounts - are they included in the calculation of the risk index? There is any way to isolate them? (feature request) We have a Jira story to investigate effort for this is https://jira.corp.adobe.com/browse/AIQ-803.  We should finalize this and consider pulling it into MVP.  The capability would be delivered by engineering and would depend on an ongoing Program/MVPD effort to maintain an list of active test acounts.
The main questions were around the mechanism of the algorithm, it was really hard to quickly explain it, we spend a lot of time on this. (Maybe it's better not to try to explain it to the customer in detail, but to keep it as a "property-calculated" formula. And explain to them that it's similar to the credit score?) I also think we need to be able to: 1) provide the forumla, and 2) illustrate the net state and effect.
They asked about the "value" of the product. "Now that we understand how many people share their content, what can we do?" It was clear that they don't perceive an obvious value of the product and they do not understand if there are actionables after the understanding. (or what actionables are\ available). They said that maybe using the understanding, they can go and discuss with MVPDs.  It is also illustrative of their thinking was their suggesting they could use the product to prove to MVPDs that sharing wasn't bad and they could use AIQ data as a defense against MVPDs asking for fraud prevention methods like CM.  It reflects their reluctance to act and potentially drive customers away, perhaps limit ad impressions, and ultimately cost them in building or buy solutions like CM.
Very precise question about how AIQ will be offered - as part of a package, included in other existing products, a product on its own?  A question for Sales.
They asked about the info that we offer on the locations (feature request?)
Ideas (Next steps): 

we need to have real use-cases about the value of the product, about how exactly they (or a potential customer) can use the product. 
Follow up with formula for Shared Accounts Index
Follow up to get their interest in participating in a beta
NBC - 10 Mar 2021 
Attendees: NBC - Scott. Sheridan, Williams Monica, Palmer Carmen, James Oliveros, Tara Brock  \ Adobe:  Brian, Todd, Calin. 

Brian did a walkthrough of the AIQ. 
at first, they didn't have too many questions but the time was short
They are using Adobe Analytics, but not in their group.
In the end, Williams Monica (VP NBC) seemed interested and asked few questions about the actionability of the findings that AIQ is supposed to show. (comment CFA - looks like the market still needs to be educated on the next steps/actions after finding the frauds) 
Todd explained all the possible actions 
Tara Brock (SR PDM, NBCU) - the fraud is always in the back of my mind. We need to know what MVPDs think about fraud and the aiq can position us in a partnership discussion with them. 
Free trial proposed - the reaction was good, they asked about the next steps. (comment CFA - maybe we need to make more clear what are the expectation from them? like a regular bi-weekly 1-hour feedback meeting? So we can avoid the previous situation when that had access to a free trial and never used it )
Adobe to come up with a follow-up for the free trial. 


Wave 1
NBCU - 04 Feb 2019 
Questions from Abraham:

Can we filter the data to only show NBCU usage instead of the full data set?
When will Comcast be added?
When will Sports be removed?
When will we be able to see break down by brand within our accounts?
When will we be able to see break down by platform/specific device within our accounts?
Can we see brands cross section across “at risk” accounts?
When will test accounts be removed?
Can we break out Mobile versus WiFi?
Can we define home IP based on the IP range from the ISP?
Can we drill down if we pinpoint a specific city/IP/account to get more details for us to analyze?
Cox - 26 Nov 2018 
Attendees: Todd, Robert, Jens, Kory - Doug Gravino, Pujan Roka, Lauryn Shabanowitz

High Level Summary:

Very productive meeting with more engagement and positive attitude than the previous 2 meetings we had with Cox. Although until now they were more a detractor for AIQ, now they seem to have moved into the promoters boat.
Doug was very delighted with the demo and he's eager to start the partnership for Account IQ. 
He stated a few times during the meeting: "It's fascinating data" and that he is excited to get this going. He would like to start using it even from December if the paper work would be ready.
Kory needs to draft the contract
Cox Feedback and Questions:

They would like to be able to modify the levers of the algorithm and to adjust them according to their needs and use cases
They are interested in comparing the data they have on their Cox apps with what we see across Programmer apps → they asked if they can ingest their data into AIQ and compare it inside AIQ
Doug asked what we will provide as part of the partnership and if we can collaborate on a regular basis to discuss and analyze together. He was afraid that they would get only a csv file (smile) and he was very glad when we told him that the dashboard we showed during the presentation will be available and they can do breakdowns per Programmers and analyze on their own on different weeks or months.
They also asked if we can have an API that they can query and if they will be able to fetch the data on their own
They were interested in the algorithm and if they can see / understand why a certain user was flagged with a certain sharing probability
They acknowledged that they don't offer HBA right now to Programmers and that they don't pass us any in-home information - but they would like to work with us and provide this data further on
They asked if we already have the Geographical view since the slide we showed them was somehow inline with their footprint areas (coincidence) → told them that it is only a mock right now (Calin Fara did some very good mock-ups (smile) ) but that we plan to have it in the near future 
They seem to be first interested in getting the list of Top shared accounts, analyze them and then decide what actions they take upon them
In terms of actionability we also proposed a Netflix like approach for the users that are not overt sharers - offer them an up-sell on the number of devices / concurrent streams they are allowed to use 
Charter - 26 Sep 2018
Call Report from Brandon Lane
 
Customer: Charter Communications
Meeting date: 9/26/18
Charter Attendees:

Jodi Robinson- SVP Experiences
Mike Baldino- VP Product Intelligence
Brian Molke- Strategic Initiatives
Anthony Piro- Technical Lead, Video App Security
Brock Bose- Data Scientist
Marjorie Truitt- Director Product Reporting
Yizhe Xu- Analyst

High Level Summary

Charter wants an industry solution for fraud protection to be adopted by both programmers and MVPDs.
Charter tired of leading alone, feels it’s programmers responsibility to police their own content.
Strategy- Adobe, Charter, and ESPN to come up with a consistent, industry-wide fraud protection standard in which ESPN can push the MVPDs and Charter can push the programmers to adopt.

Charter Feedback

Charter did not clearly understand our process for fraud protection from the presentation. Specifically, they had questions around our data elements used, methodology, scoring system, and results we shared.
Charter shared their process for identifying high risk accounts including data element indicators (features), algorithm methodology, scoring model, and results.
Confirmed they only used out of home data, no in home data was used (same data Adobe has access to)
Identified Device ID as major problem that needs to be addressed- followed up with Anthony Piro and Bucharest team.
Charter scores each programmer individually, does not take into account viewing on other apps when looking at one programmer
Charter would like to run a side by side test in which we run our fraud protection products separately, compare high risk accounts, and understand where there is overlap, where there are differences, and how we can make each other’s system improve.

Charter Questions

How do we account for in home if we don’t have in home data (ie.e what assumptions are we using). We never gave them a straight answer as to how we account for this. We owe them an answer.
What data do we have that they don’t have. They want this in a list format.
What data elements (features) are we actually using vs aspirational.
What makes up our modeling/scoring algorithm.
Anthony wants to know for each device, what is actually being sent. BG said Kitty should have that information.

Next steps

Charter to send Adobe their presentation (Brandon to follow up today for the ask)
Adobe to fill in Adobe information for each slide (data elements/features, scoring, modeling, etc) with a goal of having an identical presentation format with our information filled in.
Adobe and Charter to agree on common strategy and prepare for ESPN meeting
Adobe to help set up Charter/Adobe/ESPN meeting in NY on the 17th .
November- agree on a common process for identifying fraud and scoring risk, and run a side by side test for 3-6 months (phase 2 Account IQ).






FOX - Demo and pricing


Attendees :

Fox:  Anne Y., Ryan B., MichelleG, Eduard F , Aaron T, Sanam J. , Ariff S.

Adobe: Todd (presenter) , Brandon (presenter), Diana, Calin



Brandon's notes after the meeting:

The customer believes that what we have available today (high level insights on Fox Viewer account sharing problem) is valuable and is willing to pay for a quarterly report.
The customer also agreed that if the insights were actionable, with clear monetization channels in place, that the $1.2M price range could be justified.
There are 3 main monetization channels (Todd, feel free to add more if I missed any)
MVPD up-sell: Fox will be able to use AIQ to identify inappropriate account sharing devices and convert them to paying MVPD subs, or incremental payment as a sub account.
Fox needs to work with MVPDS to create an affiliate program specific to agreed upon scenarios.
They need to agree on what the risk profile should be, what the messages should be, what the up-sell package is, etc.
 In reality, this could be a year before they agree with the first MVPD, and many years before all the major MVPDs are on board.
 D2C up-sell: Fox will be able to use AIQ to identify inappropriate account sharing devices and convert them to paying D2C subs.
Fox needs to launch there D2C offering, then get permission from the MVPDs to send D2C up-sell messages.
Realistically we are 18 months out for that to happen.
Marketing messages: By ingesting AIQ data, Fox will be able to improve viewer profiles for advanced marketing messages.
 Fox and Adobe need an API integration so AIQ data can be ingested into Fox platform for marketing purposes.  
This may be the lowest hanging fruit, but is not as valuable as the two channels above.  I would estimate 25% of the total value of our offering can be applied to this.
My take on Ariff’s feedback on the $1.2M price tag was that if all of the above happen, it may be worth $1.2M a year. But in order for Fox to get to that place, they need to do a starter deal that would include quarterly reports, access to the dashboard, and ability to test via integrations with their marketing platforms. They are willing to pay, but in order to get them to the price point we want, we need to do a better job of selling them on the future value/investment. They will need to come up from $0, but we will need to come down from $200K

 
Given the above, my recommendation would be to ask them for a $120K starter investment to include the following:

Custom algorithms based on criteria important to Fox
4 quarterly reports over the next year.
Access to the dashboard for 6 months (as is with no customization guaranteed unless they pay extra for acceleration)
Integration testing with Fox marketing platforms

 
By Jan 2019, we should have a good sense of if our platform can feed into theirs to better inform marketing messages. They will have a better idea of their D2C offering. They will have started conversations with MVPDs on how to jointly up-sell, and we will have a much better view on executing monetization channels. At this point, we will be ready to go back to them with a $1.2M+ price tag for version 1.











Comcast - 3/9/2018
Here are my notes from today’s meeting with Comcast

Attn: Ellen Serling + Horia, Todd
Deck - https://www.dropbox.com/s/2x4ks997lqfw9t2/Account%20IQ%20Customer%20Validation%200.3%20Comcast.pptx?dl=0
Executive Summary

As expected, Comcast is very focused on this problem but they’re solving it with internal resources and don’t seem to need Adobe’s help for now
They’re the most advanced right now since they’re running analysis as well as reaching to customers/adding tools. But it’s still early days, they don’t have a cookbook yet, they’re playing around
They would love to convert users but are not sure conversion will actually work – need data to be convinced
Data sharing with Comcast will be very hard. Since they don’t actually provide a user ID across the board even when we sell the product to Programmers we won’t be able to have a good analysis for Comcast
Problem

Kids that are still 100% dependent on parents (daughter in college) should be allowed to use parent’s subscription. But once you have a job/move out you should buy your own
Some OTT providers have encouraged sharing – share as much as you’d like as long as you don’t go over your concurrency limit
Priority
Pretty high, 4 or 5
However, there are a lot of other 4 and 5s
Kodi box has started to become a big problem in the last years (note: you can very easily watch high quality pirated streams – so it’s a security issue that doesn’t even involve sharing credentials)
Is it a security or lost revenue problem?
Mix of both – it’s a high priority for the video team but the security team is also very involved
Recent analysis?
Yes, they’re running analysis but they’re not at liberty to share results
Continuing to monitor
What are you doing today?
Concurrency Monitoring, reaching out to specific accounts
Plus looking into other techniques that are no so invasive such as sign them out, reset password
Moving into more complex ones – reduce TTL, 2nd factor authentication
Automatic and manual process? A bit of both
UX experience
It matters a lot, don’t want to get customers frustrated
Product

Conversion?
That’s the dream. Is it realistic though? Are those customers that are paying nothing going to pay for anything?
They have a small package – Xfinity Instant TV that’s now rolled out nationally
Reports/Rules/Conversion
Pretty much on the same page
1 - get your arms around the problem, monitor it, see if your tactics work
2 – sending an email is not going to do much. The user probably knows that they’ve shared the account, they’ll just laugh about it. What are the tactics that are going to work? It’s hard
They would like to have a set of rules that they publish
$100 test
Not a clear answer – definitely more reporting initially with conversion maybe in 2 years
They want data in order to move into the conversion area. They won’t significantly invest until they have some indication that conversion is successful
Will the user convert to Xfinity or DirecTV Now?
Data sharing
Comcast is VERY sensitive about data, that’s been their policy all along. Not sure what the limits are
A lot of high up groups would have to get involved to make data transfer a reality
Question – how can you understand in-home consumption if that will happen on the STB? A lot of users only use TVE for outside the home
What is the data team using for account sharing analysis?
Not sure but it’s a significant team, they probably use multiple tools
Scenario for security team – account takeover, they’re very concerned about that. The attacker can create sub-accounts and also do a lot of damage
Final

Rank from 1 to 10? It’s in the lower end (Horia note: 3?) because they’re building a lot in house
But they don’t have all the things they need so the door is not closed. Cost, investment, data sharing – all will play a factor in their decision


AT&T / DirecTV
Horia's notes from meeting with AT&T(DirecTV)

Attn:

Julie Waring – leads the overall global fraud group
Riordan Robinson – leads the DirecTV specific fraud in the overall fraud group
Shawn Fried – Director Video product management
Zalina Visentin – PM working for Shawn
Steve Dulac – Engineering/Architecture group, helps the fraud team meets its goals
Todd (presenter), Horia, Calin
 

Executive summary

Shorter meeting (30’) due to conflicts on their side – but we had the right people in themeeting
DirecTV/AT&T is very different than other MVPDs – don’t care so much about account sharing per se, only if it impacts security/privacy
It becomes interesting if it’s tied to security OR if they can monetize
Want to see the demo, engage further
 

Problem discussion

Riordan: It’s a 1 or 2 (from 5), sharing is happening at some scale but it doesn’t have the attention it has at other companies
DirecTV Now is new so they’re not at the point where Netflix is
Shawn: I agree that 1 or 2 is right. It’s a leading question btw (problem) – they don’t necesarily think of it as a problem
No executive attention right now but that can change if they can prove they can monetize it
It’s different than what Charter is doing
 

#1 thing for them – customer data and privacy
Account sharing has some impact to this but not massive. If it were a big impact on privacy/security then it would be a bigger problem right now
Two flavours of sharing get different attention
friendly – friends family
stolen – need to protect these accounts, cyber fraud
Evolving business needs
First, customer security
Second, if account sharing is rampant and we can monetize maybe we’re interested
Interacting with customers on a case by case
They are thinking about increasing the number of concurrent streams the customer has (Netflix model)
Julie/Riordan are the key people to engage
There’s been a couple of years since they did an analysis, it would be nice to get new data
Shawn – make sure that you don’t share with Disney data that doesn’t belong to them – it’s OK to aggregate but only if the user visited Disney at least once.
Shawn’s analogy “give a credit score for every customer that comes into the bank. but you have to walk through the door to get it”
 

Parting thoughts

Interesting, deserves a follow-up, it’s important enough for it
 

Next steps

Schedule the demo


FOX
AIQ-Fox meeting

Attendees :
Fox:  Anne Y., Ryan B., MichelleG, Eduard F , Aaron T, Sanam J. (and other2-3)

Adobe: Todd (presenter) , Calin, Costi (listening)

 
Executive Summary

Lot of interest. 
They asked a lot of on the spot questions, my perception was that they are really keen to find a solution even they are not very sure how this solution should look.
They have sr executive level for this problem - accounts fraud/sharing
They already have a hi level image about what means to "act" on the frauds - email, up-sell, limit the no of streams.
They asked many times to see the real product/prototype
definitely will follow up for another meeting - for a prototype demo with their real data

 Notes:

Definitely a problem, executive level, they want to mitigate the impact 
A lot of discussions about - where this problem should be addressed ? - at the MVPD level?
They are looking in the market for a common understanding , common practices - limit the number of streams, devices
Asked about where we are with the development of the solution, and if they can see it
The limit of devices - maybe this is not the real solution , but to upsell, an additional account 
$100 test - they denied to respond, not enough info
they were really interested in benchmarking 
interested in segmentation (age, sex, demographics) of the sharing/fraudulent accounts 
very interested about the risk index 
asked about - what exactly do you understand by rules ? 
sharing data - initially concerned - but looks like they where ok after Todd explained them the benefits and how this actually works
asked again to see the prototype






Disney/ESPN - 3/2/2018


Here are my notes from today’s meeting with Disney/ESPN

Attn: Julius Lee, Andy Cochran, Flora Kelly, Daniel Castro, Timothy Bayus, Gabi Widder  + Horia, Todd
Deck -https://www.dropbox.com/s/mux0el4fgc4s6rz/Account%20IQ%20Customer%20Validation%200.3%20Disney.pptx?dl=0
Executive Summary

It’s an important problem for them, getting significant executive attention.
They want to understand how this would work between Programmers/MVPDs/Adobe – they feel they don’t have the rights to do any rules or conversion, data rights seemed complex <– this might be a significant issue
Due to this they would much rather push the MVPDs to solve this and they would stick to reports
99% was only Julius talking. Analytics team was very silent even when asked directly by us or Julius.
Overall, not a great meeting – they were interested, it is important, but feels like we’re far from something that would be in production. Might change this once we have real reports.
Problem

Solving account sharing is a high priority within TVE. It’s balanced out by their efforts to reduced friction for sign-in
Julius would rate it at 3 or 4 importance (out of 5)
It gets a lot of executive attention
Justin Connolly (EVP) who leads the group that Julius is in was quoted in the Bloomberg article saying that we must solve this
Their execs have joined an NCTA committee to solve account sharing
Definitely getting a lot of executive attention
Is it a revenue problem or a security problem?
Mix of both. It’s hard to quantify since they don’t know.
They do want their content to be secure
Any analysis today?
They do a lot with Nielsen especially on OTT usage for Watch ESPN
Also did out of network usage analysis
Looked at number of devices etc. – but that’s about the extent of their ability
What are you doing to combat fraud today?
Concurrency Monitoring (with Adobe), lowered the threshold from 5 to 3 concurrent streams for ESPN
Engaged in the Charter authentication principles – might be something they push other MVPDs to do as well
Hulu is also doing a lot more on their side
They are trying to get a lot more info from the MVPDs around the rules they have on their side (limitations on the number of devices etc)
Are you afraid of the bad UX and feedback it will generate from the users?
Yes, especially when there are problems like Charter TV customers who don’t have internet from Charter – need to have a solution there as well
But overall they are willing to try, see what the results are.
No solution will be perfect
Are you looking for an industry wide agreement?
Yes, that’s the holy grail – but it’s not going to happen, it’s not realistic
Metrics on your end?
Analytics said that they’ve seen about 1/3 of users claiming they use passwords – similar to our reports. No other data
On the “willingness to buy without a password” Julius asked if we have a breakdown by TVE vs. SVOD
The idea is that a lot of users would buy – but would they buy a $10 Netflix subscription or a $120 Comcast subscription? Vastly different numbers probably
Who pays for cable now?
Account IQ

A lot of discussions around the conversion part
They were asking if they could identify the device so they can target a campaign (yes) but wondering if they have the rights to do that
Would rather see MVPDs going for rules and conversion – they would be happy just to pass the data to them. But are afraid different MVPDs will want different things so it will be a lot of work
It’s a long road for ESPN/Disney to get MVPDs to allow them to do a lot of these things
Julius needs to talk to privacy/legal to figure out if they can convert users. There are some cases where maybe they could (Todd’s idea to convert only users out of the MVPDs footprint)
Generally like the idea of having an Adobe ID for every person that’s behind the account – once the legal/privacy discussion is over
Didn’t answer the $100 test for reports/rules/conversion
Have to think about it
Feel like conversion is an MVPD thing
Get data from MVPDs – it’s possible if they give something in exchange, it’s a negotiation
Maybe they can convince the MVPDs to buy Account IQ
They raised the possibility of us using the federated Analytics data to get MVPD insights – but need to check with legal
Would you like raw data and/or Analytics? Both probably. Analytics team would just use the reports but there’s a data team that would love to have it in their data warehouse
Final score

Would you buy this from Adobe (1 to 10)?
Not sure how to answer that question
It’s complicated because it’s a mix of MVPD/Programmer data rights
Next steps

They would love to see the POC once it’s done
Figure out how to work with all the parties








Cox - 2/14/2018


From Horia

Attn:  Pujan Roka (Director of Product Dev & Mgmt at Cox Communications); Kristen Cuffee-Brown (Director, Video Product Management) + Todd, Calin, Horia
Deck that we used - https://www.dropbox.com/s/5yij4o1bt6pomue/Account%20IQ%20Customer%20Validation%200.2%20Cox.pptx?dl=0
Executive summary

Cox is not convinced account sharing is a big problem but they’re getting pushed to do something about it
They are very careful in messaging customer (or acting on them in any way)
They see a lot of value in reports and would purchase a product that helps them understand account sharing in a basic way
Once they’re confident enough they’ll move to rules and later conversion
Problem

Based on their analysis account sharing is really low. But networks are pushing them to solve this problem claiming that there are a lot of accounts being shared (ESPN)
They did a small analysis on the subset of ESPN users that were using them outside of network (Houston and Denver) and didn’t see a lot of fraud
There’s no industry alignment on how to treat fraud – for example, if your daughter goes to college it’s not really fraud for Cox. Once she gets a paying job and it’s no longer living at home it’s a different story but not before.
From the MVPD perspective, they see the loss in market share, it’s a brutal market right now especially with virtual MVPDs coming in
Cox is hyper focused on retention
It would be fantastic to get data that they’re losing revenue due to account sharing – if they get that they can put together a business case to solve this problem, but not until then
They’re very very careful with customer touches – anything that gets customers to rethink their Cox subscription is very dangerous so they limit their communication (even things like “upgrade to digital”)
How are you dealing with account sharing today?
They currently have a 5 streams limit for Cox apps – not across TVE.
They don’t reach out to users about shared accounts
Quote “Netflix made a business out of this by selling extra streams”
Is there a correlation between account sharing and cord cutting? They don’t know, they have no evidence on that
They would love to just understand when a violation occurred – let’s start there
Kristen is proposing we follow a crawl / walk / run model (understand/act/convert)
They don’t want to piss off customers, they can easily go to a competitor (YouTube, Hulu etc.)
Maybe if we detect that this user is always out of market after a while you become confident enough to message them. They want to be 100% sure before they act
Kristen thinks that the whole process of who gets messaged and how you can convert users is very complicated. How do you know you’re reaching out to the owner or the user of the shared account? It’s complex. (Horia note: we need to simplify this flow)
Pujan wants to solve the ESPN use-case – top out of market users for Cox for one month – export to a list so he can message them. This can be done using the POC.
Product feedback (only Pujan as Kirsten had to leave)

They ideally would love to have both data sets – but Cox would probably never approve their data to go to Adobe. A lot of sensitivity.
Ideally this sits on top of their IDP software and has both Cox and Adobe data and a way to message users
He would love to have a dashboard where he can select different markets and do a deep dive on both Cox and Adobe data
Basic metrics seem to be good enough for them. Maybe after a while they’ll want some of the advanced functionality
Horia note: seems they want the raw export (raw data + our intelligence)
A fraud analyst should look not just at geo but at repeated offenders (Horia: new concept) – for example somebody who was in Houston for 10 months, there’s no way they’re not fraudulent (since Houston is not a Cox market)
Once they grow more confident they can act upon yellow users, not just red ones (slide 1 from the deck)
$100 tests

Today - $80 reporting, $20 rules, $0 conversion. In 2 years, probably  $75 reporting, $15 rules, 10% conversion
Reports - $90 on basic, $10 on advanced (for now)
Final score

How likely are you to buy this product from Adobe? Value is there, they will consider build vs. buy but it seems it’s more of a buy decision in this case. Depends on the price tag but it’s a 9-10 (out of 10) for them.
Horia’s note: The grade is for a reduced version of the product – basic reports, some intelligent reports, some rules but not a lot and no conversion
Next steps:

Engage with them once the POC is ready


From Calin

Kristen, Cox

for us the sharing problem is very low in this moment, even that what we hear from networks, that are pushing us, is the opposite.
our focus is on retention because -
 if somebody can provide us data about losing revenue and an opportunity to change this, we'll have more attention on this, for sure.
if we can see numbers, the numbers will speak and we'll engage.
conversion - I don't how you will do that, it's very tricky. we don't want to look like big brother. (my comment here : the tone was optimistic and unbelieving, not rejecting and skeptical)
we need to be very careful with existing customers, for all the touch points, to do not upset them. they can leave, the competition is brutal these days. 
Pujan, Cox

would be nice to see, if an account is for a long period used outside the footprint, that it becomes red. we know for sure that this is an offender. it can be initially yellow, because this is a presumptive offender and after a certain amount of time, some months, it will become red, because now we know this is an offender.
(Would you buy/co-develop this product?) From the MVPD pov this definitely have value, but depends on the price tag. 
$100 tests - My comment - on both $100 tests the value placed on conversion was minimal. They are mostly interested in "understanding" the size of the sharing problem and the potential revenue loss.