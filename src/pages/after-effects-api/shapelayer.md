---
id: "shapelayer"
title: "ShapeLayer"
sidebar_label: "ShapeLayer"
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

# ShapeLayer  

## Properties

| Name | Type | Access | Min Version | Description |
| :------ | :------ | :------ | :------ | :------ |
| active | *boolean* | R | 27.0 | For a layer, this corresponds to the setting of the eyeball icon. When `true`, the layer's video is active at the current time. |
| adjustmentLayer | *boolean* | RW | 27.0 | `true` if the layer is an adjustment layer. |
| audioActive | *boolean* | R | 27.0 | `true` if the layer's audio is active at the current time. |
| audioEnabled | *boolean* | RW | 27.0 | When `true`, the layer's audio is enabled. |
| autoOrient | *number* | RW | 27.0 | The type of automatic orientation to perform for the layer. |
| blendingMode | *number* | RW | 27.0 | The blending mode of the layer. |
| canSetCollapseTransformation | *boolean* | R | 27.0 | `true` if it is legal to change the value of the collapseTransformation attribute. |
| canSetEnabled | *boolean* | R | 27.0 | When `true`, you can set the `enabled` attribute value. |
| canSetTimeRemapEnabled | *boolean* | R | 27.0 | `true` if it is legal to change the value of the timeRemapEnabled attribute. |
| collapseTransformation | *boolean* | RW | 27.0 | `true` if collapse transformation is on for this layer. |
| comment | *string* | RW | 27.0 | A descriptive comment for the layer. |
| containingComp | *CompItem* | R | 27.0 | The composition that contains this layer. |
| effectsActive | *boolean* | RW | 27.0 | `true` if the layer's effects are active. |
| elided | *boolean* | R | 27.0 | When `true`, this property is a group used to organize other properties. The property is not displayed in the user interface. |
| enabled | *boolean* | RW | 27.0 | For layer, this corresponds to the video switch state of the layer in the Timeline panel. |
| environmentLayer | *boolean* | RW | 27.0 | `true` if this is an environment layer in a Ray-traced 3D composition. |
| frameBlending | *boolean* | R | 27.0 | `true` if frame blending is enabled for the layer. |
| frameBlendingType | *number* | RW | 27.0 | The type of frame blending to perform when frame blending is enabled. |
| guideLayer | *boolean* | RW | 27.0 | `true` if the layer is a guide layer. |
| guides | *Array* | R | 27.0 | An array of objects describing the guides in the layer's view. The properties on each entry depend on the version of After Effects. |
| hasAudio | *boolean* | R | 27.0 | `true` if the layer contains an audio component. |
| hasTrackMatte | *boolean* | R | 27.0 | `true` if this layer has track matte. |
| hasVideo | *boolean* | R | 27.0 | When `true`, the layer has a video switch (the eyeball icon) in the Timeline panel; otherwise `false`. |
| height | *number* | R | 27.0 | The height of the layer in pixels. |
| id | *number* | R | 27.0 | Instance property on Layer which returns a unique and persistent identification number used internally to identify a Layer between sessions. |
| inPoint | *number* | RW | 27.0 | The 'in' point of the layer, expressed in composition time (seconds). |
| index | *number* | R | 27.0 | The index position of the layer. |
| isEffect | *boolean* | R | 27.0 | When `true`, this property is an effect PropertyGroup. |
| isMask | *boolean* | R | 27.0 | When `true`, this property is a mask PropertyGroup. |
| isModified | *boolean* | R | 27.0 | When `true`, this property has been changed since its creation. |
| isNameFromSource | *boolean* | R | 27.0 | `true` if the layer has no expressly set name, but contains a named source. |
| isNameSet | *boolean* | R | 27.0 | When the value of the name attribute has been set explicitly, returns `true`, rather than automatically from the source. |
| isTrackMatte | *boolean* | R | 27.0 | `true` if this layer is being used as a track matte. |
| label | *number* | RW | 27.0 | The label color for the item. Colors are represented by their number (0 for None, or 1 to 16 for one of the preset colors in the Labels preferences). |
| lightSource | *Layer* | RW | 27.0 | For a light layer, the layer to use as a light source when LightLayer.lightType is LightType.ENVIRONMENT. LightLayer.lightSource can be any 2D video, still, or pre-composition layer in the same composition. |
| lightType | *number* | RW | 27.0 | For a light layer, its light type. Trying to set this attribute for a non-light layer produces an error. |
| locked | *boolean* | RW | 27.0 | When `true`, the layer is locked; otherwise `false`. |
| matchName | *string* | R | 27.0 | A special name for the property used to build unique naming paths. The match name is not displayed, but you can refer to it in scripts. Every property has a unique match-name identifier. Match names are stable from version to version regardless of the display name (the name attribute value) or any changes to the application. Unlike the display name, it is not localized. An indexed group may not have a name value, but always has a matchName value. |
| motionBlur | *boolean* | RW | 27.0 | `true` if motion blur is enabled for the layer. |
| name | *string* | RW | 27.0 | For a layer, the name of the layer. By default, this is the same as the Source name, unless Layer.isNameSet returns false. |
| nullLayer | *boolean* | R | 27.0 | When `true`, the layer was created as a null object; otherwise `false`. |
| numProperties | *number* | R | 27.0 | The number of indexed properties in this group. |
| outPoint | *number* | RW | 27.0 | The 'out' point of the layer, expressed in composition time (seconds). |
| parent | *Layer* | RW | 27.0 | The parent of this layer; can be `null`. |
| parentProperty | *Layer \| PropertyGroup* | R | 27.0 | The property group that is the immediate parent of this property, or `null` if this PropertyBase is a layer. |
| preserveTransparency | *boolean* | RW | 27.0 | `true` if preserve transparency is enabled for the layer. |
| propertyDepth | *number* | R | 27.0 | The number of levels of parent groups between this property and the containing layer. |
| propertyType | *number* | R | 27.0 | The type of this property: PropertyType.PROPERTY (a single property such as position or zoom), PropertyType.INDEXED_GROUP (a property group whose members have an editable name and an index, such as effects and masks), or PropertyType.NAMED_GROUP (a property group in which the member names are not editable, such as layers). |
| quality | *number* | RW | 27.0 | The quality with which this layer is displayed. |
| samplingQuality | *number* | RW | 27.0 | Set/get layer sampling method (bicubic or bilinear). |
| selected | *boolean* | RW | 27.0 | When `true`, this property is selected. Set to `true` to select the property, or to `false` to deselect it. |
| selectedProperties | *Array* | R | 27.0 | An array containing all of the currently selected Property and PropertyGroup objects. |
| shy | *boolean* | RW | 27.0 | When `true`, the layer is 'shy', meaning that it is hidden in the Layer panel if the composition's 'Hide all shy layers' option is toggled on. |
| solo | *boolean* | RW | 27.0 | When `true`, the layer is soloed, otherwise `false`. |
| source | *CompItem \| FootageItem* | R | 27.0 | The source AVItem for this layer. |
| startTime | *number* | RW | 27.0 | The start time of the layer, expressed in composition time (seconds). |
| stretch | *number* | RW | 27.0 | The layer's time stretch, expressed as a percentage. |
| threeDLayer | *boolean* | RW | 27.0 | `true` if this is a 3D layer. |
| threeDPerChar | *boolean* | RW | 27.0 | `true` if this layer has the Enable Per-character 3D switch set. |
| time | *number* | R | 27.0 | The current time of the layer, expressed in composition time (seconds). |
| timeRemapEnabled | *boolean* | RW | 27.0 | `true` if time remapping is enabled for this layer. |
| trackMatteLayer | *AVLayer* | R | 27.0 | Returns the track matte layer for this layer. |
| trackMatteType | *number* | RW | 27.0 | If this layer has a track matte, specifies the way the track matte is applied. |
| width | *number* | R | 27.0 | The width of the layer in pixels. |


