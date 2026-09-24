---
id: "layer"
title: "Layer"
description: "Provides access to layers within compositions."
sidebar_label: "Layer"
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

# Layer  

## Properties

| Name | Type | Access | Min Version | Description |
| :------ | :------ | :------ | :------ | :------ |
| active | *boolean* | R | 27.0 | For a layer, this corresponds to the setting of the eyeball icon. When true, the layer's video is active at the current time. For this to be true, the layer must be enabled, no other layer may be soloing unless this layer is soloed too, and the time must be between the inPoint and outPoint values of this layer. This value is never true in an audio layer; there is a separate audioActive attribute in the AVLayer object AVLayer.audioActive. For an effect and all properties, it is the same as the enabled attribute, except that it's read-only. |
| adjustmentLayer | *boolean* | RW | 27.0 | true if the layer is an adjustment layer. |
| autoOrient | *number* | RW | 27.0 | The type of automatic orientation to perform for the layer. |
| canSetEnabled | *boolean* | R | 27.0 | When true, you can set the enabled attribute value. Generally, this is true if the user interface displays an eyeball icon for this property; it is true for all layers. |
| comment | *string* | RW | 27.0 | A descriptive comment for the layer. |
| containingComp | *CompItem* | R | 27.0 | The composition that contains this layer. |
| elided | *boolean* | R | 27.0 | When true, this property is a group used to organize other properties. The property is not displayed in the user interface and its child properties are not indented in the Timeline panel. For example, for a text layer with two animators and no properties twirled down, you might see: Text, PathOptions, MoreOptions, Animator1, Animator2. In this example, "Animator 1" and "Animator 2" are contained in a PropertyBase called "Text Animators." This parent group is not displayed in the user interface, and so the two child properties are not indented in the Timeline panel. |
| enabled | *boolean* | RW | 27.0 | For layer, this corresponds to the video switch state of the layer in the Timeline panel. For an effect and all properties, it corresponds to the setting of the eyeball icon, if there is one. When true, the layer or property is enabled; otherwise false. |
| environmentLayer | *boolean* | RW | 27.0 | true if this is an environment layer in a Ray-traced 3D composition. Setting this attribute to true automatically makes the layer 3D (threeDLayer becomes true). |
| guides | *Array* | R | 27.0 | An array of objects describing the guides in the layer's view. The properties on each entry depend on the version of After Effects. In After Effects 16.1 (CC 2019) and later, each entry has: orientationType (Integer, 0 for horizontal or 1 for vertical), positionType (Integer, always 0/pixel), and position (Floating-point, in pixels). In After Effects 26.5 and later, each entry has: orientationType (GuideOrientationType.HORIZONTAL / VERTICAL), positionType (GuidePositionType.PIXEL / PERCENTAGE), position (Floating-point, in pixels or percent depending on positionType), color (Array of 3 floats, [R, G, B] each 0.0-1.0), and pinned (Boolean, true if pinned to the opposite bottom/right edge). Breaking change: the integer values behind orientationType and positionType differ between versions of After Effects - always compare against the enumerated constants rather than raw integer literals. |
| hasVideo | *boolean* | R | 27.0 | When true, the layer has a video switch (the eyeball icon) in the Timeline panel; otherwise false. |
| id | *number* | R | 27.0 | Instance property on Layer which returns a unique and persistent identification number used internally to identify a Layer between sessions. The value of the ID remains the same when the project is saved to a file and later reloaded. However, when you import this project into another project, new IDs are assigned to all Layers in the imported project. The ID is not displayed anywhere in the user interface. |
| inPoint | *number* | RW | 27.0 | The "in" point of the layer, expressed in composition time (seconds). |
| index | *number* | R | 27.0 | The index position of the layer. |
| isEffect | *boolean* | R | 27.0 | When true, this property is an effect PropertyGroup. |
| isMask | *boolean* | R | 27.0 | When true, this property is a mask PropertyGroup. |
| isModified | *boolean* | R | 27.0 | When true, this property has been changed since its creation. |
| isNameSet | *boolean* | R | 27.0 | true if the value of the name attribute has been set explicitly, rather than automatically from the source. This always returns true for layers that do not have a source (see AVLayer.source). |
| label | *number* | RW | 27.0 | The label color for the item. Colors are represented by their number (0 for None, or 1 to 16 for one of the preset colors in the Labels preferences). Custom label colors cannot be set programmatically. |
| lightSource | *Layer* | RW | 27.0 | For a light layer, the layer to use as a light source when LightLayer.lightType is LightType.ENVIRONMENT. LightLayer.lightSource can be any 2D video, still, or pre-composition layer in the same composition. Attempting to assign a 3D layer as the .lightSource will result in an "Invalid light source specified" error. |
| lightType | *number* | RW | 27.0 | For a light layer, its light type. Trying to set this attribute for a non-light layer produces an error. |
| locked | *boolean* | RW | 27.0 | When true, the layer is locked; otherwise false. This corresponds to the lock toggle in the Layer panel. |
| matchName | *string* | R | 27.0 | A special name for the property used to build unique naming paths. The match name is not displayed, but you can refer to it in scripts. Every property has a unique match-name identifier. Match names are stable from version to version regardless of the display name (the name attribute value) or any changes to the application. Unlike the display name, it is not localized. An indexed group may not have a name value, but always has a matchName value. |
| name | *string* | RW | 27.0 | For a layer, the name of the layer. By default, this is the same as the Source name, unless Layer.isNameSet returns false. For an effect and all properties - the display name of the property. It is an error to set the name value if the property is not a child of an indexed group. |
| nullLayer | *boolean* | R | 27.0 | When true, the layer was created as a null object; otherwise false. |
| numProperties | *number* | R | 27.0 | The number of indexed properties in this group. For layers, this method returns a value of 3, corresponding to the mask, effect, and motion tracker groups, which are the indexed groups within the layer. However, layers also have many other properties available only by name; see PropertyGroup.property(). |
| outPoint | *number* | RW | 27.0 | The "out" point of the layer, expressed in composition time (seconds). |
| parent | *Layer* | RW | 27.0 | The parent of this layer; can be null. Offset values are calculated to counterbalance any transforms above this layer in the hierarchy, so that when you set the parent there is no apparent jump in the layer's transform. For example, if the new parent has a rotation of 30 degrees, the child layer is assigned a rotation of -30 degrees. To set the parent without changing the child layer's transform values, use the setParentWithJump method. |
| parentProperty | *Layer \| PropertyGroup* | R | 27.0 | The property group that is the immediate parent of this property, or null if this PropertyBase is a layer. |
| propertyDepth | *number* | R | 27.0 | The number of levels of parent groups between this property and the containing layer. The value 0 for a layer. |
| propertyType | *number* | R | 27.0 | The type of this property. |
| selected | *boolean* | RW | 27.0 | When true, this property is selected. Set to true to select the property, or to false to deselect it. Sampling this attribute repeatedly for a large number of properties can slow down system performance. To read the full set of selected properties of a composition or layer, use either CompItem.selectedProperties or Layer.selectedProperties. |
| selectedProperties | *Array* | R | 27.0 | An array containing all of the currently selected Property and PropertyGroup objects in the layer. |
| shy | *boolean* | RW | 27.0 | When true, the layer is "shy", meaning that it is hidden in the Layer panel if the composition's "Hide all shy layers" option is toggled on. |
| solo | *boolean* | RW | 27.0 | When true, the layer is soloed, otherwise false. |
| startTime | *number* | RW | 27.0 | The start time of the layer, expressed in composition time (seconds). |
| stretch | *number* | RW | 27.0 | The layer's time stretch, expressed as a percentage. A value of 100 means no stretch. Values between 0 and 1 are set to 1, and values between -1 and 0 (not including 0) are set to -1. |
| time | *number* | R | 27.0 | The current time of the layer, expressed in composition time (seconds). |
| propertyIndex | *number* | R | 27.0 | Always undefined for a layer - a Layer uses index instead. For other properties, the position index of this property within its parent group, if it is a child of an indexed group (a property group that has the type PropertyType.INDEXED_GROUP). |


