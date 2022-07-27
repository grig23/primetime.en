<table data-cellpadding="5" data-cellspacing="5">
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><img src="https://dzf8vqv24eqhg.cloudfront.net/userfiles/258/326/ckfinder/images/PT_Logo_80x80.gif?dc=201503162105-4" /></td>
<td><h1 id="mvpd-direct-integration-plan">MVPD Direct Integration Plan</h1></td>
</tr>
</tbody>
</table>

  - [Introduction](#introduction)

<!-- end list -->

1.  [Kick-off Meetings](#kick-off)
2.  [Features](#follow-up)
3.  [Metadata exchange](#metadata-xchg)
4.  [Allow IP list](#whitelist)
5.  [Development](#development)
6.  [Adobe Environments](#environments)
7.  [Staging Deployment](#staging)
8.  [Test and Troubleshoot](#test_troubleshoot)
9.  [Production Deployment](#production_deployment)
10. [Escalation Procedures](#escalation)

<!-- end list -->

  - [Related Information](#related)

<span style="color:#c0392b;">**Notice**: The content on this page is
provided for information purposes only. Usage of this API requires a
current license from Adobe. No unauthorized use is permitted.</span>

-----

## <span id="introduction">Introduction</span>

Welcome to Adobe Primetime authentication for TV Everywhere.  We look
forward to working with you.

 

This is the Kickstart Guide for Multichannel Video Programming
Distributors (MVPDs).  If you are a Programmer (content provider), see
the [Programmers Kickstart Guide](#).

 

Support is available at all times through the Primetime authentication
ticket system on [Zendesk](https://tve.zendesk.com/home). This is also
where you can find samples, documentation, and video tutorials for our
processes. In order to use Zendesk, you will have to register and create
an account at <https://tve.zendesk.com/home>. There is no limit to the
amount of users you can register and who can see or post comments on a
filed ticket. All support questions should be addressed to: tve-support
at adobe.com  
   
**Team contacts:**

  - **Support** – For all questions, incidents, or feature requests
    – tve-support at adobe.com

-----

This document presents an action plan for a direct integration
between an MVPD and Primetime authentication. The steps below
provide information about different aspects of Primetime
authentication: environments, supported features, the API test tool,
ticketing system, and more.

## **<span id="kick-off"></span>1. Kick-off Meetings**

The scope for these meetings is the start of technical discussions
between Adobe and the MVPD. At this point of the process, documentation
needs to be shared from both sides. <span style="line-height: 1.6em;">As
a follow up, Adobe needs to open a ticket in our ticketing system
(</span>[<span class="s1" style="line-height: 1.6em;">https://tve.zendesk.com/</span>](https://tve.zendesk.com/)<span style="line-height: 1.6em;">)
to track the status of the integration. </span>

## **<span id="follow-up"></span>2. Features**

Adobe will set up a weekly status call to discuss and track the overall
schedule, steps, timeline, and implementation details of the
integration. In this phase, Adobe does a review of the MVPD's
specifications. The result of this should be a spec page that details
all of the features needed by the MVPD. The MVPD will send Adobe a
specification document, detailing the MVPD's authentication /
authorization implementation.  
   
Items to clarify - see MVPD Integration
Features: [https://tve.helpdocsonline.com/\#mvpd-integration-requirements](#)  
   
There are several settings that will need to be described in detail at
this point:

  - **MVPD's logo URL** - This is a file with the following dimensions:
    112 x 33 pixels. The logo is displayed by Programmers on their sites
    when the user clicks on the “Sign in” button to select their Pay TV
    provider. 
  - **TTL** **(time-to-live) Values** - The TTL typically is set by the
    MVPD during the authentication/authorization process. However Adobe
    can override those TTL values and provide different values depending
    on what is agreed upon by both the Programmer and the MVPD. 
  - **Display name** - This is displayed by Programmers on their sites
    when the user clicks on the “Sign in” button to select their Pay TV
    provider. 
  - **Test credentials** - Both profiles (staging and production) should
    have a list of test credentials.

 

**Important**

<span style="line-height: 19px;"><span style="background-color:#FFFF00;">Each
time a user will initiate an entitlement flow he will be associated with
a single, opaque, unique user ID.  The
</span></span>**<span style="background-color:#FFFF00;">user
ID</span>**<span style="line-height: 19px;"><span style="background-color:#FFFF00;"> is used
to identify the user of a Programmer's app, but originates from the
MVPD.</span></span>

<span style="background-color:#FFFF00;">An important notice for each
MVPD: the user ID should
</span>**<span style="background-color:#FFFF00;">NOT</span>**<span style="background-color:#FFFF00;">
contain any
</span>**<span style="background-color:#FFFF00;">PII</span>**<span style="background-color:#FFFF00;">
(Personally Identifiable Information), information that can be used on
its own or with other information to identify, contact, or locate the
user.</span>  

 

## **<span id="metadata-xchg"></span>3. Metadata Exchange**

The two sides need to exchange the metadata for all environments
involved (production, staging, etc.).

  - ***Adobe*** 
      - For the staging environment Adobe’s SP metadata can be retrieved
        from: <https://sp.auth-staging.adobe.com/sp/metadata>
      - For the production environment Adobe’s SP metadata can be
        retrieved from: <https://sp.auth.adobe.com/sp/metadata>
  - ***MVPD*** 
      - To add metadata (staging/production).

## **<span id="whitelist"></span>4. Whitelist IP List**

The following IPs should be whitelisted in the MVPD's firewall. Please
contact Adobe for the list of IPs.

 

Primetime authentication requires that firewalls be opened on ports 80
and 443, for allowing access to restricted resources. 

 

The MVPD needs to add a list of IP addresses for authentication and
authorization servers (if this is the case).

## **<span id="development"></span>5. Development**

The duration of the development phase will be determined after reviewing
the specifications, and taking into consideration the items the two
sides sign off on. Adobe needs to write custom code for the
authorization part. 

 

Note that authorization is performed per resource. The authorization
transaction is typically performed with an ID string, passed from the
Programmer’s site, representing the channel for which the user is
requesting authorization. This Resource ID is established between the
Programmer and MVPD and can be as granular as necessary.

 

## <span id="environments">6. Adobe Environments</span>

Adobe provides different environments for different stages of the
development process:

  - **Prequalification** (*PRE-QUAL*): The PRE-QUAL environment contains
    the next release candidate. Adobe initially integrates new partners
    in this environment, before upgrading the integration to the Release
    environment. Partners have two weeks to test on the PRE‐QUAL
    environment and must explicitly request any changes to the PRE-QUAL
    configuration (contact your Adobe representative for details on the
    change request process). Bug fixes trigger new deployments in this
    environment.
  - **Release **(*RELEASE*): Adobe’s current production build is
    deployed to a live environment here.

 

More info on how to use Adobe's environments: [Understanding the Adobe
Environments](#)

## **<span id="staging"></span>7. Staging Deployment**

Based on the metadata received from the MVPD, Adobe will create and
configure a new MVPD in the Primetime authentication system. This will
be deployed in Adobe's prequal staging environment, and will be
configured with our test Programmer (TestDistributors).   
   
The MVPD needs to do the same deployment in their QA/staging/test
environment.

## **<span id="test_troubleshoot"></span>8. Test and Troubleshoot**

In this phase, Adobe and the MVPD test and troubleshoot the integration.
To help test the integration, the Primetime authentication team can use
Adobe's API test site. More information on how to do that [can be found
here.](#)

 

When testing and troubleshooting has concluded successfully, the
integration is enabled in Adobe's release staging environment. At this
point, Adobe can integrate the MVPD with an actual programmer. 

## **<span id="production_deployment"></span>9. Production Deployment**

  - The MVPD needs to deploy **first** in the production profile, in
    order to test the connectivity. 

  - Adobe deploys in prequal production. 

  - All parties can now test in the production profile. 

  - If everything is ok at this point, Adobe can move the integration to
    the release production environment (“live”), which is available to
    all users.

## <span id="escalation">10. Escalation Procedures</span>

Once the integration is live in production it is critical to provide the
best customer experience. To ensure the best response in the case of a
server down issue, MVPDs must provide escalation procedure documentation
for issues brought to Adobe’s attention.

 

In turn, Adobe supplies MVPDs with the most current Primetime
authentication escalation process.

-----

## <span id="related"></span>Related Information

  - [Programmer Kickstart Guide](#)
  - [MVPD Integration Guide](#)
