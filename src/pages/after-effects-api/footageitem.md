---
id: "footageitem"
title: "FootageItem"
description: "Represents an imported file or a solid color used as a layer source in a composition."
sidebar_label: "FootageItem"
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

# FootageItem  

## Properties

| Name | Type | Access | Min Version | Description |
| :------ | :------ | :------ | :------ | :------ |
| comment | *string* | RW | 27.0 | A string that holds a comment, up to 15,999 bytes in length after any encoding conversion. The comment is for the user's purpose only; it has no effect on the item's appearance or behavior. |
| duration | *number* | RW | 27.0 | Returns the duration, in seconds, of the item. Still footage items have a duration of 0. In a FootageItem, the value is linked to the `duration` of the `mainSource` object, and is read-only. |
| dynamicLinkGUID | *string* | R | 27.0 | A unique and persistent identification number used for the dynamic link, in form of `00000000-0000-0000-0000-000000000000`. |
| file | *string* | R | 27.0 | The file path for the footage's source file. If the FootageItem's `mainSource` is a FileSource, this is the same as `FootageItem.mainSource.file`. Otherwise it is `null`. |
| footageMissing | *boolean* | R | 27.0 | When `true`, the AVItem is a placeholder, or represents footage with a source file that cannot be found. In this case, the path of the missing source file is in the `missingFootagePath` attribute of the footage item's source-file object. |
| frameDuration | *number* | RW | 27.0 | Returns the length of a frame for this AVItem, in seconds. This is the reciprocal of `frameRate`. If the AVItem is a FootageItem, this value is linked to the `mainSource`, and is read-only. To change it, set the `conformFrameRate` of the `mainSource` object. This sets both the `frameRate` and `frameDuration` of the FootageItem. |
| frameRate | *number* | RW | 27.0 | The frame rate of the AVItem, in frames-per-second. This is the reciprocal of the `frameDuration`. In a FootageItem, the value is linked to the `frameRate` of the `mainSource` object, and is read-only. To change it, set the `conformFrameRate` of the `mainSource` object. This sets both the `frameRate` and `frameDuration` of the FootageItem. |
| frameTime | *number* | RW | 27.0 | The current time of the item, expressed in frames - an alternative to the `time` attribute, which uses seconds. |
| guides | *Array* | R | 27.0 | An array of objects describing the guides in the item's view. The properties on each entry depend on the version of After Effects. In After Effects 16.1 (CC 2019) and later, each entry has `orientationType`, `positionType`, `position`. In After Effects (Beta) 26.5 and later, each entry also has `color` and `pinned`, and `orientationType`/`positionType` become `GuideOrientationType`/`GuidePositionType` enum values instead of raw integers. |
| hasAudio | *boolean* | R | 27.0 | When `true`, the AVItem has an audio component. In a FootageItem, the value is linked to the `mainSource` object. |
| hasVideo | *boolean* | R | 27.0 | When `true`, the AVItem has a video component. In a FootageItem, the value is linked to the `mainSource` object. |
| height | *number* | RW | 27.0 | The height of the item in pixels. In a FootageItem, the value is linked to the `mainSource` object, and is read/write only if the `mainSource` object is a SolidSource. Otherwise, it is read-only. |
| id | *number* | R | 27.0 | A unique and persistent identification number used internally to identify an item between sessions. The value of the ID remains the same when the project is saved to a file and later reloaded. However, when you import this project into another project, new IDs are assigned to all items in the imported project. The ID is not displayed anywhere in the user interface. |
| isMediaReplacementCompatible | *boolean* | R | 27.0 | Test whether the AVItem can be used as an alternate source when calling `Property.setAlternateSource()`. Returns `true` if the item can be used, or otherwise `false`. If the AVItem is a FootageItem, then its FootageSource should not be a SolidSource; if the FootageSource is a FileSource then that FileSource should not point to a non-media file (e.g. a JSX script file); setting the AVItem cannot create a cyclical reference within the project. |
| label | *number* | RW | 27.0 | The label color for the item. Colors are represented by their number (0 for None, or 1 to 16 for one of the preset colors in the Labels preferences). |
| mainSource | *FootageSource* | R | 27.0 | The footage source, an object that contains all of the settings related to that footage item, including those that are normally accessed through the Interpret Footage dialog box. The attribute is read-only. To change its value, call one of the FootageItem "replace" methods. If this is a FileSource object, and the `footageMissing` value is `true`, the path to the missing footage file is in the `FileSource.missingFootagePath` attribute. |
| name | *string* | RW | 27.0 | The name of the item, as shown in the Project panel. In a FootageItem, the value is linked to the `mainSource` object. If the `mainSource` object is a `FileSource`, this value controls the display name in the Project panel, but does not affect the file name. |
| parentFolder | *FolderItem* | RW | 27.0 | The FolderItem object for the folder that contains this item. If this item is at the top level of the project, this is the project's root folder (`app.project.rootFolder`). |
| pixelAspect | *number* | RW | 27.0 | The pixel aspect ratio (PAR) of the item. In a FootageItem, the value is linked to the `mainSource` object. |
| proxySource | *FootageSource \| null* | R | 27.0 | The FootageSource being used as a proxy. The attribute is read-only; to change it, call any of the AVItem methods that change the proxy source: `setProxy()`, `setProxyWithSequence()`, `setProxyWithSolid()`, or `setProxyWithPlaceholder()`. |
| selected | *boolean* | RW | 27.0 | When `true`, this item is selected. Multiple items can be selected at the same time. Set to `true` to select the item programmatically, or to `false` to deselect it. |
| time | *number* | RW | 27.0 | The current time of the item when it is being previewed directly from the Project panel. This value is a number of seconds. It is an error to set this value for a FootageItem whose `mainSource` is still (`item.mainSource.isStill` is `true`). |
| typeName | *string* | R | 27.0 | A user-readable name for the item type; for example, "Folder", "Footage", or "Composition". These names are application locale-dependent, meaning that they are different depending on the application's interface language. |
| useProxy | *boolean* | RW | 27.0 | When `true`, a proxy is used for the item. It is set to `true` by all the `SetProxy` methods, and to `false` by the `SetProxyToNone()` method. |
| usedIn | *Array* | R | 27.0 | All the compositions that use this AVItem. Note that upon retrieval, the array value is copied, so it is not automatically updated. |
| width | *number* | RW | 27.0 | The width of the item, in pixels. In a FootageItem, the value is linked to the `mainSource` object, and is read/write only if the `mainSource` object is a SolidSource. Otherwise, it is read-only. |


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

