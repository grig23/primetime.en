---
description: You can globally configure custom tag names in with the MediaPlayerItemConfig class.
seo-description: You can globally configure custom tag names in with the MediaPlayerItemConfig class.
seo-title: Config class methods for tags
title: Config class methods for tags
uuid: b4b2c4f6-8a37-42f4-8f93-e1c5a5693ce8
index: n
internal: n
snippet: y
translate: y
---

# Config class methods for tags

 <!-- PH element: phrases/primetime-sdk-name --> automatically applies the global configuration to any media stream that does not specify a stream-specific configuration.
` MediaPlayerItemConfig` exposes these methods to manage the custom tags: 

<table id="table_B37A6C75270D47BC99258F2884AD6905"> 
 <tbody> 
  <tr> 
   <td colspan="2"> <b>Subscribe to specific custom tags</b> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="codeph"> public final String[] getSubscribedTags </span> </td> 
   <td colname="col2"> <p>Retrieves the current list of subscribed tags.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="codeph"> public final void setSubscribedTags(String[] tags); </span> </td> 
   <td colname="col2"> <p>Sets the list of subscribed tags that will be exposed to the application.</p> <p>Your application is also automatically subscribed to all tags transmitted through <span class="codeph"> setAdTags </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colspan="2"> <b>Customize the ad tags used by the default opportunity detector</b> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="codeph"> public final String[] getAdTags; </span> </td> 
   <td colname="col2"> <p>Retrieves the current list of ad tags.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="codeph"> public final void setAdTags(String[] tags); </span> </td> 
   <td colname="col2"> <p>Sets the list of ad tags that will be used by default opportunity generator.</p> </td> 
  </tr> 
 </tbody> 
</table>

Remember the following: 
* The setter methods do not allow the tags parameter to contain null values. If encountered,  <!-- PH element: phrases/primetime-sdk-name --> throws an ` IllegalArgumentException`. 

* The custom tag name must contain the ` #` prefix. For example, ` #EXT-X-ASSET` is a correct custom tag name, but ` EXT-X-ASSET` is incorrect. 

* You cannot change the configuration after the media stream has been loaded.
