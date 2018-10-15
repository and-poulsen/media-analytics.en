---
description: null
seo-description: null
seo-title: 1.x to 2.x API Conversion
title: 1.x to 2.x API Conversion
uuid: 03254c40-fda5-4825-bb81-5f9b003b060b
index: y
internal: n
snippet: y
translate: y
---

# 1.x to 2.x API Conversion

**VHL 2.x API References:**

* [Android API Reference](https://adobe-marketing-cloud.github.io/video-heartbeat-v2/reference/android/index.html)
* [iOS API Reference](https://adobe-marketing-cloud.github.io/video-heartbeat-v2/reference/ios/index.html)
* [JS API Reference](https://adobe-marketing-cloud.github.io/video-heartbeat-v2/reference/javascript/index.html)

#### Required Track APIs:
|  VHL 1.x | VHL 2.x |
|---|---|
| `videoPlayerPlugin.trackVideoLoad()` | N/A |
| `videoPlayerPlugin.trackSessionStart()` | ` [mediaHeartbeat.trackSessionStart(mediaObject, mediaCustomMetadata)](https://adobe-marketing-cloud.github.io/video-heartbeat-v2/reference/javascript/MediaHeartbeat.html#trackSessionStart)` |
| `videoPlayerPlugin.trackPlay()` | ` [mediaHeartbeat.trackPlay()](https://adobe-marketing-cloud.github.io/video-heartbeat-v2/reference/javascript/MediaHeartbeat.html#trackPlay)` |
| `videoPlayerPlugin.trackPause()` | ` [mediaHeartbeat.trackPause()](https://adobe-marketing-cloud.github.io/video-heartbeat-v2/reference/javascript/MediaHeartbeat.html#trackPause)` |
| `videoPlayerPlugin.trackComplete()` | ` [mediaHeartbeat.trackComplete()](https://adobe-marketing-cloud.github.io/video-heartbeat-v2/reference/javascript/MediaHeartbeat.html#trackComplete)` |
| `videoPlayerPlugin.trackVideoUnload()` | ` [mediaHeartbeat.trackSessionEnd()](https://adobe-marketing-cloud.github.io/video-heartbeat-v2/reference/javascript/MediaHeartbeat.html#trackSessionEnd)` |
| `videoPlayerPlugin.trackApplicationError()` | N/A |
| `videoPlayerPlugin.trackVideoPlayerError()` | ` [mediaHeartbeat.trackError()](https://adobe-marketing-cloud.github.io/video-heartbeat-v2/reference/javascript/MediaHeartbeat.html#trackError)` |

All of the optional tracking APIs such as (Ads, Chapters, Bitrate change, Seeking, and Buffering) are now part of a single `trackEvent` API. The ` [trackEvent](https://adobe-marketing-cloud.github.io/video-heartbeat-v2/reference/javascript/MediaHeartbeat.html#trackEvent)` API receives a constant parameter that represents the type of event that it is intended to track:

#### Optional trackEvent APIs:
|  VHL 1.x | VHL 2.x |
|---|---|
| Return a valid `AdBreakInfo` in `VideoPlayerPlugin.getAdBreakInfo()` | `trackEvent(Event.AdBreakStart)` |
| Return null in `VideoPlayerPlugin.getAdBreakInfo()` | `trackEvent(Event.AdBreakComplete)` |
| `playerPlugin.trackAdStart()` | `trackEvent(Event.AdStart, adObject, adCustomMetadata)` |
| `playerPlugin.trackAdComplete()` | `trackEvent(Event.AdComplete)` |
| Return null in `VideoPlayerPlugin.getAdInfo()` | `trackEvent(Event.AdSkip)` |
| `playerPlugin.trackChapterStart()` | `trackEvent(Event.ChapterStart, chapterObject, chapterCustomMetadata)` |
| `playerPlugin.trackChapterComplete()` | `trackEvent(Event.ChapterComplete)` |
| Return null in `VideoPlayerPlugin.getChapterInfo()` | `trackEvent(Event.ChapterSkip)` |
| `playerPlugin.trackSeekStart()` | `trackEvent(Event.SeekStart)` |
| `playerPlugin.trackSeekComplete()` | `trackEvent(Event.SeekComplete)` |
| `playerPlugin.trackBufferStart()` | `trackEvent(Event.BufferStart)` |
| `playerPlugin.trackBufferComplete()` | `trackEvent(Event.BufferComplete)` |
| `playerPlugin.trackBitrateChange()` | `trackEvent(Event.BitrateChange)` |
| `playerPlugin.trackTimedMetadata()` | `trackEvent(Event.TimedMetadataUpdate)` |
