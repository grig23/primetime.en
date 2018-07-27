---
description: MediaPlayerNotification provides information that is related to the player’s status.
seo-description: MediaPlayerNotification provides information that is related to the player’s status.
seo-title: Notification content
title: Notification content
uuid: 18331c8c-4c84-4470-b54b-3410c835e538
index: n
internal: n
snippet: y
translate: y
---

# Notification content

 <!-- PH element: phrases/primetime-sdk-name --> provides a chronological list of `MediaPlayerNotification` notifications, and each notification contains the following information: 
* A time stamp
* Diagnostic metadata that consists of the following elements: 
    * `type`: INFO, WARN, or ERROR.
    * `code`: A numerical representation of the notification.
    * `name`: A human-readable description of the notification, such as SEEK_ERROR
    * `metadata`: Key/value pairs that contain relevant information about the notification. For example, a key named `URL` provides a value that is a URL related to the notification.
    * `innerNotification`: A reference to another `MediaPlayerNotification` object that directly impacts this notification.


You can store this information locally for later analysis or send it to a remote server for logging and graphical representation.