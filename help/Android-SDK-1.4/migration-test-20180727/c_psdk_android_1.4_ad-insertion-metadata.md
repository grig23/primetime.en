---
description: To allow the ad resolver to work, ad providers, such as , require configuration values to enable your connection to the provider.
seo-description: To allow the ad resolver to work, ad providers, such as , require configuration values to enable your connection to the provider.
seo-title: Ad insertion metadata
title: Ad insertion metadata
uuid: 24e31661-0900-4014-99de-20d021e60628
index: n
internal: n
snippet: y
translate: y
---

# Ad insertion metadata

 <!-- PH element: phrases/primetime-sdk-name --> includes the <!-- PH element: phrases/auditude-name --> library. For your content to include advertising from the <!-- PH element: phrases/auditude-name --> server, your application must provide the following required `AuditudeSettings` information: 
* `mediaID`, which is a unique identifier for the video to be played. The publisher assigns the `mediaID` when submitting video content and ad information to the  <!-- PH element: phrases/auditude-name-long --> server. This ID is used by <!-- PH element: phrases/auditude-name --> to retrieve related advertising information for the video from the server.

* (Optional) `defaultMediaId`, which specifies the ads that are served when the following conditions are met: 
    * Your request to the ad server is invalid, or the content is incorrectly configured.
    * <!-- PH element: phrases/auditude-name --> is experiencing delays in propagating the data.
    * One of the  <!-- PH element: phrases/auditude-name --> back-end processes is malfunctioning or is unavailable.

  >[!TIP]
  >
  >Adobe recommends using `defaultMediaId`. 

* Your `zoneID`, which is assigned by Adobe, identifies your company or website.
* The domain of your assigned ad server.
* Other targeting parameters. You can include these parameters depending on your needs and the needs of the ad provider.

