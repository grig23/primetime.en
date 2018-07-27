---
description: ID3 tags provide information about an audio or video file, such as the title of the file or the name of the artist. detects ID3 tags at the transport stream (TS) segment level in HLS streams and dispatches an event. The application can extract data from the tag.
seo-description: ID3 tags provide information about an audio or video file, such as the title of the file or the name of the artist. detects ID3 tags at the transport stream (TS) segment level in HLS streams and dispatches an event. The application can extract data from the tag.
seo-title: ID3 tags
title: ID3 tags
uuid: 7b32aa0d-c14b-4ddb-b3b6-c9cd3b8dad13
index: n
internal: n
snippet: y
translate: y
---

# ID3 tags


>[!IMPORTANT]
>
><!-- PH element: phrases/primetime-sdk-name --> recognizes ID3 metadata (version 2.3.0 or 2.4.0) in audio (AAC) and video (H.264) streams, in any of its possible encodings (ASCII, UTF8, UTF16-BE, or UTF16-LE). It ignores ID3 tags that are not in one of the recognized versions or formats. Unspecified encoding is treated as UTF8.


When  <!-- PH element: phrases/primetime-sdk-name --> detects ID3 metadata, it issues a notification with the following data:
* InfoCode = 303007
* TYPE = ID3
* NAME = not present
* ID = 0


>1. Implement an event listener for ` MediaPlayer.PlaybackEventListener#onTimedMetadata(TimeMetadata timeMetadata)` and register it with the ` MediaPlayer` object.
>   <!-- PH element: phrases/primetime-sdk-name --> calls this listener when it detects ID3 metadata.

>   >[!NOTE]
>   >
>   >Custom ad cues use the same ` onTimedMetadata` event to indicate detection of a new tag. This should not cause any confusion because custom ad cues are detected at the manifest level, and ID3 tags are embedded in the stream. For more information, see  custom-tags-configure . 
>
>1. Retrieve the metadata.
>
>   ```
>   java>   @Override 
>   public void onTimedMetadata(TimedMetadata timedMetadata) { 
>       TimedMetadata.Type type = timedMetadata.getType(); 
>       if (type.equals(TimedMetadata.Type.ID3)){ 
>           long time = timeMetadata.getTime(); 
>           Metadata metadata = timedMetadata.getMetadata(); 
>           Set&lt;String&gt; keys = metadata.keySet(); 
>           for (String key : keys){ 
>               String value = metadata.getValue(key); 
>           } 
>       } 
>   }
>   ```
>