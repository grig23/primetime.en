---
description: You can turn features on or off without going through the code by using the manager factory.
seo-description: You can turn features on or off without going through the code by using the manager factory.
seo-title: Turning features on or off using ManagerFactory
title: Turning features on or off using ManagerFactory
uuid: 9ef36175-bc59-4ed6-a002-951c90880a27
index: n
internal: n
snippet: y
translate: y
---

# Turning features on or off using ManagerFactory

The enablement argument in the example below determines whether the feature is used or not. If it is false, the feature manager is created but provides just the default functionality to the player, as if the feature manager were not created. If it is true, the feature manager is created, the feature is enabled, and the media player accepts input from the configuration file.
For example, in the ` com.adobe.primetime.reference.ui.player.PlayerFragment.java` file: 

```
javaadsManager = ManagerFactory.getAdsManager( 
<b>true</b>, config, mediaPlayer);
```
API documentation: [ ManagerFactory ](http://help.adobe.com/en_US/primetime/reference_implementation/android/javadoc/com/adobe/primetime/reference/manager/ManagerFactory.html) 