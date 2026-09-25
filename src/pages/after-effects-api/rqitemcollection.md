---
id: "rqitemcollection"
title: "RQItemCollection"
description: "Represents a collection of items in the render queue."
sidebar_label: "RQItemCollection"
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

# RQItemCollection  

## Properties

| Name | Type | Access | Min Version | Description |
| :------ | :------ | :------ | :------ | :------ |
| length | *number* | R | 27.0 | The number of objects in the collection. |


## Instance Methods

### add

Returns: *RenderQueueItem*

Since: **27.0**

Adds a composition to the Render Queue, creating a RenderQueueItem.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| intoComp | *object* | The composition to be added. |

<HorizontalLine />

### getByIndex

Returns: *RenderQueueItem*

Since: **27.0**

Returns the render queue item at the specified index.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *number* | The 1-based index of the item to retrieve, consistent with this collection's other indexing. |

<HorizontalLine />