## Instance Methods

### activeAtTime

Returns: *boolean*

Since: **27.0**

Returns true if this layer will be active at the specified time. To return true, the layer must be enabled, no other layer may be soloing unless this layer is soloed too, and the time must be between the inPoint and outPoint values of this layer.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *number* | The time in seconds. |

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

Creates and returns a PropertyBase object with the specified name, and adds it to this group. In general, you can only add properties to an indexed group (a property group that has the type PropertyType.INDEXED_GROUP). The only exception is a text animator property, which can be added to a named group (type PropertyType.NAMED_GROUP). If this method cannot create a property with the specified name, it generates an exception. To check that you can add a particular property to this group, call canAddProperty before calling this method. Warning: when you add a new property to an indexed group, the indexed group gets recreated from scratch, invalidating all existing references to properties. One workaround is to store the index of the added property with property.propertyIndex.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| matchName | *string* | The display name or matchName of the property to add. Supported forms: any match name addable through the UI (e.g. "ADBE Mask Atom", "ADBE Paint Atom", "ADBE Text Position", "ADBE Text Anchor Point"); when adding to an ADBE Mask Parade, "ADBE Mask Atom" or "Mask"; when adding to an ADBE Effect Parade, any effect by match name (e.g. "ADBE Bulge", "ADBE Glo2", "APC Vegas") or display name (e.g. "Bulge", "Glow", "Vegas"); for text animators, "ADBE Text Animator"; for selectors, "ADBE Text Selector" (Range), "ADBE Text Wiggly Selector" (Wiggly), or "ADBE Text Expressible Selector" (Expression). |

