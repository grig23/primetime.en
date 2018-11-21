---
description: Before you can use most of the Browser TVSDK player methods, the player must be in a valid state.
seo-description: Before you can use most of the Browser TVSDK player methods, the player must be in a valid state.
seo-title: Wait for a valid state
title: Wait for a valid state
uuid: 8d49333d-d06a-4a23-9809-c07019163240
index: y
internal: n
snippet: y
---

# Wait for a valid state{#wait-for-a-valid-state}

Before you can use most of the Browser TVSDK player methods, the player must be in a valid state.

 The player moves through various states. Waiting for the player to be in the correct state ensures that the media resource has successfully loaded. If the player is not in at least the required state, many player methods throw `IllegalStateException`.

The required state is usually PREPARED. 

1. To confirm that the state is PREPARED:

   When the player is initializing, wait for Browser TVSDK to dispatch the `AdobePSDK.MediaPlayerStatusChangeEvent` event with an `event.status` of `MediaPlayerStatus.PREPARED`.

   To check whether the current state of the MediaPlayer object is at least PREPARED. 

   ```
   <readonly> status :AdobePSDK.MediaPlayerStatus
   ```
