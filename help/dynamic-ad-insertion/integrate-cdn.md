---
title: Integrate your CDN
description: Integrating your CDN
---

# Integrate your CDN {#integrating-cdn}

Primetime Ad Insertion serves as a proxy between your client application and manifests, not the video chunks themselves. Deploy your content to CDN of choice and pass the URL to Primetime Ad Insertion using the Bootstrap API.<!-- For integration details, see [Supported CDNs](supported-cdns.md).-->

## Supported CDN tokenization schemes {#cdn-tokenization-schemes}

CDNs often have different tokenization schemes for fragment authorization. Primetime Ad Insertion natively support major CDN networks, including:

* Akamai
* Limelight
* Centurylink / Level3
* Contact your Primetime support representative for a complete list of supported CDNs

For more information about the `pttoken` parameter, see [Bootstrap API parameter description](/help/dynamic-ad-insertion/msapi-topics/ms-getting-started/ms-api-query-params.md).

## Configure ads to deliver from the content CDN {#configure-ad-deliver-from-cdn}

You may want to deliver ads and content from the same CDN to maintain content affinity, help bypass ad blockers and/or optimize the number of required connections from the client application. Primetime Ad Insertion supports fragment re-writing rules to map fragments to your content CDN.

<!--## Increase start-up performance with your CDN {#increase-startup-performance}

For more information, see [Optimizing start-up](optimize-video-startup-time.md).-->

## Multi-CDN features {#enable-multi-cdn-fetures}

Contact your Primetime Support representative to enable multi-CDN features.
