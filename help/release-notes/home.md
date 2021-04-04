---
title: Primetime Release Notes
description: Primetime Release Notes
copied-description: yes
exl-id: 29087a3e-f16e-4510-8d3a-ed2229700899
---
# Primetime Release Notes

Welcome to the Adobe Primetime Release Notes. The documents listed in the left navigation provide release-specific information, system requirements, limitations, fixed issues, and known issues.

## Enhancements and fixes in TVSDK 3.13 iOS

The release introduces support for DEMUXED 'HLS/CMAF' (preroll, midroll, and postroll) ads for LIVE, VOD, and FER streams.

For other fixes and details, see [TVSDK for iOS Release Notes](../release-notes/tvsdk-3x-ios.md)

## Enhancements and fixes in PTAI 21.2.2

The release includes support for EXT-X-IMAGE-STREAM-INF stream insertion/synchronization in HLS streams. The feature is enabled through a server-side configuration. Contact your technical account representative to enable the feature..

## Fixes in TVSDK 3.13 Android

This release provides a workaround to the issue about the Widevine DRM stream freezing or showing black frames on ABR switch on FireTV devices, which include Fire TV 3rd generation Pendant and Fire TV Cube 1st and 2nd generation devices.

To resolve the issue, set the API `MediaPlayer.flushVideoDecoderOnHeaderChange(true)` for the specified Fire TV devices before initiating playback. The default value is false.

Check out the [TVSDK for Android Release Notes](../release-notes/tvsdk-3x-android.md) for more information.

## Enhancements and fixes in TVSDK 3.12 iOS Release Notes

The release focused on resolving top customer issues.

Check out for more information about the current released version for [iOS](../release-notes/tvsdk-3x-ios.md).

## See also

| User Guide | Description |
|--- |--- |
| [Primetime Programming Help](/help/programming/home.md) | Allows you to learn to develop applications and video players using Java on Android devices and Objective-C on iOS devices. |
| [Primetime Migration & Conversion Help](/help/migration-guides/home.md) | Explains the conversion and migration process to move from your existing Primetime TVSDK Suite to the next-generation suite. |
| [Reference Implementation](/help/android-reference-implementation/home.md) | Helps understand the TVSDK and modify the feature managers to customize your personal player. |
| [Primetime API references](/help/reference/api-references.md) | Provides detailed information about TVSDK functions, data structures and other programming constructs. |
| [Digital Rights Management](/help/digital-rights-management/home.md) | Helps you learn more about various user scenarios in Digital Rights Management (DRM) |
| [Primetime Ad Insertion Help](/help/primetime-ad-insertion/home.md) | Explains how to monetize content by inserting user-targeted dynamic ads on the server and engage audience with personalized ads. |
| [Archives](https://helpx.adobe.com/primetime/archives.html) | Download PDFs of the archived documentation. |

## Helpful resources

* [Get to Know Adobe Primetime](https://www.adobe.com/in/marketing/primetime.html)

* [Concurrency Monitoring](https://tve.helpdocsonline.com/concurrency-monitoring-introduction)

* [Primetime Authentication](https://tve.helpdocsonline.com/home)

* [Adobe Primetime DRM Forums](https://forums.adobe.com/community/adobe_access)

* [Adobe Primetime Developer Resources](https://www.adobe.com/devnet/primetime.html)
