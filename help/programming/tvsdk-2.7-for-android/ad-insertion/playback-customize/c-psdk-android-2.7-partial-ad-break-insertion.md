---
title: Partial Ad break insertion
description: Partial Ad break insertion
copied-description: yes
exl-id: bcd4b108-9b91-479e-8147-ec4d24862e37
---
# Partial Ad break insertion {#partial-ad-break-insertion}

You can enable a TV-like experience of being able to join in the middle of an ad, in live streams. The Partial Ad break feature allows you to mimic a TV-like experience where, if the client starts a live stream inside a midroll, it will start within that midroll. It is similar to switching to a TV channel and the commercials run seamlessly.

For example, If a user joins in the middle of a 90-second ad break (three 30-second ads), 10 seconds into the second ad (that is, at 40 seconds into the ad break), the following happens:

* The second ad is played for the remaining duration (20 sec) followed by the third ad. 
* Ad trackers for the partially played ad (the second ad) are not fired. Only the tracker for the third ad is fired.

This behavior is not enabled by default. To enable this feature work in your app, do the following:

1. Disable the live prerolls, using AdvertisingMetadata class's method setEnableLivePreroll. 

   ```
   advertisingMetadata.setLivePreroll(false)  
   advertisingMetadata.setPreroll(false)
   ```

1. Switch ON the preference for Partial Ad-break Insertion. Use the new method setPartialAdBreakPref in MediaPlayer interface to switch this feature ON. Use getPartialAdBreakPref method to find the current state of this preference. 

   ```
   MediaPlayer mediaPlayer = new MediaPlayer(getActivity().getApplicationContext()); 
    mediaPlayer.setPartialAdBreakPref(true);
   ```
