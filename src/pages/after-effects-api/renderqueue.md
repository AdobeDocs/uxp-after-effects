---
id: "renderqueue"
title: "RenderQueue"
description: "Represents the After Effects render queue, used to queue and manage compositions for rendering."
sidebar_label: "RenderQueue"
repo: "uxp-aftereffects"
product: "aftereffects"
keywords:
  - Creative Cloud
  - API Documentation
  - UXP
  - Plugins
  - JavaScript
  - ExtendScript
  - SDK
  - C++
  - Scripting
  - After Effects
---

# RenderQueue  

## Properties

| Name | Type | Access | Min Version | Description |
| :------ | :------ | :------ | :------ | :------ |
| canQueueInAME | *boolean* | R | 27.0 | Indicates whether or not there are queued render items in the After Effects render queue. Only queued items can be added to the AME queue. |
| items | *RQItemCollection* | R | 27.0 | A collection of all items in the render queue. |
| lastError | *string* | R | 27.0 | The error message from the most recently failed render, or an empty string if no render error has occurred. Errors are tracked only for the current session, not saved with the project. |
| numItems | *number* | R | 27.0 | The total number of items in the render queue. |
| queueNotify | *boolean* | RW | 27.0 | Read or write the Notify property for the entire Render Queue. This is exposed in the UI as a checkbox in the lower right corner of the Render Queue panel. |
| rendering | *boolean* | R | 27.0 | When `true`, the rendering process is in progress or paused. When `false`, it is stopped. |


## Instance Methods

### item

Returns: *RenderQueueItem*

Since: **27.0**

Returns a render queue item by index

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg1 | *number* | The 1-based position index of the item in the render queue. |

<HorizontalLine />

### pauseRendering

Returns: *boolean*

Since: **27.0**

Pauses or resumes the render queue

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *boolean* | `true` to pause a current render process, `false` to continue a paused render. |

<HorizontalLine />

### queueInAME

Returns: *boolean*

Since: **27.0**

Queues items in AME, optionally rendering immediately

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *boolean* | Whether AME should only queue the render items (`false`) or also start processing its queue immediately (`true`). |

<HorizontalLine />

### render

Returns: *void*

Since: **27.0**

Starts the rendering process. This is the same as clicking Render in the Render Queue panel. The method does not return until the render process is complete. To pause or stop the rendering process, call `RenderQueue.pauseRendering()` or `RenderQueue.stopRendering()` from an `onStatus` or `app.onError` callback. Unlike ExtendScript (which takes no parameters), this binding accepts an optional `skipCheck` parameter to ignore missing source files.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| skipCheck | *boolean* | Optional. When `true`, ignore missing source files instead of raising an error. Defaults to `false`. |

<HorizontalLine />

### renderAsync

Returns: *boolean*

Since: **27.0**

Renders the queue asynchronously

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| skipCheck | *boolean* | Optional. When `true`, ignore missing source files instead of raising an error. Defaults to `false`. |

<HorizontalLine />

### showWindow

Returns: *boolean*

Since: **27.0**

Shows or hides the render queue window

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *boolean* | When `true`, show the Render Queue panel; when `false`, hide it. |

<HorizontalLine />

### stopRendering

Returns: *boolean*

Since: **27.0**

Stops the current render operation

<HorizontalLine />
