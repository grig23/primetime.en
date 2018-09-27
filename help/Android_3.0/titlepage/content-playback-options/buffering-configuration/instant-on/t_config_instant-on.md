---
description: TVSDK provides methods and statuses to allow you use Instant On with a media resource.
seo-description: TVSDK provides methods and statuses to allow you use Instant On with a media resource.
seo-title: Configure buffering for Instant On
title: Configure buffering for Instant On
uuid: 39bf6615-809d-443c-b094-2f0b2e9d85f8
index: y
internal: n
snippet: y
translate: y
---

# Configure buffering for Instant On

TVSDK provides methods and statuses to allow you use Instant On with a media resource.


>[!NOTE]
>
>Adobe recommends using `MediaPlayerItemLoader` for InstantOn. To use `MediaPlayerItemLoader`, rather than `MediaPlayer`, see  media-resource-load-using-mediaplayeritemloader . 

1. Confirm that the resource has loaded, and the player is prepared to play the resource.
1. Before calling `play`, call `prepareBuffer` for each `MediaPlayer` instance.

   `prepareBuffer` enables Instant On, and TVSDK starts buffering immediately and dispatches the `BUFFERING_COMPLETED` event when the buffer is full.


   >[!TIP]
   >
   >By default, `prepareBuffer` and `prepareToPlay` set up the media stream to start playing from the beginning. To start at another position, pass the position (in milliseconds) to `prepareToPlay`. 

   ```
   @Override 
   public void onStatusChanged(MediaPlayerStatus status) { 
       switch (status) { 
           case INITIALIZED: 
               // This example starts 5 seconds into the stream. 
               mediaPlayer.prepareToPlay(5000); 
               break; 
           case PREPARING: 
               break; 
           case PREPARED: 
               mediaPlayer.prepareBuffer(); 
               break; 
           ... 
       } 
   }
   ```

1. When you receive the `BUFFERING_COMPLETE` event, start playing the item or display visual feedback to indicate that the content is completely buffered.

   If you call `play`, playback should begin immediately.