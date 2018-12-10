---
seo-title: Upgrading the Adobe Primetime DRM Server for Protected Streaming
title: Upgrading the Adobe Primetime DRM Server for Protected Streaming
uuid: aa107a54-1067-475d-9db3-d0df553db14c
index: y
internal: n
snippet: y
---

# Upgrading the Adobe Primetime DRM Server for Protected Streaming{#upgrading-the-adobe-primetime-drm-server-for-protected-streaming}

If you want to upgrade a server that runs the Primetime DRM Server for Protected Streaming, you need to replace the `flashaccessserver.war` file that has been deployed on your application server with the file that has been included with the latest Primetime DRM.

If you want to use the new configuration options, you need to update your server’s `flashaccess-tenant.xml`. You also need to update [!DNL jsafe.dll] or [!DNL libjsafe.so] with the version that has been included with the latest Primetime DRM. 