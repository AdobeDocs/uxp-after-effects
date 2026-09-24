---
id: "itemcollection"
title: "ItemCollection"
description: "Represents a collection of Items, such as all the items in a project or in a folder."
sidebar_label: "ItemCollection"
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

# ItemCollection  

## Properties

| Name | Type | Access | Min Version | Description |
| :------ | :------ | :------ | :------ | :------ |
| length | *number* | R | 27.0 | The number of objects in the collection. |


## Instance Methods

### addComp

Returns: *CompItem*

Since: **27.0**

Creates and returns a new CompItem object and adds it to this collection. If the ItemCollection belongs to the project or the root folder, then the new item's `parentFolder` is the root folder. If the ItemCollection belongs to any other folder, the new item's `parentFolder` is that FolderItem.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *string* | The name of the composition. |
| arg1 | *number* | The width of the composition in pixels. |
| arg2 | *number* | The height of the composition in pixels. |
| arg3 | *number* | The pixel aspect ratio of the composition. |
| arg4 | *number* | The duration of the composition in seconds. |
| arg5 | *number* | The frame rate of the composition. |

<HorizontalLine />

### addFolder

Returns: *FolderItem*

Since: **27.0**

Creates and returns a new FolderItem object and adds it to this collection. If the ItemCollection belongs to the project or the root folder, then the new folder's `parentFolder` is the root folder. If the ItemCollection belongs to any other folder, the new folder's `parentFolder` is that FolderItem. To put items in the folder, set the `Item.parentFolder` attribute.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *string* | The name of the folder. |

<HorizontalLine />

### itemByID

Returns: *Item*

Since: **27.0**

Retrieves the item in this collection whose persistent `id` matches the given value. Throws an error if no item with that ID exists in the collection.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *number* | The persistent `id` of the item to retrieve. |

<HorizontalLine />

### private_itemAtIndex

Returns: *Item*

Since: **27.0**

Retrieves the item in this collection at the given index. The first item is at index 1. Used internally to implement `items[index]`-style access; not intended to be called directly.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *number* | The index of the item to retrieve. |

<HorizontalLine />
