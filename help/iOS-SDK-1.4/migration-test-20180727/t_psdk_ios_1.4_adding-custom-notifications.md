---
seo-title: Adding custom notifications
title: Adding custom notifications
uuid: 64b2fabd-88ae-4bba-9bb7-401f7a3846d1
index: n
internal: n
snippet: y
translate: y
---

# Adding custom notifications

To add a custom notification:
>1. Create a new ` PTNotification` and add it to the ` PTNotificationHistory` by using the current ` PTMediaPlayerItem`:
>
>   ```
>   //Access to the PTMediaPlayerItem  
>   PTMediaPlayerItem *item = self.player.currentItem; 
>   PTNotificationHistory *notificationHistory = item.notificationHistory; 
>    
>   //Create notification 
>   PTNotification* notification = [[PTNotification notificationWithType:PTNotificationTypeWarning code:99999 description:@"Custom notification description"]; 
>    
>   //Add notification 
>   [notificationHistory addNotification:notification];
>   ```
>