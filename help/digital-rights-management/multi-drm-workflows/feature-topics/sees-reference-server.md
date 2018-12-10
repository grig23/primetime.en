---
description: One way to coordinate licensing and policy enforcement is to build these functions in to an entitlement server. Adobe provides the SEES reference entitlement server that you can work with to build your own server.
seo-description: One way to coordinate licensing and policy enforcement is to build these functions in to an entitlement server. Adobe provides the SEES reference entitlement server that you can work with to build your own server.
seo-title: Reference Server  Sample ExpressPlay Entitlement Server (SEES)
title: Reference Server  Sample ExpressPlay Entitlement Server (SEES)
uuid: 9b5e5e8f-2d0d-422f-ae24-e7ccbfe03df5
index: y
internal: n
snippet: y
---

# Reference Server: Sample ExpressPlay Entitlement Server (SEES){#reference-server-sample-expressplay-entitlement-server-sees}

One way to coordinate licensing and policy enforcement is to build these functions in to an entitlement server. Adobe provides the SEES reference entitlement server that you can work with to build your own server.

The reference server SEES demonstrates the ExpressPlay Entitlement Service, showing two services: basic time-based entitlement and device binding entitlement.

The SEES is built on top of two ExpressPlay Fairplay Services:

1. Expressplay Token Request Service
1. Expressplay Record Retrieving Service

The URL format for the ExpressPlay Token request takes two forms, one for production, one for the test environment:

**Production**: https://fp-gen.{prod_domain}/hms/fp/token

**Test**: https://fp-gen.test.expressplay.com/hms/fp/token

The URL format for ExpressPlay Record retrieving takes two forms, one for production, one for the test environment:

**Production**: https://api.{prod_domain}/cmiapi/getrecord/

**Test**: https://api.test.expressplay.com/cmiapi/getrecord/