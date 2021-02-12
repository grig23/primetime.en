---
description: You can enable client-side ad tracking by adding the pttrackingmode and pttrackingversion parameters to your Bootstrap URL request.
seo-description: You can enable client-side ad tracking by adding the pttrackingmode and pttrackingversion parameters to your Bootstrap URL request.
seo-title: Enable client-side ad tracking
title: Enable client-side ad tracking
uuid: 0a825756-1d9a-43c5-bc22-9b366f39fdbb
---

# Enable client-side ad tracking {#enable-client-side-ad-tracking}

You can enable client-side ad tracking by adding the `pttrackingmode` and `pttrackingversion` parameters to your Bootstrap URL request.

 With client-side ad tracking enabled, you can also retrieve ad tracking metadata using the Tracking API URL. For more details, see [Query Parameters](/help/primetime-ad-insertion/~old-msapi-topics/ms-at-effectiveness/notvsdk-csat-ms-interface.md).

To perform client-side ad tracking, use the Tracking API URL.

1. Add the following query parameters to the manifest server request URL:

   * `pttrackingmode=simple`
   * `pttrackingversion={format version}`

For example:

```URL
https://. . .?. . .&pttrackingmode=simple&pttrackingversion=v1
```
