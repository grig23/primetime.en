---
description: To allow the ad resolver to work, ad providers, such as Adobe Primetime ad decisioning, require configuration values to enable your connection to the provider.
seo-description: To allow the ad resolver to work, ad providers, such as Adobe Primetime ad decisioning, require configuration values to enable your connection to the provider.
seo-title: Ad insertion metadata
title: Ad insertion metadata
uuid: ee4dd8b8-4c41-4f01-be50-60f4c7dc962d
index: y
internal: n
snippet: y
---

# Ad insertion metadata{#ad-insertion-metadata}

To allow the ad resolver to work, ad providers, such as Adobe Primetime ad decisioning, require configuration values to enable your connection to the provider.

TVSDK includes the Primetime ad decisioninglibrary. For your content to include advertising from the Primetime ad decisioningserver, your application must provide the following required `AuditudeSettings` information:

* `mediaID`, which is a unique identifier for the video to be played.

  The publisher assigns the mediaID when submitting video content and ad information to the Adobe Primetime ad decisioning server. This ID is used by Primetime ad decisioningto retrieve related advertising information for the video from the server. 

* (Optional) `defaultMediaId`, which specifies the ads that are served when the following conditions are met:

    * Your request to the ad server is invalid, or the content is incorrectly configured. 
    * Primetime ad decisioningis experiencing delays in propagating the data. 
    * One of the Primetime ad decisioning back-end processes is malfunctioning or is unavailable.

  >[!TIP]
  >
  >Adobe recommends using `defaultMediaId`.

* Your `zoneID`, which is assigned by Adobe, identifies your company or website. 
* The domain of your assigned ad server. 
* Other targeting parameters.

  You can include these parameters depending on your needs and the needs of the ad provider.
