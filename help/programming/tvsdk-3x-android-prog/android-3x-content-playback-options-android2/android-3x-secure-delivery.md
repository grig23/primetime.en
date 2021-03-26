---
description: TVSDK introduces secure delivery over HTTPS.
title: Secure Delivery over HTTPS
---

# Secure Delivery over HTTPS {#secure-delivery-https}

Adobe Primetime TVSDK provides support for HTTPS delivery for all the calls originating from TVSDK, which include

* Auditude Ad Server Calls
* CRS requests
* DRM license calls
* Video Analytics Pings
* Billing Pings

In order to use this feature, ensure that the servers configured for serving the above requests support HTTPS.

This new behavior is not enabled by default. Use the following to enable secure delivery before call to `MediaPlayer.replaceCurrentResource()`

```java
MediaPlayerItemConfig config = new MediaPlayerItemConfig(context);
NetworkConfiguration netConfig  = new NetworkConfiguration();
netConfig.setForceHTTPS(true);
config.setNetworkConfiguration(netConfig);
```