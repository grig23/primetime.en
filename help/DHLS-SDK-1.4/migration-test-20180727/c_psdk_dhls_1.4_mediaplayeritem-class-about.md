---
description: After a media resource is successfully loaded, creates an instance of the MediaPlayerItem class to provide access to that resource.
seo-description: After a media resource is successfully loaded, creates an instance of the MediaPlayerItem class to provide access to that resource.
seo-title: About the MediaPlayerItem class
title: About the MediaPlayerItem class
uuid: 44fdb824-a4cc-4720-98e8-e22850979bdd
index: n
internal: n
snippet: y
translate: y
---

# About the MediaPlayerItem class

The `MediaResource` represents a request that is issued by the application layer to the `MediaPlayer` instance to load content. 
The `MediaPlayer` resolves the media resource, loads the associated manifest file, and parses the manifest. This is the asynchronous part of the resource loading process. The `MediaPlayerItem` instance is produced after the resource has been resolved, and this instance is a resolved version of a `MediaResource`.  <!-- PH element: phrases/primetime-sdk-name --> provides access to the newly created `MediaPlayerItem` instance through `MediaPlayer.currentItem`. 

>[!TIP]
>
>You must wait for the resource to be successfully loaded before accessing the media player item.
