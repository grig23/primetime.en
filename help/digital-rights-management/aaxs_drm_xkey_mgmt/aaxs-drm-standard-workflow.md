---
seo-title: Standard AAXS DRM Workflow
title: Standard AAXS DRM Workflow
uuid: 8d5eb479-572f-46df-8529-6f2258313cc2
index: y
internal: n
snippet: y
---

# Standard AAXS DRM Workflow{#standard-aaxs-drm-workflow}

1. (Package) The AAXS Java SDK generates a random CEK.
1. (Package) The CEK is used to encrypt content.
1. (Package) The CEK is encrypted using the AAXS License Server's public key.
1. (Package) The encrypted CEK is inserted into the content's DRM metadata.
1. The device attempts to play content by requesting a license from the AAXS server.
1. (Licensing) The AAXS server uses its private key to decrypt the CEK from the metadata.
1. (Licensing) The AAXS server issues to the device a license that contains the CEK.