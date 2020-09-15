---
description: You can control the visibility of closed captions. When visibility has been enabled, the currently selected track is displayed. If you change which track is current, the visibility setting remains the same.
seo-description: You can control the visibility of closed captions. When visibility has been enabled, the currently selected track is displayed. If you change which track is current, the visibility setting remains the same.
seo-title: Control closed-caption visibility
title: Control closed-caption visibility
uuid: f142e60d-5581-4d1c-9d4d-a4a58ac1b67b
---

# Control closed-caption visibility {#control-closed-caption-visibility}

You can control the visibility of closed captions. When visibility has been enabled, the currently selected track is displayed. If you change which track is current, the visibility setting remains the same.

>[!TIP]
>
>If closed caption text is displayed when the player enters seek mode, the text no longer displays after the seek completes. Instead, after a few seconds, TVSDK displays the next closed caption text in the video after the ending seek position. 
>
>The visibility values for closed captions are defined in `MediaPlayer.Visibility`.
>
>```java
>enum Visibility {  
>    VISIBLE,  
>    INVISIBLE 
>}
>```
>

1. Wait for the `MediaPlayer` to be in at least the PREPARED status. For more information, see [Wait for a valid status](../../../../tvsdk-3x-android-prog/android-3x-content-playback-options-android2/ui-configure/android-3x-ui-state-prepared-wait-for.md).

1. To get the current visibility setting for closed captions, use the getter method in `MediaPlayer`, which returns a visibility value.

   ```java
   MediaPlayer.Visibility getCCVisibility() throws MediaPlayerException;
   ```

1. To change the visibility for closed captions, use the setter method, passing a visibility value from `MediaPlayer.Visibility`.

   For example: 

   ```java
   mediaPlayer.setCCVisibility(MediaPlayer.Visibility visibility);
   ```