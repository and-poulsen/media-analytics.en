---
description: null
seo-description: null
seo-title: Timeout Conditions
title: Timeout Conditions
uuid: aab8c841-d1b0-4c94-a309-d7d9a38de240
index: y
internal: n
snippet: y
translate: y
---

# Timeout Conditions


<a id="section_kmt_qcy_lcb"></a>

**Media Collection API Timeout Conditions: **The Media Collection API, being stateless, does not have the same mechanism as the Video Analytics SDK for issuing a new Session ID when timeout conditions occur. When a timeout condition occurs, the back end will close the session, and all subsequent calls made with that Session ID will be dropped. The logic that handles a Session Timeout must be handled in the client. That is, the player will have to monitor the timeout conditions, and obtain a new Session ID if a timeout occurs.

* **10 Minutes: No API Events - **If the back end does not receive any API events it will close the session.
* **30 Minutes: No Playhead Change - **If the playhead does not move for 30 minutes (e.g., the user hits Pause and walks away), the back end will close the session.

>[!NOTE]
>
>You can also force a session end by sending an ` events` request with the ` sessionEnd` event type.
