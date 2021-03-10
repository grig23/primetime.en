---
title: Firewall Rules
description: Firewall Rules
copied-description: yes
---

# Firewall Rules{#firewall-rules}

To secure access to the Individualization server, only certain application paths need to be exposed. The Individualization server must accept requests from clients to these paths:

* [!DNL /flashaccess/i15n/*] 
* [!DNL /flashaccess/status] 
* [!DNL /crossdomain.xml]

Service paths, such as [!DNL /flashaccess/admin/*] (i.e., status and admin pages) must only be accessible from within the firewall. No parts of the Key Generation Server should be accessed from outside the firewall. 
