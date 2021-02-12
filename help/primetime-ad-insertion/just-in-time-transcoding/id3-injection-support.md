---
description: Just-in-time-transcoding can inject ID3 timed metadata into ad creatives to facilitate client-side ad tracking.
seo-description: Just-in-time-transcoding can inject ID3 timed metadata into HLS format ad creatives to facilitate client-side ad tracking.
seo-title: Using just-in-time-transcoding to Inject ID3 Timed Metadata Tags
title: Using just-in-time-transcoding to Inject ID3 Timed Metadata Tags
uuid: 491bbb9e-15de-4871-baa1-f7bb0ea0dde2
---

# Using Just-in-Time Transcoding to Inject ID3 Timed Metadata Tags {#using-crs-to-inject-id-timed-metadata-tags}

CRS can inject ID3 timed metadata into ad creatives to facilitate client-side ad tracking.

The client player reads the ID3 metadata to enable frame-accurate ad tracking.

>[!NOTE]
>
>ID3 timed metadata injection functions only for Safari/iOS.

## Workflow for CRS for ID3 Injection {#workflow-for-crs-for-id3-injection}

If Primetime Ad Insertion receives the `ptplayer=ios-mobileweb` parameter, it will inject ID3 packets into the transcoded ad creative before uploading to the appropriate ad storage CDN.
