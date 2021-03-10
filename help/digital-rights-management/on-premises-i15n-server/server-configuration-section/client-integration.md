---
title: Client Integration
description: Client Integration
copied-description: yes
---

# Client Integration{#client-integration}

In order to direct the client into individualizing against the On Premises Individualization server (as opposed to the Adobe Hosted Global Individualization Server), the client should utilize the previously created On Premises DRM Metadata. Having an un-individualized client perform a license acquisition or initialize DRM, using the special metadata, will result in the client connecting to the custom Individualization Server URL.

A sample code snippet is included in the [!DNL client_sample] folder. 
