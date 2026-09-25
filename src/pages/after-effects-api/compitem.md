---
id: "compitem"
title: "CompItem"
description: "Represents a composition item within a project, used to access and modify composition settings and layers."
sidebar_label: "CompItem"
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

# CompItem  

## Properties

| Name | Type | Access | Min Version | Description |
| :------ | :------ | :------ | :------ | :------ |
| activeCamera | *CameraLayer \| null* | R | 27.0 | The active camera, which is the front-most camera layer that is enabled. The value is `null` if the composition contains no enabled camera layers. |
| bgColor | *number[]* | RW | 27.0 | The background color of the composition. The three array values specify the red, green, and blue components of the color. |
| comment | *string* | RW | 27.0 | A string that holds a comment, up to 15,999 bytes in length after any encoding conversion. The comment is for the user's purpose only; it has no effect on the item's appearance or behavior. |
| counters | *boolean* | RW | 27.0 | This attribute works app-wide: if changed on one CompItem, it will change it for every CompItem in the project. The value stays until restarting AE. Once restarted, it will revert to `false`. This parameter doesn't do anything. |
| displayStartFrame | *number* | RW | 27.0 | The frame value of the beginning of the composition. This value is an alternative to calculating the start frame using `displayStartTime` and `frameDuration` to compensate for floating-point problems. |
| displayStartTime | *number* | RW | 27.0 | The time set as the beginning of the composition, in seconds. This is the equivalent of the Start Timecode or Start Frame setting in the Composition Settings dialog box. |
| draft3d | *boolean* | RW | 27.0 | When `true`, Draft 3D mode is enabled for the Composition panel. This corresponds to the value of the Draft 3D button in the Composition panel. |
| dropFrame | *boolean* | RW | 27.0 | When `true`, indicates that the composition uses drop-frame timecode. When `false`, indicates non-drop-frame timecode. This corresponds to the setting in the Composition Settings dialog box. |
| duration | *number* | RW | 27.0 | Returns the duration, in seconds, of the item. Still footage items have a duration of 0. In a CompItem, the value is linked to the duration of the composition, and is read/write. In a FootageItem, the value is linked to the `duration` of the `mainSource` object, and is read-only. |
| dynamicLinkGUID | *string* | R | 27.0 | A unique and persistent identification number used for the dynamic link, in form of `00000000-0000-0000-0000-000000000000`. |
| footageMissing | *boolean* | R | 27.0 | When `true`, the AVItem is a placeholder, or represents footage with a source file that cannot be found. In this case, the path of the missing source file is in the `missingFootagePath` attribute of the footage item's source-file object. |
| frameBlending | *boolean* | RW | 27.0 | When `true`, frame blending is enabled for this Composition. Corresponds to the value of the Frame Blending button in the Composition panel. |
| frameDuration | *number* | RW | 27.0 | The duration of a frame, in seconds. This is the inverse of the `frameRate` value (frames-per-second). |
| frameRate | *number* | RW | 27.0 | The frame rate of the AVItem, in frames-per-second. This is the reciprocal of the `frameDuration`. When set, the reciprocal is automatically set as a new `frameDuration` value. In a CompItem, the value is linked to the `frameRate` of the composition, and is read/write. |
| frameTime | *number* | RW | 27.0 | The current time of the item, expressed in frames - an alternative to the `time` attribute, which uses seconds. |
| guides | *Array* | R | 27.0 | An array of objects describing the guides in the item's view. The properties on each entry depend on the version of After Effects. In After Effects 16.1 (CC 2019) and later, each entry has `orientationType`, `positionType`, `position`. In After Effects (Beta) 26.5 and later, each entry also has `color` and `pinned`, and `orientationType`/`positionType` become `GuideOrientationType`/`GuidePositionType` enum values instead of raw integers. |
| hasAudio | *boolean* | R | 27.0 | When `true`, the AVItem has an audio component. In a CompItem, the value is linked to the composition. |
| hasVideo | *boolean* | R | 27.0 | When `true`, the AVItem has a video component. In a CompItem, the value is linked to the composition. |
| height | *number* | RW | 27.0 | The height of the item in pixels. In a CompItem, the value is linked to the composition, and is read/write. |
| hideShyLayers | *boolean* | RW | 27.0 | When `true`, only layers with shy set to `false` are shown in the Timeline panel. When `false`, all layers are visible, including those whose shy value is `true`. Corresponds to the value of the Hide All Shy Layers button in the Composition panel. |
| id | *number* | R | 27.0 | A unique and persistent identification number used internally to identify an item between sessions. The value of the ID remains the same when the project is saved to a file and later reloaded. However, when you import this project into another project, new IDs are assigned to all items in the imported project. The ID is not displayed anywhere in the user interface. |
| isMediaReplacementCompatible | *boolean* | R | 27.0 | Test whether the AVItem can be used as an alternate source when calling `Property.setAlternateSource()`. Returns `true` if the item can be used, or otherwise `false`. A CompItem or a FootageItem can be used as an alternate source for the layer, with some restrictions: if the AVItem is a FootageItem, its FootageSource should not be a SolidSource; if it's a FootageItem whose FootageSource is a FileSource, that FileSource should not point to a non-media file (e.g. a JSX script file); setting the AVItem cannot create a cyclical reference within the project. |
| label | *number* | RW | 27.0 | The label color for the item. Colors are represented by their number (0 for None, or 1 to 16 for one of the preset colors in the Labels preferences). |
| layers | *LayerCollection* | R | 27.0 | A LayerCollection object that contains all the Layer objects for layers in this composition. |
| motionBlur | *boolean* | RW | 27.0 | When `true`, motion blur is enabled for the composition. Corresponds to the value of the Motion Blur button in the Composition panel. |
| motionBlurAdaptiveSampleLimit | *number* | RW | 27.0 | The maximum number of motion blur samples of 2D layer motion. This corresponds to the Adaptive Sample Limit setting in the Advanced tab of the Composition Settings dialog box. |
| motionBlurSamplesPerFrame | *number* | RW | 27.0 | The minimum number of motion blur samples per frame for Classic 3D layers, shape layers, and certain effects. This corresponds to the Samples Per Frame setting in the Advanced tab of the Composition Settings dialog box. |
| motionGraphicsTemplateControllerCount | *number* | R | 27.0 | The number of properties in the Essential Graphics panel for the composition. |
| motionGraphicsTemplateName | *string* | RW | 27.0 | Read or write the name property in the Essential Graphics panel for the composition. The name in the Essential Graphics panel is used for the file name of an exported Motion Graphics template (ex., "My Template.mogrt"). |
| name | *string* | RW | 27.0 | The name of the item, as shown in the Project panel. In a FootageItem, the value is linked to the `mainSource` object. If the `mainSource` object is a `FileSource`, this value controls the display name in the Project panel, but does not affect the file name. |
| parentFolder | *FolderItem* | RW | 27.0 | The FolderItem object for the folder that contains this item. If this item is at the top level of the project, this is the project's root folder (`app.project.rootFolder`). |
| pixelAspect | *number* | RW | 27.0 | The pixel aspect ratio (PAR) of the item. In a CompItem, the value is linked to the composition. |
| preserveNestedFrameRate | *boolean* | RW | 27.0 | When `true`, the frame rate of nested compositions is preserved in the current composition. Corresponds to the value of the "Preserve frame rate when nested or in render queue" option in the Advanced tab of the Composition Settings dialog box. |
| preserveNestedResolution | *boolean* | RW | 27.0 | When `true`, the resolution of nested compositions is preserved in the current composition. Corresponds to the value of the "Preserve Resolution When Nested" option in the Advanced tab of the Composition Settings dialog box. |
| proxySource | *FootageSource \| null* | R | 27.0 | The FootageSource being used as a proxy. The attribute is read-only; to change it, call any of the AVItem methods that change the proxy source: `setProxy()`, `setProxyWithSequence()`, `setProxyWithSolid()`, or `setProxyWithPlaceholder()`. |
| renderer | *string* | RW | 27.0 | The current rendering plug-in module to be used to render this composition, as set in the Advanced tab of the Composition Settings dialog box. Allowed values are the members of `CompItem.renderers`. |
| renderers | *string[]* | R | 27.0 | The available rendering plug-in modules. Member strings reflect installed modules, as seen in the Advanced tab of the Composition Settings dialog box. |
| resolutionFactor | *number[]* | RW | 27.0 | The x and y downsample resolution factors for rendering the composition. The two values in the array specify how many pixels to skip when sampling; the first number controls horizontal sampling, the second controls vertical sampling. Full resolution is `[1, 1]`, half resolution is `[2, 2]`, and quarter resolution is `[4, 4]`. The default is `[1, 1]`. |
| selected | *boolean* | RW | 27.0 | When `true`, this item is selected. Multiple items can be selected at the same time. Set to `true` to select the item programmatically, or to `false` to deselect it. |
| selectedLayers | *Array* | R | 27.0 | All of the selected layers in this composition. This is a 0-based array (the first object is at index 0). |
| selectedProperties | *Array* | R | 27.0 | All of the selected properties (Property and PropertyGroup objects) in this composition. The first property is at index position 0. |
| shutterAngle | *number* | RW | 27.0 | The shutter angle setting for the composition. This corresponds to the Shutter Angle setting in the Advanced tab of the Composition Settings dialog box. |
| shutterPhase | *number* | RW | 27.0 | The shutter phase setting for the composition. This corresponds to the Shutter Phase setting in the Advanced tab of the Composition Settings dialog box. |
| time | *number* | RW | 27.0 | The current time of the item when it is being previewed directly from the Project panel. This value is a number of seconds. |
| typeName | *string* | R | 27.0 | A user-readable name for the item type; for example, "Folder", "Footage", or "Composition". These names are application locale-dependent, meaning that they are different depending on the application's interface language. |
| useProxy | *boolean* | RW | 27.0 | When `true`, a proxy is used for the item. It is set to `true` by all the `SetProxy` methods, and to `false` by the `SetProxyToNone()` method. |
| usedIn | *Array* | R | 27.0 | All the compositions that use this AVItem. Note that upon retrieval, the array value is copied, so it is not automatically updated. |
| width | *number* | RW | 27.0 | The width of the item, in pixels. In a CompItem, the value is linked to the composition, and is read/write. |
| workAreaDuration | *number* | RW | 27.0 | The duration of the work area in seconds. This is the difference of the start-point and end-point times of the Composition work area. |
| workAreaStart | *number* | RW | 27.0 | The time when the Composition work area begins, in seconds. |
| markerProperty | *Property* | R | 27.0 | A PropertyGroup object that contains all a composition's markers. Composition marker scripting has the same functionality as Layer markers. |
| numLayers | *number* | R | 27.0 | The number of layers in the composition. |


