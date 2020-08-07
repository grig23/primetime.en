---
description: null
seo-description: null
seo-title: Allow list for Primetime DRM applications allowed to play protected content
title: Allow list for Primetime DRM applications allowed to play protected content
uuid: 23dd4faf-7992-4ee9-97ce-c6004ee995c2
---

# Allow list for Primetime DRM applications allowed to play protected content {#allowlist-for-primetime-drm-applications-allowed-to-play-protected-content}

A allow list specifies the AIR, iOS, and Android applications that are allowed to play content. It also specifies AIR and iOS application IDs, minimum version, maximum version, and publisher ID.

Example use case: Use this rule to limit playback to a particular application, or to control the version of the application that can access content. 

>[!NOTE]
>
>If you use Adobe Flash Builder to build protected applications, you must make sure that you do not deploy the application in Debug mode. When you deploy an application in Debug mode, the Flash Builder appends `.debug` to the AIR application ID, which then causes the allow list functionality in Primetime DRM to behave unexpectedly.