### getRenderGUID

Returns: *DeferredCall*

Since: **27.0**

Asynchronously computes a GUID that uniquely identifies the rendered state of this footage item at the specified time, useful for detecting whether a frame's render output has changed. Returns a `DeferredCall` that resolves to a 36-character GUID string.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| seconds | *number* | The time, in seconds, at which to compute the GUID. |
| thread | *number* | A `ProjectThread` enum value specifying which thread to perform the computation on. |
| trace | *boolean* | Whether to enable verbose tracing for this call. |

<HorizontalLine />

### openInViewer

Returns: *Viewer*

Since: **27.0**

Opens the footage in a Footage panel, and moves the Footage panel to front and gives it focus. Missing and placeholder footage can be opened using this method, but cannot manually (via double-clicking it).

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

### replace

Returns: *boolean*

Since: **27.0**

Changes the source of this FootageItem to the specified file. In addition to loading the file, the method creates a new FileSource object for the file and sets `mainSource` to that object. In the new source object, it sets the `name`, `width`, `height`, `frameDuration`, and `duration` attributes based on the contents of the file. The method preserves interpretation parameters from the previous `mainSource` object. If the specified file has an unlabeled alpha channel, the method estimates the alpha interpretation.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *string* | The file path to use as the footage main source. |

<HorizontalLine />

### replaceWithPlaceholder

Returns: *boolean*

Since: **27.0**

