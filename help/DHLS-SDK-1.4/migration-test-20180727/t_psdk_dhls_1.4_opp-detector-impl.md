---
description: You can implement your own opportunity detectors.
seo-description: You can implement your own opportunity detectors.
seo-title: Implement a custom opportunity detector
title: Implement a custom opportunity detector
uuid: 1c2e6b37-6429-407b-bc04-f7bcda279ff5
index: n
internal: n
snippet: y
translate: y
---

# Implement a custom opportunity detector


* If your opportunity generator is based on ` TimedMetadata` objects associated with the current media stream, then it should extend the ` SpliceOutOpportunityGenerator` or ` TimedMetadataOpportunityGenerator`.
* If your opportunity generator is based on out-of-band data provided by an external service (such as a CIS), then it should extend the ` OpportunityGenerator`.

>1. Create the custom opportunity generator.
>       If your custom opportunity generator is based on ` TimedMetadata` objects, then extend the ` TimedMetadataOpportunityGenerator` and override these methods: >    
>    * ` doConfigure` - This method is called after the media player item has been created and provides the opportunity generator to create an initial set of opportunities if needed
>    * ` doProcess` - This method is called every time new ` TimedMetadata` is detected (for example, for live/linear streams every time the playlist/manifest refreshes)

>    

>    
>       ```
>       public class CustomOpportunityGenerator extends TimedMetadataOpportunityGenerator { 
>           override protected function doConfigure(playhead:Number, playbackRange:TimeRange):void { 
>               // the playhead represents the initial playback position 
>               // the playback range represents the initial playback range 
>                 
>               // the item property indicates the current MediaPlayerItem associated with this generator 
>               // the initial set of timed metadata can be obtain through the item property 
>               var timedMetadataCollection:Vector.&lt;TimedMetadata&gt; = item.timedMetadata; 
>           } 
>         
>           override protected function doProcess(timedMetadata:TimedMetadata):void { 
>               ... 
>                 
>               // when an opportunity is created by this generator 
>               // we need to notify the  
<ph conkeyref="phrases primetime-sdk-name"="">
  Phrase through the client property 
 >               client.resolve(opportunity); 
 >           }  
 >           ... 
 >       } 
</ph conkeyref="phrases>
>       ```
>1. Create the custom content factory, which uses the custom opportunity generator.

>    
>       ```
>       public class CustomContentFactory extends DefaultContentFactory { 
>           ... 
>         
>           /** 
>           * @inheritDoc 
>           */ 
>           override protected function doRetrieveGenerators(item:MediaPlayerItem):Vector.&lt;OpportunityGenerator&gt; { 
>               var result:Vector.&lt;OpportunityGenerator&gt; = new Vector.&lt;OpportunityGenerator&gt;(); 
>               result.push(new CustomOpportunityGenerator()); 
>                 
>               return result; 
>           } 
>       }
>       ```
>1. Register the custom content factory for the media stream to be played.

>    
>       ```
>       var mediaPlayerItemConfig:MediaPlayerItemConfig = new DefaultMediaPlayerItemConfig(); 
>       mediaPlayerItemConfig.advertisingFactory = new CustomContentFactory(); 
>       ... 
>         
>       player.replaceCurrentResource(mediaResource, mediaPlayerItemConfig);
>       ```