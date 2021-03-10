---
description: You can turn on this feature and check for related events.
title: Use live master-manifest update
---

# Use live master-manifest update{#use-live-master-manifest-update}

You can turn on this feature and check for related events.

1. To turn on live master-manifest updates, set the update frequency (in minutes) by setting the `NetworkConfiguration.masterUpdateInterval` property.
1. Optionally, track successful manifest updates by listening for the `MediaPlayerItemEvent.MASTER_UPDATED` event.
