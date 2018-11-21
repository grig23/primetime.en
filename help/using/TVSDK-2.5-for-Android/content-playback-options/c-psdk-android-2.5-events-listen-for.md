---
description: Events from TVSDK indicate the status of the player, errors that occur, the completion of actions that you have requested, such as a video starting to play, or actions that occur implicitly, such as an ad completing.
seo-description: Events from TVSDK indicate the status of the player, errors that occur, the completion of actions that you have requested, such as a video starting to play, or actions that occur implicitly, such as an ad completing.
seo-title: Listen for Primetime Player events
title: Listen for Primetime Player events
uuid: ba618cfe-3ad6-4878-b68f-570f5de260e0
index: y
internal: n
snippet: y
---

# Listen for Primetime Player events{#listen-for-primetime-player-events}

Events from TVSDK indicate the status of the player, errors that occur, the completion of actions that you have requested, such as a video starting to play, or actions that occur implicitly, such as an ad completing.

Because your application needs to respond to many of these events, you need to implement event-handling routines and register these routines with TVSDK. The routines call the relevant TVSDK methods to respond appropriately.

More information about events:

* The real-time nature of video playback requires asynchronous (non-blocking) activity for many TVSDK operations. 
* TVSDK supports an event-driven video player.

  It provides events that correspond to all important steps in the playing process. You register those events with your platform's event mechanism and create event handlers that will be called when those events occur. *`Event Handlers`* are also known as callback routines or event listeners. TVSDK provides a complete range of methods that can be used by the event handlers. 
* Your application generally initiates non-blocking operations, such as requesting that a video start playing.

  TVSDK communicates asynchronously with your application by dispatching events, such as when the video starts playing and an event when the video finishes. Other events can indicate status changes in your player and error conditions. Your event handlers take appropriate actions.