## Instance Methods

### activeAtTime

Returns: *boolean*

Since: **27.0**

Returns `true` if this layer will be active at the specified time.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *number* | The time to check, in composition time (seconds). |

<HorizontalLine />

### addGuide

Returns: *number \| undefined*

Since: **27.0**

Adds a guide to the layer's view and returns its index. There are two forms: addGuide(orientationType, position) - adds a pixel guide using an orientation and a pixel position. addGuide(guideOptions) - adds a guide described by a GuideOptions object, allowing percentage positioning, per-guide color, and pinning (After Effects 26.5 and later; calling this form in an earlier version raises an error).

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| orientation | *number* | 0 for a horizontal guide, 1 for a vertical guide. Any other value defaults to horizontal. In After Effects 26.5 and later you may also pass GuideOrientationType.HORIZONTAL / GuideOrientationType.VERTICAL. |
| position | *number* | The X or Y coordinate position of the guide in pixels. Clamped to ±100,000; non-finite values are rejected. |

<HorizontalLine />

### addProperty

Returns: *PropertyGroup*

Since: **27.0**

Creates and returns a PropertyBase object with the specified name, and adds it to this group.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| matchName | *string* | The display name or matchName of the property to add. |

<HorizontalLine />

### addToMotionGraphicsTemplate

