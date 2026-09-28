---
id: "folderitem"
title: "FolderItem"
description: "Represents a folder in a project that can contain other items."
sidebar_label: "FolderItem"
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

# FolderItem  

## Properties

| Name | Type | Access | Min Version | Description |
| :------ | :------ | :------ | :------ | :------ |
| comment | *string* | RW | 27.0 | A string that holds a comment, up to 15,999 bytes in length after any encoding conversion. The comment is for the user's purpose only; it has no effect on the item's appearance or behavior. |
| dynamicLinkGUID | *string* | R | 27.0 | A unique and persistent identification number used for the dynamic link, in form of `00000000-0000-0000-0000-000000000000`. |
| guides | *Array* | R | 27.0 | An array of objects describing the guides in the item's view. The properties on each entry depend on the version of After Effects. In After Effects 16.1 (CC 2019) and later, each entry has `orientationType`, `positionType`, `position`. In After Effects (Beta) 26.5 and later, each entry also has `color` and `pinned`, and `orientationType`/`positionType` become `GuideOrientationType`/`GuidePositionType` enum values instead of raw integers. |
| id | *number* | R | 27.0 | A unique and persistent identification number used internally to identify an item between sessions. The value of the ID remains the same when the project is saved to a file and later reloaded. However, when you import this project into another project, new IDs are assigned to all items in the imported project. The ID is not displayed anywhere in the user interface. |
| items | *ItemCollection* | R | 27.0 | An ItemCollection object containing Item objects that represent the top-level contents of this folder. Unlike the ItemCollection in the Project object, this collection contains only the top-level items in the folder. The top-level within the folder is not the same as top-level within the project. Only those items that are top-level in the root folder are also top-level in the Project. |
| label | *number* | RW | 27.0 | The label color for the item. Colors are represented by their number (0 for None, or 1 to 16 for one of the preset colors in the Labels preferences). |
| name | *string* | RW | 27.0 | The name of the item as displayed in the Project panel. |
| parentFolder | *FolderItem* | RW | 27.0 | The FolderItem object for the folder that contains this item. If this item is at the top level of the project, this is the project's root folder (`app.project.rootFolder`). |
| selected | *boolean* | RW | 27.0 | When `true`, this item is selected. Multiple items can be selected at the same time. Set to `true` to select the item programmatically, or to `false` to deselect it. |
| typeName | *string* | R | 27.0 | A user-readable name for the item type; for example, "Folder", "Footage", or "Composition". These names are application locale-dependent, meaning that they are different depending on the application's interface language. |
| numItems | *number* | R | 27.0 | The number of items contained in the items collection (`folderItem.items.length`). If the folder contains another folder, only the FolderItem for that folder is counted, not any subitems contained in it. |


## Instance Methods

### addGuide

Returns: *any*

Since: **27.0**

Adds a guide to the item's view and returns its index. Two forms: `addGuide(orientationType, position)` adds a pixel guide using an orientation and pixel position; `addGuide(guideOptions)` adds a guide described by a GuideOptions object (After Effects (Beta) 26.5+).

<HorizontalLine />

### getGuideAsObject

Returns: *\{ orientationType: GuideOrientationType; position: number; positionType: GuidePositionType; color: number[]; pinned: boolean }*

Since: **27.0**

Returns the guide at the specified index as a GuideOptions object, which you can modify and pass back to `setGuide()`. This is a convenient way to read a guide's full state (orientation, position, position type, color, pinning).

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| index | *number* | The index of the guide to read. |

<HorizontalLine />

### item

Returns: *Item*

Since: **27.0**

Returns the top-level item in this folder at the specified index position. Note that "top-level" here means top-level within the folder, not necessarily within the project.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| index | *number* | The position index of the item to retrieve. The first item is at index 1. |

<HorizontalLine />

### remove

Returns: *boolean*

Since: **27.0**

Deletes this item from the project and the Project panel. If the item is a FolderItem, all the items contained in the folder are also removed from the project. No files or folders are removed from the disk.

<HorizontalLine />

### removeGuide

Returns: *boolean*

Since: **27.0**

Removes an existing guide. Choose the guide based on its index inside the `Item.guides` array.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *number* | The index of the guide to be removed. |

<HorizontalLine />

### setGuide

Returns: *any*

Since: **27.0**

Updates an existing guide. Two forms, distinguished by the type of the second argument: `setGuide(position, guideIndex)` moves the guide at `guideIndex` to a new pixel `position`; `setGuide(guideIndex, guideOptions)` applies the properties set on a GuideOptions object to the guide at `guideIndex` (partial update, After Effects (Beta) 26.5+). The two forms take their arguments in the opposite order.

<HorizontalLine />
