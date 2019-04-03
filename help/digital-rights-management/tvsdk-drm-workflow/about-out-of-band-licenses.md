---
seo-title: Out-of-band licenses overview
title: Out-of-band licenses overview
uuid: 82e4529a-ee1b-4c0c-8885-e0e68319d1a0
---

# Out-of-band licenses {#out-of-band-licenses}

Licenses can also be obtained out-of-band (without contacting a Primetime DRM license Server) by storing the license on disk and in memory using the `storeVoucher()` method.

To play encrypted videos in Primetime, the respective runtime needs to obtain the license for that video. The license contains the video's decryption key and is generated by the Primetime DRM license server that the customer has deployed.

The runtime generally obtains this license by sending a license request to the Primetime DRM license server indicated in the video's DRM metadata ( `DRMContentData` class). The application can trigger this license request by calling the `DRMManager.loadVoucher()` method.

`DRMManager.storeVoucher()` allows the application to send licenses that it has obtained out-of- band. The runtime can then skip the license request process and use the forwarded licenses for playing encrypted videos. The license still needs to be generated by the Primetime DRM license server before it can be obtained out-of-band. However, you have the option of hosting the licenses on any HTTP server, instead of an Primetime DRM license server.

`DRMManager.storeVoucher()` is also used to support license sharing between multiple devices. After Primetime DRM 3.0, this feature is referred to as "Device Domain Support". If your deployment supports this use case, you can register multiple machines to a device group using the `DRMManager.addToDeviceGroup()` method. If there is a machine with a valid domain-bound license for a given content, the application can then extract the serialized license using the `DRMVoucher.toByteArray()` method and on your other machines you can import the licenses using the `DRMManager.storeVoucher()` method.

## About device registration {#about-device-registration}

All Primetime DRM licenses, at creation time, must be bound to an end-entity. Binding is the cryptographic process of only allowing a specific entity the ability to consume the license. This is necessary as to prevent "floating licenses" which can be used by any arbitrary device. For Primetime DRM to "pre-generate" licenses, this means the "target" of these pre-generated licenses must be known ahead of time. Primetime DRM refers to this as "Device Registration".

## Register a device {#register-a-device}

Let us assume that you have performed the following tasks:

* You have set up the Primetime DRM Server SDK. 
* You have set up an HTTP server for issuing pre-generated licenses. 
* You have created a Primetime application to view the protected content.

 The device registration phase involves the following actions: 

1. The application creates a randomly generated ID.
1. The application invokes the `DRMManager.authenticate()` method. The application must include the randomly generated ID in the authentication request. For instance, include the ID in the username field.
1. The action mentioned in Step 2 will result in Primetime DRM sending an authentication request to the customer's server. This request includes the device certificate:
   1. The server extracts the device certificate and the generated ID from the request and stores.
   1. The customer sub-system pre-generates licenses for this device certificate, stores them and grants access to them  in a way that associates them with the generated ID. .
1. The server responds to the request with a "success" message.
1. The application stores the generated ID.

After the device registration, the application uses the generated ID in the same way as it would have used the device ID in the previous scheme:
1. The application will try to locate the generated ID. 
1. If the generated ID is found, the application will use the generated ID while downloading the pre-generated licenses. The application will send the licenses to the Primetime DRM client for consumption using the `DRMManager.storeVoucher()` method. . 
1. If the generated ID is not found, the application will go through the device registration procedure.

## DRM factory reset {#drm-factory-reset}

When the user of the device invokes the DRM factory reset option, the device certificate will be purged. To continue playing the protected content, the application must go through the device registration procedure again. If the application sends an outdated pre-generated license, the Primetime DRM client will reject it since the license was encrypted for an older device ID.

* Flash API: [DRMManager.resetDRMVouchers()](https://help.adobe.com/en_US/FlashPlatform/reference/actionscript/3/flash/net/drm/DRMManager.html#resetDRMVouchers()) - (Can only be called in response to certain un-recoverable DRM error codes.) 
* iOS API: [DRMManager resetDRM](https://help.adobe.com/en_US/primetime/api/drm-apis/client/ios/interface_d_r_m_manager.html#a0dd6c9662428583196e0419d3ea69446) 
* Android API: [DRMManager.resetDRM()](https://help.adobe.com/en_US/primetime/api/drm-apis/client/android/com/adobe/ave/drm/DRMManager.html#resetDRM(com.adobe.ave.drm.DRMOperationErrorCallback,%20com.adobe.ave.drm.DRMOperationCompleteCallback))