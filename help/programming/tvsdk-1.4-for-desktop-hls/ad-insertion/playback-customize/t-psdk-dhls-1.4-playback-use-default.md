---
description: You can choose to use default ad behaviors.
title: Use the default playback behavior
---

# Use the default playback behavior{#use-the-default-playback-behavior}

You can choose to use default ad behaviors.

To use default behaviors:

* If you implement your own `ContentFactory` class, return a new instance of `DefaultAdPolicySelector` in your implementation of `doRetrieveAdPolicySelector`.     

   ```
   public class CustomContentFactory extends ContentFactory { 
   
       //... 
       // your custom code for advertising classes 
       //... 
            
       /** 
        * @inheritDoc 
        */ 
       override protected function  
         doRetrieveAdPolicySelector(item:MediaPlayerItem):AdPolicySelector { 
           return new DefaultAdPolicySelector(item); 
       } 
   }
   ```

* If you do not have a custom implementation for the `ContentFactory` class, TVSDK uses `DefaultAdPolicySelector`.