## Instance Methods

### addGuide

Returns: *any*

Since: **27.0**

Adds a guide to the item's view and returns its index. Two forms: `addGuide(orientationType, position)` adds a pixel guide using an orientation and pixel position; `addGuide(guideOptions)` adds a guide described by a GuideOptions object (After Effects (Beta) 26.5+).

<HorizontalLine />

### applyPreset

Returns: *boolean*

Since: **27.0**

Applies the specified animation preset to all the currently selected layers in this composition. If no layer is selected, it applies the animation preset to a new solid layer.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *string* | The file path of the animation preset to apply. |

<HorizontalLine />

### duplicate

Returns: *CompItem*

Since: **27.0**

Creates and returns a duplicate of this composition, which contains the same layers as the original.

<HorizontalLine />

### exportAsMotionGraphicsTemplate

Returns: *boolean*

Since: **27.0**

Exports the composition as a Motion Graphics template. Returns `true` if the Motion Graphics template is successfully exported, otherwise `false`. The name in the Essential Graphics panel is used for the file name of the Motion Graphics template. Use the `motionGraphicsTemplateName` attribute to set the name. Optionally specify the path to the folder where the Motion Graphics template file is saved; if not specified, it saves to the current user's Motion Graphics Templates folder. If the project has been changed since the last save, After Effects will prompt the user to save it - use the project `save()` method first to avoid this.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| overwrite_existing_file | *boolean* | Whether to overwrite an existing file of the same name. |
| destination_path | *string* | Optional. Path to the folder where the file will be saved. |

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

