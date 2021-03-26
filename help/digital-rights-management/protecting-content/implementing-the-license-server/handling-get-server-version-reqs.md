---
title: Handle Get Server Version requests
description: Handle Get Server Version requests
copied-description: yes
---

# Handle Get Server Version requests {#handle-get-server-version-requests}

Adobe Primetime DRM client 3.0 or later sends a Get Server Version request to determine the capabilities of the server. All servers using Primetime DRM SDK 3.0 or later must implement support for Get Server Version requests.

* The request handler class is `com.adobe.flashaccess.sdk.protocol.getversion.GetServerVersionHandler` 
* The request message class is `com.adobe.flashaccess.sdk.protocol.getversion.GetServerVersionRequestMessage` 
* The request URL must be “License Server URL in metadata” + " [!DNL /flashaccess/getServerVersion/v3]"

For Primetime DRM SDK 4.0 or later, the response to a Get Server Version request indicates to clients that the server supports versions 3 and 4 of the Primetime DRM protocol. 
