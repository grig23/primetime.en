---
description: TVSDK dispatches digital rights management (DRM) events in response to DRM-related operations such as when new DRM metadata becomes available.
title: DRM events
---

# DRM events{#drm-events}

TVSDK dispatches digital rights management (DRM) events in response to DRM-related operations such as when new DRM metadata becomes available.

 To be notified about all DRM-related events, register an implementation of `MediaPlayer.DRMEventListener` that includes the following callback. 

|  Event  | Meaning  |
|---|---|
| [onDRMMetadata](https://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/MediaPlayer.DRMEventListener.html#onDRMMetadata(DRMMetadataInfo)) `(DRMMetadataInfo drmMetadataInfo)`  | New DRM metadata is available.  |

