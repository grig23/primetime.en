---
title: Configure SSL on your BEES server
description: Configure SSL on your BEES server
copied-description: yes
---

# Configure SSL on your BEES server {#configure-ssl-on-your-bees-server}

1. Provide your server SSL certificate to your Adobe contact who supplied this software.

   The certificate will be added as a trusted certificate to the  Primetime Cloud DRM trust store.
1. To enable client authentication for the SSL connection (disabled in this version):
   1. Add the `[!DNL clouddrm-transport.cer]` and `[!DNL AdobeFlashAccessIntermediateCA.cer]` certificates to the trust store used for client authentication.
   1. Enable client authentication in your SSL configuration.