<HorizontalLine />

### addToMotionGraphicsTemplate

Returns: *boolean*

Since: **27.0**

Adds the layer to the Essential Graphics Panel for the specified composition. Returns true if the layer is successfully added, or otherwise false. If the layer cannot be added, it is either because it is not a layer type for which media can be replaced (referred to as Media Replacement Layers), or the layer has already been added to the EGP for that composition. After Effects will present a warning dialog if the layer cannot be added to the EGP. Use canAddToMotionGraphicsTemplate() to test whether the layer can be added first.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *object* | The composition where you wish to add the property to the EGP. |

<HorizontalLine />

### addToMotionGraphicsTemplateAs

Returns: *boolean*

Since: **27.0**

Adds the layer to the Essential Graphics Panel for the specified composition. Returns true if the layer is successfully added, or otherwise false. If the layer cannot be added, it is either because it is not a layer type for which media can be replaced (referred to as Media Replacement Layers), or the layer has already been added to the EGP for that composition. After Effects will present a warning dialog if the layer cannot be added to the EGP. Use canAddToMotionGraphicsTemplate() to test whether the layer can be added first.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *object* | The composition where you wish to add the property to the EGP. |
| arg1 | *string* | The new name. |

<HorizontalLine />

### addVariableFontAxis

Returns: *Property*

Since: **27.0**

Creates and returns a Property object for a variable font axis, and adds it to this property group. This method can only be called on the "ADBE Text Animator Properties" property group within a text animator. Common axis tags include (but are not limited to): "wght" - Weight (100-900 typical range), "wdth" - Width (percentage of normal width), "slnt" - Slant (angle in degrees), "ital" - Italic (0-1 range), "opsz" - Optical Size (point size). Fonts may also include custom axes with 4-character uppercase tags (e.g., "INFM" for Informality).

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| axisTag | *string* | The 4-character tag identifying the variable font axis (e.g., "wght", "wdth", "slnt", "ital"). |

<HorizontalLine />

### applyPreset

Returns: *boolean*

Since: **27.0**

Applies the specified collection of animation settings (an animation preset) to all the currently selected layers of the comp to which the layer belongs. If no layer is selected, it applies the animation preset to a new solid layer. Predefined animation preset files are installed in the Presets folder, and users can create new animation presets through the user interface. The animation preset is applied to the selected layer(s) of the comp, not to the layer whose applyPreset function is called; the layer whose applyPreset is called just determines the comp whose layers are processed.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *string* | The file containing the animation preset. |

<HorizontalLine />

### canAddProperty

Returns: *boolean*

Since: **27.0**

Returns true if a property with the given name can be added to this property group. For example, you can only add mask to a mask group. The only legal input arguments are "mask" or "ADBE Mask Atom".

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| matchName | *string* | The display name or match name of the property to be checked. |

<HorizontalLine />

### canAddToMotionGraphicsTemplate

Returns: *boolean*

Since: **27.0**

Test whether or not the layer can be added to the Essential Graphics Panel for the specified composition. Returns true if the layer can be added, or otherwise false. Media Replacement layers are recognized as AVLayers with a source set to a FootageItem (with specific source types) or a CompItem. The AVLayer must comply with restrictions: Layer.hasVideo must be true, AVLayer.adjustmentLayer must be false, Layer.nullLayer must be false, and if the source is a FootageItem its FootageSource must not be a SolidSource, and if that FootageSource is a FileSource it must not point to a non-media file (e.g. a JSX script file).

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *object* | The composition where you wish to add the property to the EGP. |

<HorizontalLine />

### copyToComp

Returns: *boolean*

Since: **27.0**

