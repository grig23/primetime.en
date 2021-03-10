---
description: You can integrate late-binding or alternate audio streams into your player by creating an alternate audio feature manager.
title: Integrate late-binding audio
---

# Integrate late-binding audio {#integrate-late-binding-audio}

You can integrate late-binding or alternate audio streams into your player by creating an alternate audio feature manager.

* To create an alternate audio manager:

  ```java
  AAManager aaManager = new AAManagerOn(); 
  ```

* To use the ManagerFactory to enable alternate audio, make sure the following line of code is in the `PlayerFragment.java` file:

  ```java
  aaManager = ManagerFactory.getAAManager( 
  <b>true</b>,config, mediaPlayer);
  ```

  To disable alternate audio:

  ```java
  aaManager = ManagerFactory.getAAManager( 
  <b>false</b>,config, mediaPlayer);
  ```

