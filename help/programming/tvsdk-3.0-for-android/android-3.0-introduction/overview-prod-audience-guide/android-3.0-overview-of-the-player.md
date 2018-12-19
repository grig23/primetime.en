---
description: TVSDK for Android 3.0 includes a variety of features that you can implement in your players.
seo-description: TVSDK for Android 3.0 includes a variety of features that you can implement in your players.
seo-title: Primetime TVSDK features
title: Primetime TVSDK features
uuid: 6e26c09c-2858-47d1-80e8-1d7c6a468b86
index: y
internal: n
snippet: y
---

# Primetime TVSDK features{#primetime-tvsdk-features}

TVSDK for Android 3.0 includes a variety of features that you can implement in your players.

TVSDK capabilities:

* **VOD and live/linear playback**

    * Management of the playback window, including methods that play, stop, pause, seek, and retrieve the playhead position 
    * Support for full-event replay 
    * Closed captioning (608, 708, WebVTT) and alternate forms of audio for increased accessibility 
    * Controls for text styling in captions 
    * DVR capability, fast forward, and fast rewind (the latter two are known as *trick-play mode*) 
    * Adaptive bit rate (ABR) logic and initial set up of ABR controls 
    * Live manifest failover support 
    * Adjustable playback buffers 
    * Fragment duration, size, and time-to-download tracking support

* **Advertising**

    * VPAID 2.0 
    * Client-side ad stitching

        * Seamless ad insertion, including support for VAST/VMAP 
        * Support for custom cue tags for ads 
        * Support for marking, replacing, and deleting C3 ads 
        * Customizable content/ad insertion workflow including blackout signaling

* **Content protection**

    * Access to digital rights management (DRM)-related services 
    * Playback of HLS streams unencrypted or with Protected HTTP Live Streaming (PHLS) 
    * Resolution-based output control, based on DRM policy

* **Video and ad tracking**

    * QoS event tracking 
    * Notifications that help TVSDK and your application to communicate asynchronously about the status of videos, advertisements, and other elements. Notifications also log activity.

* **Logging**

    * Debug logging 
    * Tracking support for fragment duration, size, and time-to-download
