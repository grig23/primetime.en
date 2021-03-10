---
description: In some cases, you need to know whether the media content is live or VOD.
title: Identify whether the content is live or VOD
---

# Identify whether the content is live or VOD{#identify-whether-the-content-is-live-or-vod}

In some cases, you need to know whether the media content is live or VOD.

1. Ensure that the player is in at least the PREPARED state.
1. Determine whether the `MediaPlayerItem` content is live (true) or VOD (false).

   ```java
   boolean isLive();
   ```