### getMotionGraphicsTemplateControllerName

Returns: *string*

Since: **27.0**

Gets the name of a single property in the Essential Graphics panel.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *number* | The index of the EGP property whose name will be returned. |

<HorizontalLine />

### getRenderGUID

Returns: *DeferredCall*

Since: **27.0**

Asynchronously computes a GUID that uniquely identifies the rendered state of this composition at the specified time, useful for detecting whether a frame's render output has changed. Returns a `DeferredCall` that resolves to a 36-character GUID string.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| seconds | *number* | The time, in seconds, at which to compute the GUID. |
| thread | *number* | A `ProjectThread` enum value specifying which thread to perform the computation on. |
| trace | *boolean* | Whether to enable verbose tracing for this call. |

<HorizontalLine />

### layer

Returns: *Layer*

Since: **27.0**

Returns a Layer object, which can be specified by name, an index position in this layer, or an index position relative to another layer.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| indexOrOtherLayer | *number* or *string* or [*Layer*](./layer.md) | The index number of the desired layer in this composition, in the range `[1..numLayers]` - or a Layer object in this composition (used with `relIndex`) - or the name of the desired layer as a string. |
| relIndex | *number* | The position of the desired layer, relative to `otherLayer`. This value is added to the `otherLayer` value to derive the absolute index of the layer to return. |

