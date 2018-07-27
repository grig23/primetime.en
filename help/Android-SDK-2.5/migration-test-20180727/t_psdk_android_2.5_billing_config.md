---
description: If you use the default configuration, there is nothing else you need to do to enable or configure billing. If you obtained different configuration parameters from your Adobe Enablement representative, use the BillingMetricsConfiguration class to set these parameters up before initializing the media player.
seo-description: If you use the default configuration, there is nothing else you need to do to enable or configure billing. If you obtained different configuration parameters from your Adobe Enablement representative, use the BillingMetricsConfiguration class to set these parameters up before initializing the media player.
seo-title: Configure billing metrics
title: Configure billing metrics
uuid: a6846eb8-db36-4607-9098-17056ab6e2a4
index: n
internal: n
snippet: y
translate: y
---

# Configure billing metrics


>[!TIP]
>
>Most customers should use the default configuration.


>[!IMPORTANT]
>
>The configuration you set remains in effect for the life of the media player. Once you initialize the media player, you cannot change the configuration.

To configure billing metrics:

>1. Enter the following code sample.
>
>   ```
>   java>   MediaPlayerItemConfig config = new MediaPlayerItemConfig(); 
>   BillingMetricsConfiguration billingConfig = new BillingMetricsConfiguration(); 
>   billingConfig.setEnabled(true); 
>   billingConfig.setProVODBillableDurationMinutes(60); 
>   billingConfig.setStdVODBillableDurationMinutes(30); 
>   billingConfig.setLiveBillableDurationMinutes(15); 
>   config.setBillingMetricsConfiguration(billingConfig); 
>   mediaPlayer.replaceCurrentResource(mediaResource, config);
>   ```
>