Returns: *boolean*

Since: **27.0**

Adds the layer to the Essential Graphics Panel for the specified composition.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *object* | The composition to add the layer to. |

<HorizontalLine />

### addToMotionGraphicsTemplateAs

Returns: *boolean*

Since: **27.0**

Adds the layer to the Essential Graphics Panel for the specified composition, using a custom name.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *object* | The composition to add the layer to. |
| arg1 | *string* | The custom name to use for the layer in the Essential Graphics Panel. |

<HorizontalLine />

### addVariableFontAxis

Returns: *Property*

Since: **27.0**

Creates and returns a Property object for a variable font axis, and adds it to this property group.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| axisTag | *string* | The 4-character tag identifying the variable font axis (e.g., `wght`, `wdth`, `slnt`, `ital`). |

<HorizontalLine />

### applyPreset

Returns: *boolean*

Since: **27.0**

Applies the specified collection of animation settings to all currently selected layers.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *string* | The path to the animation preset (.ffx) file to apply. |

<HorizontalLine />

### audioActiveAtTime

Returns: *boolean*

Since: **27.0**

Returns `true` if this layer's audio will be active at the specified time.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *number* | The time to check, in composition time (seconds). |

<HorizontalLine />

### calculateTransformFromPoints

Returns: *\{ anchorPoint: number[]; position: number[]; xRotation: number; yRotation: number; zRotation: number; scale: number[] }*

Since: **27.0**

Calculates a transformation from a set of points in this layer. Given the layer-space coordinates of three corners of a rectangle - as if pinning the layer's untransformed bounds onto those points, the way you would match a flat layer to three points picked in a photographed scene - returns the anchorPoint, position, rotation, and scale that would produce that mapping.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| pointTopLeft | *number[]* | The `[x, y, z]` layer-space coordinates to map to the top-left corner. |
| pointTopRight | *number[]* | The `[x, y, z]` layer-space coordinates to map to the top-right corner. |
| pointBottomLeft | *number[]* | The `[x, y, z]` layer-space coordinates to map to the bottom-left corner. |

<HorizontalLine />

### canAddProperty

Returns: *boolean*

Since: **27.0**

Returns `true` if a property with the given name can be added to this property group.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| matchName | *string* | The display name or match name of the property to be checked. |

<HorizontalLine />

### canAddToMotionGraphicsTemplate

Returns: *boolean*

Since: **27.0**

Test whether or not the layer can be added to the Essential Graphics Panel.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *object* | The composition to test against. |

<HorizontalLine />

### compPointToSource

Returns: *number[]*

Since: **27.0**

Converts composition coordinates to layer coordinates.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| compXyz | *number[]* | The `[x, y, z]` point in composition coordinates to convert. |

<HorizontalLine />

### copyToComp

Returns: *boolean*

Since: **27.0**

Copies the layer into the specified composition.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| intoComp | *object* | The composition to copy the layer into. |

<HorizontalLine />

### doSceneEditDetection

Returns: *number[]*

Since: **27.0**

Runs Scene Edit Detection on the layer and returns an array containing times of detected scenes.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *number* | The scene edit detection mode to use. |

<HorizontalLine />

### duplicate

Returns: *ShapeLayer*

Since: **27.0**

Duplicates the layer. Creates a new Layer object with the same values.

<HorizontalLine />

### getGuideAsObject

Returns: *GuideOptions*

Since: **27.0**

Returns the guide at the specified index as a GuideOptions object.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| index | *number* | The index of the guide in the layer's `guides` array. |

<HorizontalLine />

### getRenderGUID

Returns: *DeferredCall*

Since: **27.0**

Returns a DeferredCall that, once resolved, provides a unique identifier string representing the rendered state of the layer at the given time.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| seconds | *number* | The time, in seconds, at which to evaluate the layer's render state. |
| thread | *number* | The project thread to evaluate the render on. |
| trace | *boolean* | When `true`, enables tracing/diagnostic output for the render GUID computation. |

<HorizontalLine />

### moveAfter

Returns: *boolean*

Since: **27.0**

Moves this layer to a position immediately after (below) the specified layer.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| otherLayer | *object* | The layer after which to move this layer. |

<HorizontalLine />

### moveBefore

Returns: *boolean*

Since: **27.0**

