---
title: Account IQ get started with account IQ, prerequisites and onboarding
description: How to onboard, prerequisites, and getting started with the Account IQ. 
---

# How to get started with the Account IQ {#onboarding}

## Prerequisites {#prerequisites}

* The organization must be registered in [!DNL Adobe Marketing Cloud] organizations.

* Users in that org should be assigned to either TVE Dashboard Read-Write or TVE Dashboard Read-Only.

### Browser prerequisites {#browser-prerequisites}

The Account IQ is a hosted web service. It is compatible with the most recent version of the following browsers:

* Google Chrome
* Mozilla Firefox
* Safari version

 these user groups set dma_primetime product context for the user accounts. In AIQ code we’re checking for this product context when providing access. Internally, in the code we have an additional condition: the org id should be whitelisted in order for the users to get access to their data.
This is what we have at the moment. The plan is to get rid of dma_primetime check and have a dedicated profile for AIQ. The users who need to have access to the console would need that user profile. This is however not implemented at the moment.