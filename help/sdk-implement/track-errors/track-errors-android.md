---
description: null
seo-description: null
seo-title: Track Errors on Android
title: Track Errors on Android
uuid: 7f0be55b-81c5-4ab1-9e1c-dc5c2c1fb956
index: y
internal: n
snippet: y
translate: y
---

# Track Errors on Android

>[!IMPORTANT]
>
>The following instructions provide guidance for implementation across all 2.x SDKs. If you are implementing a 1.x version of the SDK, you can download the 1.x Developers Guides here: [](../../sdk-implement/download-sdks.md).

1. Track video player errors: 

   ```java
   public void onPlayerError(Observable observable, Object data) {  
       _heartbeat.trackError("videoErrorID"); 
   }
   ```

>[!NOTE]
>
>Tracking video player errors will not stop the video tracking session. If the video player error prevents the playback from continuing, make sure that the video tracking session is closed by calling `trackSessionEnd` after calling `trackError`.
