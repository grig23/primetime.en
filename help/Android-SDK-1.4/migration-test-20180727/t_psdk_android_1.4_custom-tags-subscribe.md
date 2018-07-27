---
description: prepares TimedMetadata objects for subscribed tags each time these objects are encountered in the content manifest.
seo-description: prepares TimedMetadata objects for subscribed tags each time these objects are encountered in the content manifest.
seo-title: Subscribe to custom tags
title: Subscribe to custom tags
uuid: 4b83594f-bc8c-4430-b4ae-0de39eaf0e9d
index: n
internal: n
snippet: y
translate: y
---

# Subscribe to custom tags

Before the playback starts, you must subscribe to the tags.
To be notified about custom tags in HLS manifests:

>1. Set the custom ad tag names globally by passing an array that contains the custom tags to ` setSubscribedTags` in ` MediaPlayerItemConfig`.

>   >[!IMPORTANT]
>   >
>   >You must include the ` #` prefix when working with HLS streams. 
>   For example: >
>   ```
>   java>   String[] array = new String[3]; 
>   array[0] = "#EXT-X-ASSET"; 
>   array[1] = "#EXT-X-BLACKOUT"; 
>   array[2] = "#EXT-OATCLS-SCTE35"; 
>   MediaPlayerItemConfig.setSubscribedTags(array);
>   ```

>