---
description: Late-binding audio uses MediaPlayer to play a video that is specified in an M3U8 HLS playlist and that can contain several alternate audio streams.
title: Access alternate audio tracks
---

# Access alternate audio tracks{#access-alternate-audio-tracks}

Late-binding audio uses MediaPlayer to play a video that is specified in an M3U8 HLS playlist and that can contain several alternate audio streams.

1. Wait for the `MediaPlayer` to be in at least the PREPARED status.
1. Listen for these events:

    * `MediaPlayerItemEvent.ITEM_CREATED`: The initial list of audio tracks is available.
    * `MediaPlayerItemEvent.AUDIO_UPDATED`: Audio tracks changed during playback

1. Get the available audio tracks from the `MediaPlayerItem` instance.
1. (Optional) Present the available tracks to the user.
1. Set the selected audio track on the `MediaPlayerItem` instance.
