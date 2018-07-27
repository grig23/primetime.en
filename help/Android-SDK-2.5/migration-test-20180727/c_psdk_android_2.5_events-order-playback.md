---
description: dispatches events/notifications in generally expected sequences. Your player can implement actions based on events in the expected sequence.
seo-description: dispatches events/notifications in generally expected sequences. Your player can implement actions based on events in the expected sequence.
seo-title: Order of playback events
title: Order of playback events
uuid: 0bf9112d-1575-4ea2-b938-e7d08bac2ace
index: n
internal: n
snippet: y
translate: y
---

# Order of playback events


<a id="section_09D3ED5F4886460A8669EC362E57F5F8"></a>

The following examples show the order of some events that occur during playback.
When successfully loading a media resource through `MediaPlayer.replaceCurrentResource`, the order of events is: 
1. `MediaPlayerEvent.STATUS_CHANGED` with status `MediaPlayerStatus.INITIALIZING`
1. `MediaPlayerEvent.STATUS_CHANGED` with status `MediaPlayerStatus.INITIALIZED`

>[!TIP]
>
>Load your media resource on the main thread. If you load a media resource on a background thread, this operation or subsequent operations might throw an error, such as `MediaPlayerException`, and exit. 

When preparing for playback through `MediaPlayer.prepareToPlay`, the order of events is: 
1. `MediaPlayerEvent.STATUS_CHANGED` with status `MediaPlayerStatus.PREPARING`
1. `MediaPlayerEvent.TIMELINE_UPDATED` if ads were inserted.
1. `MediaPlayerEvent.STATUS_CHANGED` with status `MediaPlayerStatus.PREPARED`
For live/linear streams, during playback as the playback window advances and additional opportunities are resolved, the order of events is:
1. `MediaPlayerEvent.ITEM_UPDATED`
1. `MediaPlayerEvent.TIMELINE_UPDATED` if ads were inserted
