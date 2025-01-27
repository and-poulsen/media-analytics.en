---
title: Track seeking on Chromecast
description: This topic describes implementing seek tracking using the Media SDK on Chromecast.
uuid: 8018e6c4-fed9-4de7-9eae-c720da55ad8c
exl-id: 03be8ed3-ae3a-4e9a-b667-0d9280a844a1
---
# Track seeking on Chromecast{#track-seeking-on-chromecast}

>[!IMPORTANT]
>
>The following instructions provide guidance for implementation across all 2.x SDKs. If you are implementing a 1.x version of the SDK, you can download the 1.x Developers Guides here: [Download SDKs.](/help/sdk-implement/download-sdks.md)

## Seek tracking constants

|  Constant name  | Description&nbsp;&nbsp;&nbsp;&nbsp;  |
|---|---|
|  `SeekStart`  | Constant for tracking Seek Start event.  |
|  `SeekComplete`  | Constant for tracking Seek Complete event.  |

## Implement seeking

1. Listen for the playback seeking events from the media player, and on seek start event notification, track seeking using the `SeekStart` event: [trackEvent](https://adobe-marketing-cloud.github.io/media-sdks/reference/chromecast/ADBMobile.media.html#.trackEvent) 

     ```
     ADBMobile.media.trackEvent(ADBMobile.media.Event.SeekStart); 
     ```

1. On seek complete notification from the media player, track the end of seeking using the `SeekComplete` event: [trackEvent](https://adobe-marketing-cloud.github.io/media-sdks/reference/chromecast/ADBMobile.media.html#.trackEvent) 

    ```
    ADBMobile.media.trackEvent(ADBMobile.media.Event.SeekComplete); 
    ```

See the tracking scenario [VOD playback with seeking in the main content](/help/sdk-implement/tracking-scenarios/vod-seeking.md) for more information.
