---
description: CRS can inject ID3 timed metadata into HLS format ad creatives to facilitate client-side ad tracking.
seo-description: CRS can inject ID3 timed metadata into HLS format ad creatives to facilitate client-side ad tracking.
seo-title: Using CRS to Inject ID3 Timed Metadata Tags
title: Using CRS to Inject ID3 Timed Metadata Tags
uuid: 491bbb9e-15de-4871-baa1-f7bb0ea0dde2
index: y
internal: n
snippet: y
---

# Using CRS to Inject ID3 Timed Metadata Tags{#using-crs-to-inject-id-timed-metadata-tags}

CRS can inject ID3 timed metadata into HLS format ad creatives to facilitate client-side ad tracking.

The client player reads the ID3 metadata to enable frame-accurate ad tracking. 

>[!NOTE]
>
>ID3 timed metadata injection works only on Safari on iOS.

**Workflow for CRS for ID3 Injection**

The workflow for ID3 injection is the same as in [Detailed Workflows for JIT Repackaging.](../creative-repackaging-service/jit-repackage.md) If the manifest server receives the `ptplayer=ios-mobileweb` parameter, it tells CRS to inject ID3 packets into the transcoded ad creative before uploading it to the CDN server.

>[!NOTE]
>
>In a multi-CDN setup, the manifest server uses the `ptcdn` parameter in the bootstrap URL to identify the CDN server to upload the ad creative.
