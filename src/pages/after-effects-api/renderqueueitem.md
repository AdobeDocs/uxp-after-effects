---
id: "renderqueueitem"
title: "RenderQueueItem"
description: "Represents a composition queued for rendering in the render queue."
sidebar_label: "RenderQueueItem"
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

# RenderQueueItem  

## Properties

| Name | Type | Access | Min Version | Description |
| :------ | :------ | :------ | :------ | :------ |
| comment | *string* | RW | 27.0 | A user comment for this render queue item. |
| comp | *CompItem* | R | 27.0 | The composition that will be rendered by this render-queue item. To change the composition, delete this item and create a new one. |
| elapsedSeconds | *number* | R | 27.0 | The number of seconds spent rendering this item. |
| logType | *number* | RW | 27.0 | A log type for this item, indicating which events are logged while it renders. One of `LogType.ERRORS_ONLY`, `LogType.ERRORS_AND_SETTINGS`, `LogType.ERRORS_AND_PER_FRAME_INFO`. |
| numOutputModules | *number* | R | 27.0 | The total number of Output Modules assigned to this item. |
| outputModules | *OMCollection* | R | 27.0 | The collection of Output Modules for the item. |
| queueItemNotify | *boolean* | RW | 27.0 | Reads and writes the Notify checkbox for this item in the Render Queue panel's Notify column (hidden by default). |
| skipFrames | *number* | RW | 27.0 | The number of frames to skip when rendering this item, in the range `[0..99]`, for faster test renders. `0` renders every frame; `1` renders every other frame ("on twos"). Total length of time remains unchanged. |
| startTime | *number* | R | 27.0 | The day and time this item started rendering, or `null` if it hasn't started. |
| status | *number* | R | 27.0 | The current render status of the item. One of `RQItemStatus.WILL_CONTINUE`, `NEEDS_OUTPUT`, `UNQUEUED`, `QUEUED`, `RENDERING`, `USER_STOPPED`, `ERR_STOPPED`, `DONE`. |
| templates | *string[]* | R | 27.0 |  |
| timeSpanDuration | *number* | RW | 27.0 | The duration in seconds of the composition to be rendered (end time minus start time). Same as setting a custom end time in the Render Settings dialog. |
| timeSpanStart | *number* | RW | 27.0 | The time in the composition, in seconds, at which rendering begins. Same as setting a custom start time in the Render Settings dialog. |
| render | *boolean* | RW | 27.0 | When `true`, the item is rendered when the render queue is started, and its `status` is set to `RQItemStatus.QUEUED`. When set to `false`, `status` is set to `RQItemStatus.UNQUEUED`. |


## Instance Methods

### applyTemplate

Returns: *boolean*

Since: **27.0**

Applies a Render Settings template to the item.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| templateName | *string* | The name of the template to apply. |

<HorizontalLine />

### duplicate

Returns: *RenderQueueItem*

Since: **27.0**

Creates a duplicate of this item and adds it to the render queue. Duplicating an item whose status is "Done" sets the new item's status to "Queued".

<HorizontalLine />

### getSetting

Returns: *string*

Since: **27.0**

Gets a specific Render Queue Item setting by name. Appending `-str` to the key name returns the string version of the setting.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| settingName | *string* | The name of the setting to get. Append `-str` to get the string version. |

<HorizontalLine />

### getSettings

Returns: *\{ [settingName: string]: string \| number \| boolean \| \{ x: number; y: number } \| \{ [key: string]: string \| number } }*

Since: **27.0**

Gets all settings for this item as a key-value object, in the format specified by the `GetSettingsFormat` value passed in.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| format | *number* | A `GetSettingsFormat` value: `STRING`, `STRING_SETTABLE`, `NUMBER`, or `NUMBER_SETTABLE`, controlling which settings are included and how values are formatted. |

<HorizontalLine />

### onComplete

Returns: *void*

Since: **27.0**

Registers a callback function to be invoked when this item finishes rendering.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| callback | *(...args: any[]) =\> void* | The function to call when this item finishes rendering. |

<HorizontalLine />

### onReorder

Returns: *void*

Since: **27.0**

Registers a callback function to be invoked when this item is reordered in the render queue.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| callback | *(...args: any[]) =\> void* | The function to call when this item is reordered. |

<HorizontalLine />

### onStatus

Returns: *void*

Since: **27.0**

Registers a callback function to be invoked whenever this item's `status` changes.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| callback | *(...args: any[]) =\> void* | The function to call when this item's status changes. |

<HorizontalLine />

### outputModule

Returns: *OutputModule*

Since: **27.0**

Gets the output module at the specified index position.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| index | *number* | The position index of the output module, in the range `[1..numOutputModules]`. |

<HorizontalLine />

### remove

Returns: *boolean*

Since: **27.0**

Removes this item from the render queue.

<HorizontalLine />

### saveAsTemplate

Returns: *boolean*

Since: **27.0**

Saves the item's current render settings as a new template with the specified name.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| name | *string* | The name of the new template. |

<HorizontalLine />

### setSetting

Returns: *boolean*

Since: **27.0**

Sets a specific setting for this item by name.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| settingName | *string* | The name of the setting to set. |
| value | *string* | The new value, as a string or number. |

<HorizontalLine />

### setSettings

Returns: *boolean*

Since: **27.0**

Sets multiple settings for this item from a key-value object.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| settings | *Object* | An object of setting name/value pairs to apply. |

<HorizontalLine />
