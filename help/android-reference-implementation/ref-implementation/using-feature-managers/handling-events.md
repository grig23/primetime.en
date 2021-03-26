---
description: If the application needs to handle events dispatched from the feature manager, it needs to register the manager in the PlayerFragment.java file.
title: Handling events
---

# Handling events {#handling-events}

If the application needs to handle events dispatched from the feature manager, it needs to register the manager in the PlayerFragment.java file.

For example:

```
private final AdsManager.AdsManagerEventListener adsManagerEventListener =  
  new AdsManager.AdsManagerEventListener() { 
 
    // add the ads functionality... 
 
} 
 
//Register the listener 
adsManager.addEventListener(adsManagerEventListener);
```