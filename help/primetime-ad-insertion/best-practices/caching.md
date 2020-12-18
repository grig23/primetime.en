---
title: Caching
description: 
---

# Caching {#caching}

Contact your CDN representative to enable caching on your video streams. Primetime Ad Insertion respects the HTTP cache control headers `max-age`. For caching, following settings are recommended.

## For Live/Linear content {#caching-live-linear-content}

* Master manifest: 24 hours, or Cache-Control: max-age=86400

* Media manifest: 1 second, or Cache-Control: max-age=1

## For VOD content {#caching-vod-content}

* Master manifest: 24 hours, or Cache-Control: max-age=86400

* Media manifest: 24 hours, or Cache-Control: max-age=86400
