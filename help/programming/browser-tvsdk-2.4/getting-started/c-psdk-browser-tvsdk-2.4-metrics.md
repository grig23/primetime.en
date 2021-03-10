---
description: Browser TVSDK provides metrics to use for analyzing and debugging. You can get these metrics by using QoSProvider.
title: Metrics
---

# Metrics{#metrics}

Browser TVSDK provides metrics to use for analyzing and debugging. You can get these metrics by using QoSProvider.

For example: 

```js
var qosProvider = new AdobePSDK.QOSProvider(); 
qosProvider.attachMediaPlayer(player); 
var metrics = qosProvider.playbackInformation;
```

