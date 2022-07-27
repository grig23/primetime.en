<table data-cellpadding="5" data-cellspacing="5">
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><img src="https://dzf8vqv24eqhg.cloudfront.net/userfiles/258/326/ckfinder/images/PT_Logo_80x80.gif?dc=201503162105-4" /></td>
<td><p> </p>
<h1 id="programmer-kickstart-guide"><span style="font-family: arial, helvetica, sans-serif; ">Programmer Kickstart Guide</span></h1></td>
</tr>
</tbody>
</table>

 

  - [Introduction](#intro)
  - [Release Schedule](#release_schedule)
  - [Support Documentation](#support_docs)
  - [Test Environment Setup](#support_docs)
  - [Setup with MVPD](#setup_mvpd)
  - [Related Information](#related)

<span style="color:#c0392b;">**Notice**: The content on this page is
provided for information purposes only. Usage of this API requires a
current license from Adobe. No unauthorized use is permitted.</span>

-----

## <span id="intro"></span>Introduction

Welcome to Adobe Primetime authentication for TV Everywhere. We look
forward to working with you.

 

Note:  This is the Kickstart Guide for Programmers (content providers).
 If you are with a Multi-channel Video Programming Distributor (MVPD),
please be sure to see the [MVPD Kickstart Guide](#).

  
Adobe Primetime authentication contacts:

  - Support – for all questions, incidents or feature requests –
    tve-support at adobe.com
  - An Enablement contact will be assigned to your project by the time
    of your project kickoff.

 

The following information outlines some important first steps to get us
off to a solid and efficient start. The goal is to provide an
explanation and expectation about how we will work with partners to
achieve integrations. Please note the “you will provide” / “Adobe will
provide” sections below for each item. These are listed by way of a
checklist, or guide as we work through the project.  
  
This document assumes that programmers are signed up to work with a
chosen MVPD partner.

## <span id="release_schedule"></span>Release Schedule

The Adobe sprint development cycle is planned out so that you can see
when our releases are scheduled and how each release gets promoted
through our development system.  
  
After each sprint is complete it is available for QE, or to see new
implementations on our UAT server.  
  
Approximately every 6 weeks a release will be made to the Adobe
Pre-Qualification server. (This is the server where we hold our proposed
next release while carrying out final QE.) These builds will include all
work completed in sprints since the last drop. A two week QE window is
available at this time for partners to test this release.

 

Assuming no critical issues arose during the preceding two-week testing
window, the release will be promoted to live production. This means that
the integration will be available in the Adobe Release environment, but
partners choose when they make the release public.

 

For the latest release schedule information, see the [Release
Calendar](#).

## <span id="support_docs"></span>Support Documentation

<span style="background-color:#afeeee;">Adobe will provide:</span>

1.  Deployment Guide:
     https://tve.zendesk.com/entries/498741-tve-deployment-guide
2.  Access to our Zendesk customer support system. This is also where
    you can find samples, information and video tutorials on some of the
    processes. In order to access this document on Zendesk, along with
    other documents posted there, you will have to register and create
    an account at <https://tve.zendesk.com/home> There is no limit to
    the amount of users you can register.  You able to see and
    share comments on any filed ticket. All support questions should be
    addressed to <tve-support@adobe.com>.
3.  Programmer Integration Guide
     ([http://tve.helpdocsonline.com/\#introduction-to-programmer-integration](#))
4.  Media Token Verifier Library:
     https://tve.zendesk.com/entries/471323-media-token-validator-library.

## <span id="test_env"></span>Test Environment Setup

Adobe will first set you up with the Adobe test site, where Adobe acts
as an MVPD for test purposes. Your team can then set up a test website
that calls the Adobe API. Use the default MVPD selector, and select
“Adobe” as the idP.   
  
<span style="background-color:#ffd700;">You will provide:</span>

1.  Requestor ID. This is a string that will uniquely identify the brand
    of the website or the application that is making requests to Adobe
    Primetime authentication. The string itself is arbitrary but needs
    to be agreed between Adobe and the Programmer
2.  Channel information. This is a set of strings that identifies the
    content channel(s) being requested by the requestor ID. In many
    cases the channel and the Requestor ID are the same. You may however
    have multiple channels of content that can be requested by the same
    ID. Channel name strings should correspond to the cable TV channels.
    Some MVPDs will validate this value over the AuthN and/or AuthZ
    protocol.
3.  Domain names (to be allowed for that requestor ID). This will be a
    list of actual domain names that will be listed by Adobe to accept
    the requestor ID. This ensures that only your approved domains have
    access to Adobe Primetime authentication with your metadata. NOTE:
    domain names valid for production may be different for
    testing/staging and both should be provided and identified.

  
<span style="background-color:#afeeee;">Adobe will set up the account
and Adobe will provide:</span>

  - Login and password to access the test site

## <span id="setup_mvpd"></span>Setup with MVPD

This section describes what you need when you migrate from the Adobe
test site to work with an MVPD.  
  
<span style="background-color:#ffd700;">You will provide (via
MVPD):</span>

  - **Two sets of credentials**:
      - AuthN + AuthZ : login/password for a user which is authenticated
        and authorized
      - AuthN + Non-AuthZ : login/password for a user which is
        authenticated but not authorized

 

  - **Resource ID.** This is a specific content identifier that will be
    validated with an MVPD over the AuthZ protocol. This can be at the
    channel, show, episode, or asset level; it should be agreed upon
    with your MVPD.

  
Adobe Primetime authentication supports an MRSS-based metadata schema
which means that Resource IDs can be as specific as needed, and can
include identifiers that may be unique to a specific MVPD.  
  
**NEW MVPD integration:** It is important to remember that your chosen
MVPD plays an integral part in completing any integration. Adobe needs
to write code for each MVPD according to their specs. Until these steps
are complete, you will not be able to select that MVPD from the dialog,
or complete your product testing. Adobe needs to schedule this work in
advance to fit with the next available sprint. (For current schedule
information, refer to the [Release Calendar](#).)  
  
**Existing MVPD integrations:** If your chosen MVPD is already set up
with Adobe then the connectivity steps should be much simpler (faster),
and often connectivity can be achieved by way of configuration changes. 

 

Note: the MVPD will STILL have to enable the Programmer, and sign off on
any relevant business deals.  
  
**QE with MVPDs:** All integrations will involve joint QE, and since the
end user is ultimately a customer of the MVPD, many have set test cycles
prior to pushing “live”. Since this involves scheduling of MVPD
resources, this is a potential area for delay.

-----

## <span style="font-family: arial,helvetica,sans-serif;"><span id="related"></span>Related Topics</span>

  - <span style="font-family: arial,helvetica,sans-serif;">[MVPD
    Kickstart Guide](#)</span>
