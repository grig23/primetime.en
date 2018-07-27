---
description: You can control the visibility of closed captions. When visibility is on, the currently selected track is displayed. If you change which track is current, the visibility setting remains the same.
seo-description: You can control the visibility of closed captions. When visibility is on, the currently selected track is displayed. If you change which track is current, the visibility setting remains the same.
seo-title: Control closed-caption visibility
title: Control closed-caption visibility
uuid: 2e77306a-3557-42d7-bf73-353694824db6
index: n
internal: n
snippet: y
translate: y
---

# Control closed-caption visibility


>[!TIP]
>
>If closed caption text is displayed when the player enters the seek mode, the text no longer displays after the seek completes. Instead, after a few seconds, <!-- PH element: phrases/primetime-sdk-name --> displays the next closed caption text in the video after the ending seek position.


>[!NOTE]
>
>The visibility values for closed captions are defined in ` MediaPlayer.Visibility`. >
>```
>java>enum Visibility { 
>    VISIBLE,  
>    INVISIBLE 
>}
>```



>1. Wait for the MediaPlayer to have at least the PREPARED state (see  ui-state-prepared-wait-for ).
>1. To get the current visibility setting for closed captions, use the getter method in MediaPlayer, which returns a visibility value.

>    
>       ```
>       java>       Visibility getCCVisibility() throws IllegalStateException;
>       ```
>1. To change the visibility for closed captions, use the setter method, passing a visibility value from ` MediaPlayer.Visibility`.

>    
>       ```
>       java>       mediaPlayer.setCCVisibility(Visibility.VISIBLE);
>       ```