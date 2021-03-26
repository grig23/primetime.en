---
description: You can choose a custom starting point for when to enter a DVR stream instead of the default behavior of entering the DVR stream at the beginning using the ConfigProvider class.
title: Choosing a custom starting point for DVR
---

# Choosing a custom starting point for DVR {#choosing-a-custom-starting-point-for-dvr}

You can choose a custom starting point for when to enter a DVR stream instead of the default behavior of entering the DVR stream at the beginning using the ConfigProvider class.

To set the start time through the [ConfigProvider](https://help.adobe.com/en_US/primetime/api/reference_implementation/android/javadoc/com/adobe/primetime/reference/config/ConfigProvider.html) class:

1. Enable [isCustomPositionPrefEnabled()](https://help.adobe.com/en_US/primetime/api/reference_implementation/android/javadoc/com/adobe/primetime/reference/config/ConfigProvider.html#isCustomPositionPrefEnabled()).
1. Set the start time in [retrieveStartTimePref()](https://help.adobe.com/en_US/primetime/api/reference_implementation/android/javadoc/com/adobe/primetime/reference/config/IPlaybackConfig.html#iretrieveStartTimePref()).
1. Check that the custom start position is enabled.
