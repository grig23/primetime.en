---
description: null
seo-description: null
seo-title: Implement VPAID 2.0 integration
title: Implement VPAID 2.0 integration
uuid: ef05f2a3-843e-477a-8ce6-a1eb5d6e8f6b
index: n
internal: n
snippet: y
translate: y
---

# Implement VPAID 2.0 integration

To add VPAID 2.0 support in your iOS application:

>1. (Optional) Add a listener for custom ad events.
>
>   ```
>   [[NSNotificationCenter defaultCenter] addObserver:self selector:@selector(onMediaPlayerCustomAdNotification:) name:PTMediaPlayerCustomAdNotification object:self.player];
>   ```
>
>1. (Optional) Display the notification.
>
>   ```
>   -(void)onMediaPlayerCustomAdNotification:(NSNotification *)notification{    PTCustomAdNotificationObject *notificationObject = [notification.userInfo objectForKey:PTCustomAdNotificationObjectKey];    if (notificationObject)    
>   {        NSLog(@"ViewController:: Custom Ad Notification Received: %ld", notificationObject.type);    } 
>    
>   }
>   ```
>