Copies the layer into the specified composition. The original layer remains unchanged. Creates a new Layer object with the same values as this one, and prepends the new object to the LayerCollection in the target CompItem. Copying in a layer changes the index positions of previously existing layers in the target composition. This is the same as copying and pasting a layer through the user interface.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| intoComp | *object* | The target composition. |

<HorizontalLine />

### doSceneEditDetection

Returns: *number[]*

Since: **27.0**

Runs Scene Edit Detection on the layer that the method is called on and returns an array containing the times of any detected scenes. This is the same as selecting a layer in the Timeline and choosing "Layer > Scene Edit Detection", with the single argument determining whether the edits are applied as markers, layer splits, pre-comps, or are not applied to the layer. doSceneEditDetection will fail and error if called on a non-video layer or a video layer with Time Remapping enabled.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *number* | How the detected edits will be applied: SceneEditDetectionMode.MARKERS creates markers at edit points, SPLIT splits the layer, SPLIT_PRECOMP splits and pre-composes each edit, NONE applies no changes to the layer. |

<HorizontalLine />

### duplicate

Returns: *Layer*

Since: **27.0**

Duplicates the layer. Creates a new Layer object in which all values are the same as in this one. This has the same effect as selecting a layer in the user interface and choosing Edit > Duplicate, except the selection in the user interface does not change when you call this method.

<HorizontalLine />

### getGuideAsObject

Returns: *GuideOptions*

Since: **27.0**

Returns the guide at the specified index as a GuideOptions object, which you can modify and pass back to setGuide(). This is a convenient way to read a guide's full state (orientation, position, position type, color, pinning).

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| index | *number* | The index of the guide to read. |

<HorizontalLine />

### getRenderGUID

Returns: *DeferredCall*

Since: **27.0**

Starts an asynchronous render of the layer at the given time on the specified thread and returns a DeferredCall. Calling .wait() on the result yields a render GUID string once the render completes; pass true for trace to enable additional tracing.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| seconds | *number* | The time, in seconds, at which to render the layer. |
| thread | *number* | The thread to render on, as a ProjectThread enumerated value (for example ProjectThread.MainThread). |
| trace | *boolean* | Whether to enable additional tracing for the render. |

<HorizontalLine />

### moveAfter

Returns: *boolean*

Since: **27.0**

Moves this layer to a position immediately after (below) the specified layer.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| otherLayer | *object* | The target layer in the same composition. |

<HorizontalLine />

### moveBefore

Returns: *boolean*

Since: **27.0**

Moves this layer to a position immediately before (above) the specified layer.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| otherLayer | *object* | The target layer in the same composition. |

<HorizontalLine />

### moveTo

Returns: *boolean*

Since: **27.0**

Moves this property to a new position in its parent property group. Valid only for children of indexed groups; otherwise generates an exception. Using this method invalidates existing references to other children in the same indexed group.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *number* | The new index position at which to place this property in its group. |

<HorizontalLine />

### moveToBeginning

Returns: *boolean*

Since: **27.0**

Moves this layer to the topmost position of the layer stack (the first layer).

<HorizontalLine />

### moveToEnd

Returns: *boolean*

Since: **27.0**

Moves this layer to the bottom position of the layer stack (the last layer).

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
| arg0 | *number* | Optional. The number of levels to ascend within the parent-child hierarchy. Default is 1, which gets the immediate parent. |

<HorizontalLine />

### remove

Returns: *boolean*

Since: **27.0**

Deletes the specified layer from the composition.

<HorizontalLine />

### removeGuide

Returns: *boolean*

Since: **27.0**

Removes an existing guide. Choose the guide based on its index inside the Layer.guides array.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| index | *number* | The index of the guide to be removed. |

<HorizontalLine />

### savePreset

Returns: *boolean*

Since: **27.0**

Saves the currently selected properties of this layer as an animation preset (.ffx) file at the given path. Returns true if the preset was written successfully, or false if nothing was selected to save (for example, if the layer itself is not selected).

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *string* | The file path to write the animation preset (.ffx) to. |

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

Sets the parent of this layer to the specified layer, without changing the transform values of the child layer. There may be an apparent jump in the rotation, translation, or scale of the child layer, as this layer's transform values are combined with those of its ancestors. If you do not want the child layer to jump, set the parent attribute directly instead.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| newParent | *object* | A layer in the same composition. Required in this binding - unlike ExtendScript's optional [newParent] signature, omitting it throws an error rather than clearing the parent. |

<HorizontalLine />
