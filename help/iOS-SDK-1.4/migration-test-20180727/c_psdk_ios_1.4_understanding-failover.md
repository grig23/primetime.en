---
description: Failover handling occurs when a variant playlist has multiple renditions for the same bit rate, and one of the renditions stops working. The switches between renditions.
seo-description: Failover handling occurs when a variant playlist has multiple renditions for the same bit rate, and one of the renditions stops working. The switches between renditions.
seo-title: Failover
title: Failover
uuid: 2293dbe7-6267-44d4-8700-0bef5b1435ba
index: n
internal: n
snippet: y
translate: y
---

# Failover

The following example shows a variant playlist with failover URLs of the same bit rate: 
```
#EXTM3U
#EXT-X-STREAM-INF:PROGRAM-ID=1, BANDWIDTH =700000
http://sj2slu225.corp.adobe.com:8090/_default_/_default_/livestream.m3u8   

#EXT-X-STREAM-INF:PROGRAM-ID=1, BANDWIDTH =700000
http://sj2slu225.corp.adobe.com:8091/_default_/_default_/livestream.m3u8
```

When  <!-- PH element: phrases/primetime-sdk-name --> loads the variant playlist, it creates a queue that holds the URLs for all the renditions of the content for the same bit rate. When a request for a URL fails, <!-- PH element: phrases/primetime-sdk-name --> uses the next URL of the same bit rate from the failover queue. At any specific failure time, <!-- PH element: phrases/primetime-sdk-name --> cycles once through all available URLs until it finds one that works correctly or until it has attempted all the available URLs. If <!-- PH element: phrases/primetime-sdk-name --> has tried to all of the available URLs and none of the URLs work, <!-- PH element: phrases/primetime-sdk-name --> stops trying to play the content.
Failover occurs only at the M3U8 level, which means: 
* For VOD, failover can occur only when it begins to attempt to play and not after it has started playing.
* For live streaming, failover can happen in the middle of the stream.


>[!TIP]
>
><!-- PH element: phrases/primetime-sdk-name --> , rather than the Apple AV Foundation player, provides failover handling.

