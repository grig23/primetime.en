---
title: Replay protection
description: Replay protection
copied-description: yes
---

# Replay protection{#replay-protection}

Replay protection prevents an attacker from replaying a license request message and potentially causing a denial-of-service (DoS) attack against the client (A *denial-of-service* attack is an attempt by attackers to prevent legitimate users of a service from using that service.). For example, a replay attack using the rollback counter could be used to “trick” the License Server into thinking that the DRM client is rolling back its state, causing a suspension of the account.

To learn more about replay protection, see `AbstractRequestMessage.getMessageId()` the *Adobe Access API Reference*. 