Moves this layer to a position immediately before (above) the specified layer.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| otherLayer | *object* | The layer before which to move this layer. |

<HorizontalLine />

### moveTo

Returns: *boolean*

Since: **27.0**

Moves this property to a new position in its parent property group. Works as documented for children of indexed groups (effects, masks, motion trackers).

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *number* | The new position index. |

<HorizontalLine />

### moveToBeginning

Returns: *boolean*

Since: **27.0**

Moves this layer to the topmost position of the layer stack.

<HorizontalLine />

### moveToEnd

Returns: *boolean*

Since: **27.0**

Moves this layer to the bottom position of the layer stack.

<HorizontalLine />

### openInViewer

Returns: *Viewer*

Since: **27.0**

Opens the layer in a Layer panel, and moves the Layer panel to front.

<HorizontalLine />

### property

Returns: *Property \| PropertyGroup*

Since: **27.0**

Finds and returns a child property of this group, as specified by either its index or name. A name specification can use the same syntax that is available with expressions. mylayer.position, mylayer("position"), mylayer.property("position"), mylayer(1), and mylayer.property(1) are all equivalent. Some properties of a layer, such as position and zoom, can be accessed only by name. When using the name to find a property that is multiple levels down, you must make more than one call to this method - for example, myLayer.property("ADBE Masks").property(1) searches two levels down.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| indexOrName | *number* or *string* | The index (in the range 1..numProperties) or name of the child property to find - supports match name, expression-style name, or display name. |

<HorizontalLine />

### propertyGroup

Returns: *PropertyGroup*

Since: **27.0**

Gets the PropertyGroup object for an ancestor group of this property at a specified level of the parent-child hierarchy.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *number* | How many levels up the parent-child hierarchy to walk to find the ancestor group. |

<HorizontalLine />

### remove

Returns: *boolean*

Since: **27.0**

Deletes the specified layer from the composition.

<HorizontalLine />

### removeGuide

Returns: *boolean*

Since: **27.0**

Removes an existing guide by its index in the guides array.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| index | *number* | The index of the guide to remove, in the layer's `guides` array. |

<HorizontalLine />

### removeTrackMatte

Returns: *boolean*

Since: **27.0**

Removes the track matte for this layer while preserving the TrackMatteType.

<HorizontalLine />

### replaceSource

Returns: *boolean*

Since: **27.0**

Replaces the source for this layer.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *object* | The new source item for the layer. |
| arg1 | *boolean* | When `true`, updates expressions that reference the old source to reference the new one. |

<HorizontalLine />

### savePreset

Returns: *boolean*

Since: **27.0**

Saves the currently selected keyframes/properties of the layer as an animation preset (.ffx) file at the specified path. Returns false if nothing is selected to save.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *string* | The file path at which to save the animation preset (.ffx) file. |

<HorizontalLine />

### setGuide

Returns: *void*

Since: **27.0**

Updates an existing guide. Two forms, distinguished by the type of the second argument: setGuide(position, guideIndex) moves the guide at guideIndex to a new pixel position (position first, index second); a guide's orientationType may not be changed after creation. setGuide(guideIndex, guideOptions) applies the properties set on a GuideOptions object to the guide at guideIndex as a partial update (After Effects 26.5 and later).

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| position | *number* | The new X or Y coordinate position of the guide in pixels. Clamped to ±100,000; non-finite values are rejected. |
| index | *number* | The index of the guide to be modified. |

<HorizontalLine />

### setParentWithJump

Returns: *boolean*

Since: **27.0**

Sets the parent without changing the transform values of the child layer.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| newParent | *object* | The new parent layer, or `null` to remove the parent. |

<HorizontalLine />

### setTrackMatte

Returns: *boolean*

Since: **27.0**

Sets the track matte layer and type for this layer.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| newTrackMatteLayer | *object* | The layer to use as the track matte. |
| arg1 | *number* | The way the track matte is applied. |

<HorizontalLine />

### sourcePointToComp

Returns: *number[]*

Since: **27.0**

Converts layer coordinates to composition coordinates.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| srcXyz | *number[]* | The `[x, y, z]` point in layer coordinates to convert. |

<HorizontalLine />

### sourceRectAtTime

Returns: *\{ height: number; left: number; top: number; width: number }*

Since: **27.0**

Retrieves the rectangle bounds of the layer at the specified time index.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *number* | The time, in composition time (seconds), at which to retrieve the bounds. |
| arg1 | *boolean* | When `true`, includes extra render-time extents (e.g. blur/shadow bleed) in the returned rectangle. |

<HorizontalLine />
