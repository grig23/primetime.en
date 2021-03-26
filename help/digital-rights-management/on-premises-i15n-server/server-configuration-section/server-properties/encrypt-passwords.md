---
title: Encrypt Passwords
description: Encrypt Passwords
copied-description: yes
---

# Encrypt Passwords{#encrypt-passwords}

The properties files include several password values that you should not enter as plain text. Encrypt these values using the following command: 

`java -jar adobe-flashaccess-i15n-setup.jar password`

This command will output an encrypted password, which you then use in the properties files.

>[!NOTE]
>This is not the utility used for encrypting License Server passwords.

