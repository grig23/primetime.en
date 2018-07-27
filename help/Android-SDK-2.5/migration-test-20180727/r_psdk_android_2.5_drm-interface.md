---
description: The key client-side element of the Primetime DRM solution is the DRM Manager. The sample application that is included with the Android SDK also includes a DRMHelper class that can be used to make certain DRM operations easier to implement.
seo-description: The key client-side element of the Primetime DRM solution is the DRM Manager. The sample application that is included with the Android SDK also includes a DRMHelper class that can be used to make certain DRM operations easier to implement.
seo-title: Primetime DRM interface overview
title: Primetime DRM interface overview
uuid: a40fd427-c211-4a10-9da1-49e63b13970c
index: n
internal: n
snippet: y
translate: y
---

# Primetime DRM interface overview


<a id="section_4DD54E085AB345FE9BE00865E56B28DB"></a>

<!-- PH element: phrases/drm-short --> provides a scalable, efficient workflow to implement content protection in <!-- PH element: phrases/primetime-sdk-name --> applications. You protect and manage the rights to your video content by creating a license for each digital media file.
For more information, see the DRM sample player code that is included in the  <!-- PH element: phrases/primetime-sdk-name --> package.
Here are the most important API elements for working with DRM: 
* A reference in the media player to the DRM manager object that implements the DRM subsystem: 
  ```
  java  MediaPlayer.getDRMManager();
  ```

  >[!TIP]
  >
  >This API will return a valid ` DRMManager` object only after the ` MediaPlayerEvent.DRM_METADATA` is fired. If you call ` getDRMManager()` before this event fires, it might return NULL. 


* The ` DRMHelper` helper class, which is useful when implementing DRM workflows.
* A ` DRMHelper` metadata loader method, which loads DRM metadata when it is located in a separate URL from the media. 
  ```
  java  public static void loadDRMMetadata(final DRMManager drmManager,  
     final String drmMetadataUrl,  
     final DRMLoadMetadataListener loadMetadataListener);
  ```

* A ` DRMHelper` method to check the DRM metadata and determine whether authentication is required. 
  ```
  java  /** 
  * Return whether authentication is needed for the provided 
  * DRMMetadata. 
  * 
  * @param drmMetadata 
  * The desired DRMMetadata on which to check whether auth is needed. 
  * @return whether authentication is required for the provided metadata 
  */ 
  public static boolean isAuthNeeded(DRMMetadata drmMetadata);
  ```

* ` DRMHelper` method to perform authentication. 
  ```
  java  /** 
  * Helper method to perform DRM authentication. 
  * 
  * @param drmManager 
  * the DRMManager, used to perform the authentication. 
  * @param drmMetadata 
  * the DRMMetadata, containing the DRM specific information. 
  * @param authenticationListener 
  * the listener, on which the user can be notified about the 
  * authentication process status. 
  * @param authUser 
  * the DRM username provider by the user. 
  * @param authPass 
  * the DRM password provided by the user. 
  */ 
  public static void performDrmAuthentication(final DRMManager drmManager,  
  final DRMMetadata drmMetadata,  
  final String authUser,  
  final String authPass,  
  final DRMAuthenticationListener authenticationListener);
  ```

* Events that notify your application about various DRM activities and status.


<a id="section_F58941D68EB94A5EBD1C7454D2A1B17A"></a>

For more information about DRM, see the [ DRM documentation ](http://help.adobe.com/en_US/primetime/drm). 