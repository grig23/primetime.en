---
title: Account IQ get started with account IQ, prerequisites and onboarding
description: How to onboard, prerequisites, and getting started with the Account IQ. 
---

# How to get started with the Account IQ {#onboarding}

Read on to know the prerequisites to use Account IQ and how can your company onboard to begin looking at the account sharing scores of subscribers.

## Prerequisites {#prerequisites}

* The organization must be registered in [!DNL Adobe Marketing Cloud] organizations.

* Users in that organization should be assigned to either TVE Dashboard Read-Write or TVE Dashboard Read-Only.

### Browser prerequisites {#browser-prerequisites}

The Account IQ is a hosted web service. It is compatible with the most recent version of the following browsers:

* Google Chrome
* Mozilla Firefox
* Safari version

### How to onboard organizations on Account IQ? {#steps-to-onboard}
 

This is what we have at the moment. The plan is to get rid of dma_primetime check and have a dedicated profile for AIQ. The users who need to have access to the console would need that user profile. This is however not implemented at the moment.

1. Having their org onboarded in Adobe Marketing Cloud
@Eric or @Peter, can you take this.  I think it’s now called “Experience Cloud”, but that’s minor.  Is there more detail to this? Is this managed by another group? If so, do we provide a link, contact, etc.? This should also contain a caveat about checking if their org is already part of Experience Cloud.
 
2. Having “TVE Dashboard Read-Write” or “TVE Dashboard Read Only” profiles assigned to their users in http://adminconsole.adobe.com/.
@Eric, do you know how to do this?  Are there sub-steps?  Can we explain to customers why they’d chose Read-Write vs Read-Only?
@Cristina, can you provide a short explanation that this is a temporary approach and maybe how it will work in the next version?
 
3. Having their org id whitelisted on AIQ side
@Cristina, is there a process that we can put in place to manage this?  For example, send an email to “DL-AdobePass-Eng AdobePass-Eng@adobe.com” with the org’s org ID, etc.

<!-- these user groups set dma_primetime product context for the user accounts. In AIQ code we’re checking for this product context when providing access. Internally, in the code we have an additional condition: the org id should be whitelisted in order for the users to get access to their data. -->