<HorizontalLine />

### openInEssentialGraphics

Returns: *boolean*

Since: **27.0**

Opens the composition in the Essential Graphics panel.

<HorizontalLine />

### openInViewer

Returns: *Viewer*

Since: **27.0**

Opens the composition in a Composition panel, and moves the Composition panel to front and gives it focus.

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

### saveDraftFrameToPng

Returns: *DeferredCall*

Since: **27.0**

Renders the frame at the specified time using a draft-quality render and saves it as a PNG file. Returns a `DeferredCall` that resolves once the file has been written.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| seconds | *number* | The time, in seconds, of the frame to render. |
| arg1 | *string* | The file path to save the PNG to. |

<HorizontalLine />

### saveFrameToPng

Returns: *DeferredCall*

Since: **27.0**

Renders the frame at the specified time and saves it as a PNG file. Returns a `DeferredCall` that resolves once the file has been written.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| seconds | *number* | The time, in seconds, of the frame to render. |
| arg1 | *string* | The file path to save the PNG to. |
| max_abort_interval | *number* | Optional. The maximum time, in seconds, to wait before aborting the render. |

<HorizontalLine />

### setGuide

Returns: *any*

Since: **27.0**

Updates an existing guide. Two forms, distinguished by the type of the second argument: `setGuide(position, guideIndex)` moves the guide at `guideIndex` to a new pixel `position`; `setGuide(guideIndex, guideOptions)` applies the properties set on a GuideOptions object to the guide at `guideIndex` (partial update, After Effects (Beta) 26.5+). The two forms take their arguments in the opposite order.

<HorizontalLine />

### setMotionGraphicsControllerName

Returns: *boolean*

Since: **27.0**

Sets the name of a single property in the Essential Graphics panel.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *number* | The index of the EGP property to be renamed. |
| arg1 | *string* | The new name for the EGP property. |

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
