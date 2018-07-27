---
description: supports displaying linear Video Player-Ad Interface Definition (VPAID) ads in an ad break. VPAID version 1.0 requires Flash, while version 2.0 also works with Browser TVSDK and JavaScript.
seo-description: supports displaying linear Video Player-Ad Interface Definition (VPAID) ads in an ad break. VPAID version 1.0 requires Flash, while version 2.0 also works with Browser TVSDK and JavaScript.
seo-title: Display linear VPAID ads in an ad break
title: Display linear VPAID ads in an ad break
uuid: 87ab7f27-a5bf-4204-9809-e8873a081648
index: n
internal: n
snippet: y
translate: y
---

# Display linear VPAID ads in an ad break

To display VPAID ads correctly, you must provide an ad container ( ` AdContainerView`) within the ` MediaPlayerContext` instance. 
Limitations for VPAID ads: 
* VPAID ads do not necessarily have a predefined duration, given that the ad can be interactive. Therefore, the ad duration (defined by the ad server response) may not always exactly correspond to the true duration of the ad.
* For VPAID 1.0 ads,  <!-- PH element: phrases/primetime-sdk-name --> requires Flash player 14.0.0.160 or greater installed on the device. For earlier versions of the Flash player, this feature is disabled and VPAID 1.0 ads are skipped.

To set up an ad container for displaying VPAID ads (version 1.0 or 2.0) within an ad break:

>1. Use the following sample code to set up an ad container that can show VPAID ads.
>
>   ```
>   var context:MediaPlayerContext =  
>     new MediaPlayerContext(_authorizedFeatureHelper.authorizedFeatures); 
>     
>   adContainer = new AdContainerView(); 
>   adContainer.x = adContainer.y = 0; 
>   adContainer.setSize(videoContainer.width, videoContainer.height); 
>   addChild(adContainer); 
>     
>   context.adContainer = adContainer; 
>   _player = new DefaultMediaPlayer(context);
>   ```
>
>1. When the view resizes, reset the size on the ad container.
>
>   ```
>   adContainer.setSize(stage.stageWidth, stage.stageHeight);
>   ```
>

>   >[!NOTE]
>   >
>   >When you get a full-screen-change event and you set the new size on the ad container, pass the stage display state as follows to ensure that the player resizes correctly:>   >
>   >```
>   >private function onFullScreenChange(event:FullScreenEvent):void { 
>   >if (_adContainer) 
>   >{ _adContainer.setSize(stage.stageWidth, stage.stageHeight, stage.displayState); } 
>   >}
>   >```

>