Changes the source of this FootageItem to the specified placeholder. Creates a new PlaceholderSource object, sets its values from the parameters, and sets `mainSource` to that object.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *string* | The name of the placeholder. |
| arg1 | *number* | The width of the placeholder in pixels. |
| arg2 | *number* | The height of the placeholder in pixels. |
| arg3 | *number* | The frame rate of the placeholder. |
| arg4 | *number* | The duration of the placeholder in seconds. |

<HorizontalLine />

### replaceWithSequence

Returns: *boolean*

Since: **27.0**

Changes the source of this FootageItem to the specified image sequence. In addition to loading the file, the method creates a new FileSource object for the file and sets `mainSource` to that object. In the new source object, it sets the `name`, `width`, `height`, `frameDuration`, and `duration` attributes based on the contents of the file. The method preserves interpretation parameters from the previous `mainSource` object. If the specified file has an unlabeled alpha channel, the method estimates the alpha interpretation.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *string* | The file path of the first file in the sequence to be used as the footage main source. |
| arg1 | *boolean* | When `true`, use the "Force alphabetical order" option. |

<HorizontalLine />

### replaceWithSolid

Returns: *boolean*

Since: **27.0**

Changes the source of this FootageItem to the specified solid. Creates a new SolidSource object, sets its values from the parameters, and sets `mainSource` to that object.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *number[]* | The color of the solid. |
| arg1 | *string* | The name of the solid. |
| arg2 | *number* | The width of the solid in pixels. |
| arg3 | *number* | The height of the solid in pixels. |
| arg4 | *number* | The pixel aspect ratio of the solid. |

<HorizontalLine />

### setGuide

Returns: *any*

Since: **27.0**

Updates an existing guide. Two forms, distinguished by the type of the second argument: `setGuide(position, guideIndex)` moves the guide at `guideIndex` to a new pixel `position`; `setGuide(guideIndex, guideOptions)` applies the properties set on a GuideOptions object to the guide at `guideIndex` (partial update, After Effects (Beta) 26.5+). The two forms take their arguments in the opposite order.

<HorizontalLine />

### setProxy

Returns: *boolean*

Since: **27.0**

Sets a file as the proxy of this AVItem. Loads the specified file into a new FileSource object, sets this as the value of the `proxySource` attribute, and sets `useProxy` to `true`. It does not preserve the interpretation parameters, instead using the user preferences.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *string* | The file path to use as a proxy. |

<HorizontalLine />

### setProxyToNone

Returns: *boolean*

Since: **27.0**

Removes the proxy from this AVItem, sets the value of `proxySource` to `null`, and sets the value of `useProxy` to `false`.

<HorizontalLine />

### setProxyWithPlaceholder

Returns: *boolean*

Since: **27.0**

Creates a PlaceholderSource object with specified values, sets this as the value of the `proxySource` attribute, and sets `useProxy` to `true`. It does not preserve the interpretation parameters, instead using the user preferences.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *string* | The name of the new object. |
| arg1 | *number* | The pixel dimensions of the placeholder. |
| arg2 | *number* | The pixel dimensions of the placeholder. |
| arg3 | *number* | Frame rate for the proxy. |
| arg4 | *number* | The total length in seconds, up to 3 hours. |

<HorizontalLine />

### setProxyWithSequence

Returns: *boolean*

Since: **27.0**

Sets a sequence of files as the proxy of this AVItem, with the option of forcing alphabetical order. Loads the specified file sequence into a new FileSource object, sets this as the value of the `proxySource` attribute, and sets `useProxy` to `true`.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *string* | The file path of the first file in the sequence. |
| arg1 | *boolean* | When `true`, use the "Force alphabetical order" option. |

<HorizontalLine />

### setProxyWithSolid

Returns: *boolean*

Since: **27.0**

Creates a SolidSource object with specified values, sets this as the value of the `proxySource` attribute, and sets `useProxy` to `true`. It does not preserve the interpretation parameters, instead using the user preferences.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *number[]* | The color of the solid. |
| arg1 | *string* | The name of the new object. |
| arg2 | *number* | The pixel dimensions of the placeholder. |
| arg3 | *number* | The pixel dimensions of the placeholder. |
| arg4 | *number* | The pixel aspect ratio of the solid. |

<HorizontalLine />
