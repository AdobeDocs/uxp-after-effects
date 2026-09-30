---
id: "cameralayer"
title: "CameraLayer"
sidebar_label: CameraLayer
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

# CameraLayer  

## Properties

| Name | Type | Access | Min Version | Description |
| :------ | :------ | :------ | :------ | :------ |
| active | *boolean* | R | 27.0 | For a layer, corresponds to the eyeball icon; `true` when the layer's video is active at the current time (enabled, not overridden by another soloed layer, and within `inPoint`/`outPoint`). Never `true` for an audio layer. For an effect or property, same as `enabled` but read-only. |
| adjustmentLayer | *boolean* | RW | 27.0 | `true` if the layer is an adjustment layer. |
| autoOrient | *number* | RW | 27.0 | The type of automatic orientation applied to the layer, one of `AutoOrientType`. |
| canSetEnabled | *boolean* | R | 27.0 | `true` if the `enabled` attribute value can be set. Generally `true` if the UI shows an eyeball icon for this property; always `true` for layers. |
| comment | *string* | RW | 27.0 | A descriptive comment for the layer. |
| containingComp | *CompItem* | R | 27.0 | The composition that contains this layer. |
| elided | *boolean* | R | 27.0 | `true` if this property is an organizational group not shown in the UI, whose children are not indented in the Timeline panel. |
| enabled | *boolean* | RW | 27.0 | For a layer, the video switch state in the Timeline panel. For an effect or property, the eyeball icon setting, if present. |
| environmentLayer | *boolean* | RW | 27.0 | `true` if this is an environment layer in a ray-traced 3D composition; setting it to `true` also makes the layer 3D. |
| guides | *Array* | R | 27.0 | An array of objects describing the guides in the layer's view (orientation, position, and - in AE 26.5+ - color and pinning). |
| hasVideo | *boolean* | R | 27.0 | `true` if the layer has a video switch (the eyeball icon) in the Timeline panel. |
| id | *number* | R | 27.0 | A unique, persistent identification number for the layer, stable across save/reload but reassigned when imported into another project. |
| inPoint | *number* | RW | 27.0 | The layer's "in" point, in composition time (seconds). |
| index | *number* | R | 27.0 | The layer's index position. |
| isEffect | *boolean* | R | 27.0 | `true` if this property is an effect PropertyGroup. |
| isMask | *boolean* | R | 27.0 | `true` if this property is a mask PropertyGroup. |
| isModified | *boolean* | R | 27.0 | `true` if this property has changed since it was created. |
| isNameSet | *boolean* | R | 27.0 | `true` if `name` has been explicitly set rather than derived from the source; always `true` for layers without a source. |
| label | *number* | RW | 27.0 | The label color for the item, as a number (`0` for none, `1`-`16` for a preset color). |
| lightSource | *Layer* | RW | 27.0 | For a light layer, the layer used as its light source when `lightType` is `LightType.ENVIRONMENT`. |
| lightType | *number* | RW | 27.0 | For a light layer, its light type; setting this on a non-light layer produces an error. |
| locked | *boolean* | RW | 27.0 | `true` if the layer is locked. |
| matchName | *string* | R | 27.0 | A stable, unlocalized identifier for the property used to build unique naming paths. Unlike `name`, it doesn't change across versions. |
| name | *string* | RW | 27.0 | For a layer, its name (same as source name unless `isNameSet` is `false`). For an effect or property, its display name; settable only for children of an indexed group. |
| nullLayer | *boolean* | R | 27.0 | `true` if the layer was created as a null object. |
| numProperties | *number* | R | 27.0 | The number of indexed properties in this group. For layers, this returns 3 (the mask, effect, and motion tracker groups). Other properties are available only by name; see `property()`. |
| outPoint | *number* | RW | 27.0 | The layer's "out" point, in composition time (seconds). |
| parent | *Layer* | RW | 27.0 | The layer's parent, or `null`. Setting this offsets transform values so the child's on-screen transform doesn't jump; use `setParentWithJump` to reparent without that offset. |
| parentProperty | *Layer \| PropertyGroup* | R | 27.0 | The immediate parent property group of this property, or `null` if this is a layer. |
| propertyDepth | *number* | R | 27.0 | The number of parent group levels between this property and its containing layer. `0` for a layer. |
| propertyType | *number* | R | 27.0 | The type of this property: `PropertyType.PROPERTY`, `PropertyType.INDEXED_GROUP`, or `PropertyType.NAMED_GROUP`. |
| selected | *boolean* | RW | 27.0 | `true` if this property is selected in the UI. |
| selectedProperties | *Array* | R | 27.0 | An array of the currently selected `Property` and `PropertyGroup` objects in the layer. |
| shy | *boolean* | RW | 27.0 | `true` if the layer is "shy" (hidden in the Layer panel when the comp's "Hide all shy layers" option is on). |
| solo | *boolean* | RW | 27.0 | `true` if the layer is soloed. |
| startTime | *number* | RW | 27.0 | The layer's start time, in composition time (seconds). |
| stretch | *number* | RW | 27.0 | The layer's time stretch, as a percentage; `100` means no stretch. |
| time | *number* | R | 27.0 | The layer's current time, in composition time (seconds). |


## Instance Methods

### activeAtTime

Returns: *boolean*

Since: **27.0**

Returns `true` if the layer will be active at the given time (enabled, not overridden by soloing, and within `inPoint`/`outPoint`).

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *number* | The time, in seconds. |

<HorizontalLine />

### addGuide

Returns: *any*

Since: **27.0**

Adds a guide to the layer's view and returns its index. Accepts either `(orientationType, position)` for a pixel guide, or a single `GuideOptions` object (AE 26.5+) for percentage positioning, color, and pinning.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| orientation | *number* | `0` for horizontal, `1` for vertical; you can also pass `GuideOrientationType.HORIZONTAL` / `.VERTICAL`. |
| position | *number* | The X or Y position of the guide, in pixels. |

<HorizontalLine />

### addProperty

Returns: *PropertyGroup*

Since: **27.0**

Creates and returns a PropertyBase object with the specified name, and adds it to this group. In general, you can only add properties to an indexed group (a property group that has the type `PropertyType.INDEXED_GROUP`). The only exception is a text animator property, which can be added to a named group (type `PropertyType.NAMED_GROUP`). If this method cannot create a property with the specified name, it generates an exception. To check that you can add a particular property to this group, call `canAddProperty` before calling this method. Warning: when you add a new property to an indexed group, the indexed group gets recreated from scratch, invalidating all existing references to properties. One workaround is to store the index of the added property with `propertyIndex`.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| matchName | *string* | The match name or display name of the property to add. |

<HorizontalLine />

### addToMotionGraphicsTemplate

Returns: *boolean*

Since: **27.0**

Adds this property to the Essential Graphics panel for the specified composition. `true` on success. Use `canAddToMotionGraphicsTemplate` to check eligibility first.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *object* | The composition to add the layer to. |

<HorizontalLine />

### addToMotionGraphicsTemplateAs

Returns: *boolean*

Since: **27.0**

Same as `addToMotionGraphicsTemplate`, but lets you give the EGP property a custom name.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *object* | The composition to add the layer to. |
| arg1 | *string* | The new name. |

<HorizontalLine />

### addVariableFontAxis

Returns: *Property*

Since: **27.0**

Creates and returns a Property object for a variable font axis, and adds it to this property group. This method can only be called on the "ADBE Text Animator Properties" property group within a text animator. Common axis tags include (but are not limited to): "wght" - Weight (100-900 typical range), "wdth" - Width (percentage of normal width), "slnt" - Slant (angle in degrees), "ital" - Italic (0-1 range), "opsz" - Optical Size (point size). Fonts may also include custom axes with 4-character uppercase tags (e.g., "INFM" for Informality).

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| axisTag | *string* | The 4-character variable font axis tag (e.g. "wght", "wdth"). |

<HorizontalLine />

### applyPreset

Returns: *boolean*

Since: **27.0**

Applies an animation preset file to the comp's currently selected layers (or a new solid layer if none is selected).

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *string* | The animation preset file. |

<HorizontalLine />

### canAddProperty

Returns: *boolean*

Since: **27.0**

Returns `true` if a property with the given name can be added to this property group. For example, you can only add mask to a mask group. The only legal input arguments are "mask" or "ADBE Mask Atom".

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| matchName | *string* | The display name or match name of the property to be checked. |

<HorizontalLine />

### canAddToMotionGraphicsTemplate

Returns: *boolean*

Since: **27.0**

Tests whether the layer can be added to the Essential Graphics panel for the given composition (Media Replacement Layers only).

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *object* | The composition to check. |

<HorizontalLine />

### copyToComp

Returns: *boolean*

Since: **27.0**

Copies the layer into the target composition, prepending it to the composition's `LayerCollection`.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| intoComp | *object* | The target composition. |

<HorizontalLine />

### doSceneEditDetection

Returns: *number[]*

Since: **27.0**

Runs Scene Edit Detection on the layer and returns the detected scene-change times; throws for non-video layers or layers with Time Remapping enabled.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *number* | How detected edits are applied, one of `SceneEditDetectionMode.MARKERS`, `.SPLIT`, `.SPLIT_PRECOMP`, `.NONE`. |

<HorizontalLine />

### duplicate

Returns: *CameraLayer*

Since: **27.0**

Duplicates the layer, creating a new one with the same values.

<HorizontalLine />

### getGuideAsObject

Returns: *GuideOptions*

Since: **27.0**

Returns the guide at the given index as a `GuideOptions` object, modifiable and passable back to `setGuide`.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| index | *number* | The index of the guide to read. |

<HorizontalLine />

### getRenderGUID

Returns: *DeferredCall*

Since: **27.0**

Starts an asynchronous render of the layer and returns a `DeferredCall`; `.wait()` on the result yields the render GUID.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| seconds | *number* | The time to render, in seconds. |
| thread | *number* | The thread to render on, a `ProjectThread` value. |
| trace | *boolean* | Whether to enable additional tracing. |

<HorizontalLine />

### moveAfter

Returns: *boolean*

Since: **27.0**

Moves this layer to a position immediately after (below) the given layer.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| otherLayer | *object* | The target layer in the same composition. |

<HorizontalLine />

### moveBefore

Returns: *boolean*

Since: **27.0**

Moves this layer to a position immediately before (above) the given layer.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| otherLayer | *object* | The target layer in the same composition. |

<HorizontalLine />

### moveTo

Returns: *boolean*

Since: **27.0**

Moves this property to a new index in its parent group. Only valid for children of indexed groups; invalidates existing sibling references.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *number* | The new index position. |

<HorizontalLine />

### moveToBeginning

Returns: *boolean*

Since: **27.0**

Moves this layer to the top of the layer stack.

<HorizontalLine />

### moveToEnd

Returns: *boolean*

Since: **27.0**

Moves this layer to the bottom of the layer stack.

<HorizontalLine />

### property

Returns: *any*

Since: **27.0**

Finds and returns a child property of this group, as specified by either its index or name. A name specification can use the same syntax that is available with expressions. mylayer.position, mylayer("position"), mylayer.property("position"), mylayer(1), and mylayer.property(1) are all equivalent. Some properties of a layer, such as position and zoom, can be accessed only by name. When using the name to find a property that is multiple levels down, you must make more than one call to this method - for example, myLayer.property("ADBE Masks").property(1) searches two levels down.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| indexOrName | *number* or *string* | The index or name of the child property to find. |

<HorizontalLine />

### propertyGroup

Returns: *PropertyGroup*

Since: **27.0**

Gets the ancestor PropertyGroup at a specified level up the parent-child hierarchy (default: immediate parent). Returns the Layer if the count reaches the containing layer.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *number* | The number of levels to ascend (default `1`). |

<HorizontalLine />

### remove

Returns: *boolean*

Since: **27.0**

Deletes the layer from the composition.

<HorizontalLine />

### removeGuide

Returns: *boolean*

Since: **27.0**

Removes the guide at the given index.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| index | *number* | The index of the guide to remove. |

<HorizontalLine />

### savePreset

Returns: *boolean*

Since: **27.0**

Saves the layer's currently selected properties as an animation preset (`.ffx`) file. Returns `false` if nothing was selected to save.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *string* | The file path to save the preset to. |

<HorizontalLine />

### setGuide

Returns: *any*

Since: **27.0**

Updates an existing guide: `(position, guideIndex)` moves it to a new pixel position, or `(guideIndex, guideOptions)` applies a partial update (AE 26.5+).

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| position | *number* | The new X or Y position, in pixels. |
| index | *number* | The index of the guide to update. |

<HorizontalLine />

### setParentWithJump

Returns: *boolean*

Since: **27.0**

Sets the layer's parent without changing its transform values (may cause an apparent jump). Required in this binding - throws if `newParent` is omitted, unlike ExtendScript's optional signature.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| newParent | *object* | The new parent layer; required - throws if omitted. |

<HorizontalLine />
