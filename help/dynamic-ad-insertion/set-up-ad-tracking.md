---
title: Set up Ad Tracking
description: Setting up Ad Tracking
---

# Set up Ad Tracking {#ser-up-ad-tracking}

Most advertisers require information about when, for how long, and how successfully their ads were viewed. Primetime Ad Insertion supports client-side, server-side and hybrid ad tracking to provide flexibility in collecting this information.

## Client-side Ad Tracking with VMAP/JSON {#client-side-ad-tracking-vmap-json}

In client-side ad tracking, the server sends the client a JSON, VMAP or in-manifest structure specifying tracking events and URLs along with the ad-stitched playlist.

To enable client-side ad tracking, specify the following parameters in the [Bootstrap API](/help/dynamic-ad-insertion/msapi-topics/ms-getting-started/ms-api-query-params.md).

* `pttrackingmode=simple`

* `pttrackingversion={format version (vmap,v1,v2,v3)}`

>[!NOTE]
>
>Setting the `pttrackingmode=simple` will cause the initial bootstrap API request to return a JSON response, rather than an HLS or DASH document.

More information about `pttrackingmode`, `pttrackingversion` formats, can be found in [API Reference: Manifest server query parameters](/help/dynamic-ad-insertion/msapi-topics/ms-getting-started/ms-api-query-params.md).

## Server-side Ad Tracking {#server-side-ad-tracking}

Using this method, ad tracking data is calculated entirely on the server side. This is useful when updating the client application is not feasible. However, server-side ad tracking may not match with client-side playback activity. For example, the server considers an ad to be played after the segments are delivered, even if the end-user does not view the entire ad.

To enable server-side ad tracking, specify the following parameter in the [Bootstrap API](/help/dynamic-ad-insertion/msapi-topics/ms-getting-started/ms-api-query-params.md).

`pttrackingmode=sstm`

See `pttrackingmode` sections of [Bootstrap API](/help/dynamic-ad-insertion/msapi-topics/ms-getting-started/ms-api-query-params.md).

All ad tracking beacons are sent with the following HTTP Request headers:

* `X-Forwarded-For`
* `User-Agent`
* `X-Device-User-Agent`

These values contain the client/player user-agent and client IP address.

## Hybrid Ad Tracking {#hybrid-ad-tracking}

This approach is like server-side tracking, but the client application also requests sidecars from Primetime Ad Insertion for detailed tracking information. Hybrid ad tracking can deliver non-linear ads such as overlays and companions to the client application, while still relying on Primetime Ad Insertion to send individual ad tracking URLs.
To enable hybrid ad tracking, refer to the `pttrackingmode` parameter in the [Bootstrap API](/help/dynamic-ad-insertion/msapi-topics/ms-getting-started/ms-api-query-params.md).
