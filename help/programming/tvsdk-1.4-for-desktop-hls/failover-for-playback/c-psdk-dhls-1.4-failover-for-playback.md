---
description: Streaming over the Internet requires a constant and stable connection to play a stream from a remote server. However, the variability of a viewer's Internet connection or streaming playback means that remote playback might not have the quality of media played locally.
title: Playback and failover
---

# Overview {#playback-and-failover-overview}

Streaming over the Internet requires a constant and stable connection to play a stream from a remote server. However, the variability of a viewer's Internet connection or streaming playback means that remote playback might not have the quality of media played locally.

Primetime cannot protect from such failures as an ISP outage or a cable disconnection. However, Primetime streaming provides failover protection to protect playback from certain remote server failures or operational failures, making a better experience for viewers. TVSDK implements failover protection to minimize playback interruptions and achieve a seamless playback despite transmission problems. The video player automatically switches to a backup media set when entire renditions or fragments are unavailable. 
