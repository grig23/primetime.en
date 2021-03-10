---
description: In Adobe Primetime ad decisioning, you can target ads on key-value pairs.
title: Targeting information
---

# Targeting information{#targeting-information}

In Adobe Primetime ad decisioning, you can target ads on key-value pairs.

 To pass these key value pairs to Browser TVSDK: 

```js
var auditudeSettings = new AdobePSDK.AuditudeSettings(); 
var targetingInfo = new AdobePSDK.Metadata(); 
 
// Add key value pairs to targetingInfo 
targetingInfo.setValue(key1, value1); 
targetingInfo.setValue(key2, value2); 
 
auditudeSettings.targetingInfo = targetingInfo;
```

