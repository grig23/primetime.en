---
title: Implement identity-based domain registration
description: Implement identity-based domain registration
copied-description: yes
---

# Implement identity-based domain registration{#implement-identity-based-domain-registration}

1. Create a DRM policy with mandatory domain registration.
1. Specify the server's host and port for the domain server URL.

   In your [!DNL .properties] file, set: 

   ```
   policy.domain.url=https://[server:port] 
   ```

1. Make authentication with a username and password mandatory.

   In your [!DNL .properties] file, set: 

   ```
   policy.domain.anonymous=false 
   ```
