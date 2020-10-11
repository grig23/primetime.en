---
title: Get started with Adobe Primetime Ad Insertion
description: Getting started with Adobe Primetime Ad Insertion
---

# Get started with Adobe Primetime Ad Insertion {#ptai-get-started}

Primetime Ad Insertion co-ordinates the systems that provide content and ads to create personalized, in-stream ad experiences and then track ad playback for your advertisers.

Primetime Ad Insertion interacts with video-delivery client applications by re-writing video manifests to provide targeted ads and personalized experiences for each viewer.These manifests combine content and ads delivered from an ad server and can optionally include metadata containing detailed ad-tracking instructions. Primetime Ad Insertion supports both client-side and server-side ad tracking.

After the system has been properly set up, a typical workflow might look as follows:

1. The client application generates a [Bootstrap URL](/help/dynamic-ad-insertion/msapi-topics/ms-getting-started/ms-api-query-params.md) with information about the video stream and sends a GET request to Primetime Ad Insertion.

1. Primetime Ad Insertion responds by sending the content manifest from the publisher’s CDN back to the client application.

1. The client application chooses appropriate streams in the generated manifest to play and makes requests to Primetime Ad Insertion.

1. Primetime Ad Insertion fetches the requested stream(s) from the content CDN, parses/reads any cue information, makes calls to the ad server and replaces ad breaks as necessary.

1. Primetime Ad Insertion normalizes the manifest by rewriting resource URLs and detecting whether ad creatives require transcoding, see [Just-in-time ad transcoding](just-in-time-transcoding.md) and [packaging](just-in-time-repackaging.md).

1. Primetime Ad Insertion fetches the required ad creatives and inserts the appropriate fragments into the manifests.

1. Primetime Ad Insertion delivers the final stitched manifests, including ads, to the client application for playback.

1. Ad delivery and viewability can be measured via either client or server-side ad tracking, see [Setting up Ad Tracking](set-up-ad-tracking.md).

Primetime Ad Insertion supports most client configurations for HLS/DASH.
