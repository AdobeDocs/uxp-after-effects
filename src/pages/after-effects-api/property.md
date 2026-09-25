---
id: "property"
title: "Property"
description: "Contains value, keyframe, and expression information about a particular AE property of a layer."
sidebar_label: "Property"
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

# Property  

## Properties

| Name | Type | Access | Min Version | Description |
| :------ | :------ | :------ | :------ | :------ |
| LayerInputStageType | *LayerInputStageType* | R | 27.0 | Instance-level accessor exposing the `LayerInputStageType` enum object (e.g. `property.LayerInputStageType.SOURCE`), for convenience alongside `layerInputStage`/`setLayerInputStage`. |
| active | *boolean* | R | 27.0 | For a layer, corresponds to the eyeball icon; `true` when the layer's video is active at the current time (enabled, not overridden by another soloed layer, and within `inPoint`/`outPoint`). Never `true` for an audio layer. For an effect or property, same as `enabled` but read-only. |
| alternateSource | *AVItem* | R | 27.0 | The original source item used to create a Media Replacement Essential Property, or `null` if not set or not applicable. Use `canSetAlternateSource` to check eligibility. |
| canSetAlternateSource | *boolean* | R | 27.0 | `true` if this property is an Essential Property that supports Media Replacement. |
| canSetEnabled | *boolean* | R | 27.0 | `true` if the `enabled` attribute value can be set. Generally `true` if the UI shows an eyeball icon for this property; always `true` for layers. |
| canSetExpression | *boolean* | R | 27.0 | `true` if this property's type allows its expression to be set by a script. |
| canVaryOverTime | *boolean* | R | 27.0 | `true` if this property can vary over time - keyframe values or an expression can be written to it. |
| dimensionsSeparated | *boolean* | RW | 27.0 | `true` if the property's dimensions are represented as separate properties (e.g. X/Y Position). Only meaningful when `isSeparationLeader` is `true`. |
| elided | *boolean* | R | 27.0 | `true` if this property is an organizational group not shown in the UI, whose children are not indented in the Timeline panel. |
| enabled | *boolean* | RW | 27.0 | For a layer, the video switch state in the Timeline panel. For an effect or property, the eyeball icon setting, if present. |
| expression | *string* | RW | 27.0 |  |
| expressionEnabled | *boolean* | RW | 27.0 | When `true`, the property uses its associated expression to generate a value; when `false`, keyframes or the static value are used. Can only be set to `true` if `canSetExpression` and `expression` contains a valid expression string. |
| expressionError | *string* | R | 27.0 | The error, if any, from evaluating the most recently set `expression`. Empty string if no error occurred or none was set. |
| hasMax | *boolean* | R | 27.0 | `true` if there is a maximum permitted value for this property. |
| hasMin | *boolean* | R | 27.0 | `true` if there is a minimum permitted value for this property. |
| inputLayerAndStage | *number[]* | R | 27.0 | The `[layerIndex, stage]` this property currently reads its input from - `layerIndex` of `0` means no layer, `stage` is a `LayerInputStageType` value (or raw effect index). |
| isDropdownEffect | *boolean* | R | 27.0 | `true` if this is the Menu property of a Dropdown Menu Control effect, whose items can be updated with `setPropertyParameters`. |
| isEffect | *boolean* | R | 27.0 | `true` if this property is an effect PropertyGroup. |
| isMask | *boolean* | R | 27.0 | `true` if this property is a mask PropertyGroup. |
| isModified | *boolean* | R | 27.0 | `true` if this property has changed since it was created. |
| isSeparationFollower | *boolean* | R | 27.0 | `true` if this property represents one of the separated dimensions of a multidimensional property (e.g. X Position). |
| isSeparationLeader | *boolean* | R | 27.0 | `true` if this property is multidimensional and can be separated (e.g. Position). |
| isSpatial | *boolean* | R | 27.0 | `true` if this property defines a spatial value, e.g. position or an effect point control. |
| isTimeVarying | *boolean* | R | 27.0 | `true` if this property has keyframes or an enabled expression. Implies `canVaryOverTime` is `true`. |
| layerInputStage | *number* | R | 27.0 | The current `LayerInputStageType` (or raw effect index) this property reads its input from. Change it with `setLayerInputStage`. |
| matchName | *string* | R | 27.0 | A stable, unlocalized identifier for the property used to build unique naming paths. Unlike `name`, it doesn't change across versions. |
| maxValue | *number* | R | 27.0 | The maximum permitted value of this property. Throws an exception if `hasMax` is `false`. |
| mediaReplacementScaleMode | *number* | R | 27.0 | The `MediaReplacementScaleMode` used when this Essential Property's alternate source is rendered (e.g. Scale to Fill). |
| minValue | *number* | R | 27.0 | The minimum permitted value of this property. Throws an exception if `hasMin` is `false`. |
| name | *string* | RW | 27.0 | For a layer, its name (same as source name unless `isNameSet` is `false`). For an effect or property, its display name; settable only for children of an indexed group. |
| numKeys | *number* | R | 27.0 | The number of keyframes on this property. `0` means the property isn't keyframed. |
| parentProperty | *PropertyGroup \| Layer* | R | 27.0 | The immediate parent property group of this property, or `null` if this is a layer. |
| propertyDepth | *number* | R | 27.0 | The number of parent group levels between this property and its containing layer. `0` for a layer. |
| propertyIndex | *number* | R | 27.0 | The position index of this property within its parent group, if it's a child of an indexed group. |
| propertyParameters | *string[]* | R | 27.0 | The item strings of a dropdown menu property. Set via `setPropertyParameters`. |
| propertyType | *number* | R | 27.0 | The type of this property: `PropertyType.PROPERTY`, `PropertyType.INDEXED_GROUP`, or `PropertyType.NAMED_GROUP`. |
| propertyValueType | *number* | R | 27.0 | The `PropertyValueType` describing how this property's value is stored/retrieved (e.g. `OneD`, `ThreeD_SPATIAL`, `COLOR`, `SHAPE`, `TEXT_DOCUMENT`). |
| selected | *boolean* | RW | 27.0 | `true` if this property is selected in the UI. |
| selectedKeys | *number[]* | R | 27.0 | The indices of all selected keyframes on this property; empty array if none are selected or there are no keyframes. |
| separationDimension | *number* | R | 27.0 | For a separated follower, the dimension number it represents in the multidimensional leader (0-based; e.g. Y Position is `1`, X Position is `0`). |
| separationLeader | *Property* | R | 27.0 | For a separated follower, the original multidimensional property it was separated from (e.g. Position, for Y Position). |
| unitsText | *string* | R | 27.0 | The text description of the units this property's value is expressed in. |
| valueText | *string* | R | 27.0 | The text string of the currently-selected item in a dropdown menu property. |
| essentialPropertySource | *AVLayer \| Property* | R | 27.0 | On an Essential Property, the original source Property or AVLayer (Media Replacement Footage item) it was created from; `null` if not an Essential Property. |
| value | *any* | R | 27.0 | The value of this property at the current time: the evaluated expression value if `expressionEnabled`, else the keyframed value at the current time, else the static value. |


## Instance Methods

### addKey

Returns: *number*

Since: **27.0**

Adds a new keyframe or marker to this property at the specified time; returns the index of the new keyframe.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| time | *number* | The time, in seconds, at which to add the keyframe. |

<HorizontalLine />

### addToMotionGraphicsTemplate

Returns: *boolean*

Since: **27.0**

Adds this property to the Essential Graphics panel for the specified composition. `true` on success. Use `canAddToMotionGraphicsTemplate` to check eligibility first.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| comp | *object* | The composition to add the property to. |

<HorizontalLine />

### addToMotionGraphicsTemplateAs

Returns: *boolean*

Since: **27.0**

Same as `addToMotionGraphicsTemplate`, but lets you give the EGP property a custom name.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| comp | *object* | The composition to add the property to. |
| name | *string* | The new name. |

<HorizontalLine />

### canAddToMotionGraphicsTemplate

Returns: *boolean*

Since: **27.0**

Tests whether this property can be added to the Essential Graphics panel for the specified composition. Supported types: Checkbox, Color, Numerical Slider, Source Text.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| comp | *object* | The composition to test. |

<HorizontalLine />

### duplicate

Returns: *Property*

Since: **27.0**

If a child of an indexed group, creates and returns a copy of this property with the same values. Throws otherwise.

<HorizontalLine />

### getInputStageCycleSafeLimit

Returns: *number*

Since: **27.0**

Returns the highest `LayerInputStageType` this property can safely be wired to without creating a reference cycle.

<HorizontalLine />

### getSeparationFollower

Returns: *Property*

Since: **27.0**

For a separated, multidimensional property, retrieves the follower property for the given dimension (e.g. X/Y Position from Position).

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| dim | *number* | The dimension number (starting at 0). |

<HorizontalLine />

### isInterpolationTypeValid

Returns: *boolean*

Since: **27.0**

`true` if this property can be interpolated using the specified `KeyframeInterpolationType`.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| type | *number* | The `KeyframeInterpolationType` to test: `LINEAR`, `BEZIER`, or `HOLD`. |

<HorizontalLine />

### keyInInterpolationType

Returns: *number*

Since: **27.0**

Returns the incoming interpolation type for the specified keyframe.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| keyIndex | *number* | The index for the keyframe, as returned by `addKey` or `nearestKeyIndex`. |

<HorizontalLine />

### keyInSpatialTangent

Returns: *number[]*

Since: **27.0**

Returns the incoming spatial tangent for the specified keyframe, if this property is spatial (`TwoD_SPATIAL`/`ThreeD_SPATIAL`).

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| keyIndex | *number* | The index for the keyframe, as returned by `addKey` or `nearestKeyIndex`. |

<HorizontalLine />

### keyInTemporalEase

Returns: *Array*

Since: **27.0**

Returns the incoming temporal ease (KeyframeEase objects) for the specified keyframe.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| keyIndex | *number* | The index for the keyframe, as returned by `addKey` or `nearestKeyIndex`. |

<HorizontalLine />

### keyLabel

Returns: *number*

Since: **27.0**

The label color (0-16) for the specified keyframe. Set via `setLabelAtKey`.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| keyIndex | *number* | The index for the keyframe, as returned by `addKey` or `nearestKeyIndex`. |

<HorizontalLine />

### keyOutInterpolationType

Returns: *number*

Since: **27.0**

Returns the outgoing interpolation type for the specified keyframe.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| keyIndex | *number* | The index for the keyframe, as returned by `addKey` or `nearestKeyIndex`. |

<HorizontalLine />

### keyOutSpatialTangent

Returns: *number[]*

Since: **27.0**

Returns the outgoing spatial tangent for the specified keyframe.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| keyIndex | *number* | The index for the keyframe, as returned by `addKey` or `nearestKeyIndex`. |

<HorizontalLine />

### keyOutTemporalEase

Returns: *Array*

Since: **27.0**

Returns the outgoing temporal ease for the specified keyframe.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| keyIndex | *number* | The index for the keyframe, as returned by `addKey` or `nearestKeyIndex`. |

<HorizontalLine />

### keyRoving

Returns: *boolean*

Since: **27.0**

`true` if the specified keyframe is roving. The first/last keyframe can never rove. Throws if the property isn't spatial.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| keyIndex | *number* | The index for the keyframe, as returned by `addKey` or `nearestKeyIndex`. |

<HorizontalLine />

### keySelected

Returns: *boolean*

Since: **27.0**

`true` if the specified keyframe is selected.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| keyIndex | *number* | The index for the keyframe, as returned by `addKey` or `nearestKeyIndex`. |

<HorizontalLine />

### keySpatialAutoBezier

Returns: *boolean*

Since: **27.0**

`true` if the specified keyframe has spatial auto-Bezier interpolation. Throws if the property isn't spatial.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| keyIndex | *number* | The index for the keyframe, as returned by `addKey` or `nearestKeyIndex`. |

<HorizontalLine />

### keySpatialContinuous

Returns: *boolean*

Since: **27.0**

`true` if the specified keyframe has spatial continuity. Throws if the property isn't spatial.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| keyIndex | *number* | The index for the keyframe, as returned by `addKey` or `nearestKeyIndex`. |

<HorizontalLine />

### keyTemporalAutoBezier

Returns: *boolean*

Since: **27.0**

`true` if the specified keyframe has temporal auto-Bezier interpolation (effective only when both interpolation types are Bezier).

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| keyIndex | *number* | The index for the keyframe, as returned by `addKey` or `nearestKeyIndex`. |

<HorizontalLine />

### keyTemporalContinuous

Returns: *boolean*

Since: **27.0**

`true` if the specified keyframe has temporal continuity (effective only when both interpolation types are Bezier).

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| keyIndex | *number* | The index for the keyframe, as returned by `addKey` or `nearestKeyIndex`. |

<HorizontalLine />

### keyTime

Returns: *number*

Since: **27.0**

Finds the specified keyframe or marker and returns the time it occurs at. Throws if none matches.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| keyIndexOrMarkerComment | *number* or *string* | The keyframe index, or the comment attached to a marker. |

<HorizontalLine />

### keyValue

Returns: *any*

Since: **27.0**

Finds the specified keyframe or marker and returns its current value. Throws if none matches.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| keyIndexOrMarkerComment | *number* or *string* | The keyframe index, or the comment attached to a marker. |

<HorizontalLine />

### moveTo

Returns: *boolean*

Since: **27.0**

Moves this property to a new index in its parent group. Only valid for children of indexed groups; invalidates existing sibling references.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| newIndex | *number* | The new index position at which to place this property in its group. |

<HorizontalLine />

### nearestKeyIndex

Returns: *number*

Since: **27.0**

Returns the index of the keyframe nearest to the specified time.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| time | *number* | The time, in seconds. |

<HorizontalLine />

### propertyGroup

Returns: *PropertyGroup*

Since: **27.0**

Gets the ancestor PropertyGroup at a specified level up the parent-child hierarchy (default: immediate parent). Returns the Layer if the count reaches the containing layer.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| countUp | *number* | Optional. The number of levels to ascend within the parent-child hierarchy. Default is 1, which gets the immediate parent. |

<HorizontalLine />

### remove

Returns: *boolean*

Since: **27.0**

Removes this property (and any children) from its parent group. Only valid for children of indexed groups; can be called on a text animator.

<HorizontalLine />

### removeKey

Returns: *boolean*

Since: **27.0**

Removes the specified keyframe. Remaining indices shift down; remove from highest index to lowest when removing multiple.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| keyIndex | *number* | The index for the keyframe, as returned by `addKey` or `nearestKeyIndex`. |

<HorizontalLine />

### setAlternateSource

Returns: *boolean*

Since: **27.0**

Sets the alternate source AVItem for this Media Replacement property. Both the property and the AVItem must be Media Replacement compatible.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| newSource | *object* | The new source AVItem. |

<HorizontalLine />

### setInputLayerAndStage

Returns: *boolean*

Since: **27.0**

Sets the layer index and `LayerInputStageType` (or raw effect index) this property reads its input from.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| layerIndex | *number* | The index of the layer to read input from. `0` means no layer. |
| stageIndex | *number* | The `LayerInputStageType` (or raw effect index) to read from that layer. |

<HorizontalLine />

### setInterpolationTypeAtKey

Returns: *boolean*

Since: **27.0**

Sets the in/out interpolation types for the specified keyframe. If `outType` isn't given, it's set to `inType`.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| keyIndex | *number* | The index for the keyframe, as returned by `addKey` or `nearestKeyIndex`. |
| inType | *number* | The incoming interpolation type: `KeyframeInterpolationType.LINEAR`, `BEZIER`, or `HOLD`. |
| outType | *number* | Optional. The outgoing interpolation type. If not supplied, set to the `inType` value. |

<HorizontalLine />

### setLabelAtKey

Returns: *boolean*

Since: **27.0**

Sets the label color (0-16) for the specified keyframe.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| keyIndex | *number* | The index for the keyframe, as returned by `addKey` or `nearestKeyIndex`. |
| labelIndex | *number* | The index for the new label value, in the range `[0..16]`. |

<HorizontalLine />

### setLayerInputStage

Returns: *boolean*

Since: **27.0**

Sets the `LayerInputStageType` (or raw effect index, 0-5) this property reads its input from.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| stageIndex | *number* | The `LayerInputStageType` (or raw effect index) to set. |

<HorizontalLine />

### setPropertyParameters

Returns: *Property*

Since: **27.0**

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *string[]* | - |

<HorizontalLine />

### setRovingAtKey

Returns: *boolean*

Since: **27.0**

Turns roving on/off for the specified keyframe. Ignored for the first/last keyframe. Throws if the property isn't spatial.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| keyIndex | *number* | The index for the keyframe, as returned by `addKey` or `nearestKeyIndex`. |
| newVal | *boolean* | `true` to turn roving on, `false` to turn it off. |

<HorizontalLine />

### setSelectedAtKey

Returns: *boolean*

Since: **27.0**

Selects or deselects the specified keyframe.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| keyIndex | *number* | The index for the keyframe, as returned by `addKey` or `nearestKeyIndex`. |
| onOff | *boolean* | `true` to select the keyframe, `false` to deselect it. |

<HorizontalLine />

### setSpatialAutoBezierAtKey

Returns: *boolean*

Since: **27.0**

Turns spatial auto-Bezier interpolation on/off for the specified keyframe. Throws if the property isn't spatial.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| keyIndex | *number* | The index for the keyframe, as returned by `addKey` or `nearestKeyIndex`. |
| newVal | *boolean* | `true` to turn spatial auto-Bezier on, `false` to turn it off. |

<HorizontalLine />

### setSpatialContinuousAtKey

Returns: *boolean*

Since: **27.0**

Turns spatial continuity on/off for the specified keyframe. Throws if the property isn't spatial.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| keyIndex | *number* | The index for the keyframe, as returned by `addKey` or `nearestKeyIndex`. |
| newVal | *boolean* | `true` to turn spatial continuity on, `false` to turn it off. |

<HorizontalLine />

### setSpatialTangentsAtKey

Returns: *boolean*

Since: **27.0**

Sets the incoming and outgoing tangent vectors for the specified keyframe. If the outgoing tangent isn't given, it's set to the incoming value. Throws if the property isn't spatial.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| keyIndex | *number* | The index for the keyframe, as returned by `addKey` or `nearestKeyIndex`. |
| inTan | *number[]* | An array of 2 or 3 floating-point values, matching the property's spatial dimension. NOTE: due to a generator limitation, this description applies to both `inTan` rows shown - the first is the incoming tangent vector, the second is actually the optional outgoing tangent vector (`outTan`), defaulting to the incoming value if omitted. |
| inTan | *number[]* | An array of 2 or 3 floating-point values, matching the property's spatial dimension. NOTE: due to a generator limitation, this description applies to both `inTan` rows shown - the first is the incoming tangent vector, the second is actually the optional outgoing tangent vector (`outTan`), defaulting to the incoming value if omitted. |

<HorizontalLine />

### setTemporalAutoBezierAtKey

Returns: *boolean*

Since: **27.0**

Turns temporal auto-Bezier interpolation on/off for the specified keyframe.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| keyIndex | *number* | The index for the keyframe, as returned by `addKey` or `nearestKeyIndex`. |
| newVal | *boolean* | `true` to turn temporal auto-Bezier on, `false` to turn it off. |

<HorizontalLine />

### setTemporalContinuousAtKey

Returns: *boolean*

Since: **27.0**

Turns temporal continuity on/off for the specified keyframe.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| keyIndex | *number* | The index for the keyframe, as returned by `addKey` or `nearestKeyIndex`. |
| newVal | *boolean* | `true` to turn temporal continuity on, `false` to turn it off. |

<HorizontalLine />

### setTemporalEaseAtKey

Returns: *boolean*

Since: **27.0**

Sets the incoming and outgoing temporal ease for the specified keyframe. If the outgoing ease isn't given, it's set to the incoming value.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| keyIndex | *number* | The index for the keyframe, as returned by `addKey` or `nearestKeyIndex`. |
| inTemporalEase | *Array* | An array of 1, 2, or 3 KeyframeEase objects for the incoming temporal ease, matching the property's value type dimension. |
| outTemporalEase | *Array* | Optional. An array of 1, 2, or 3 KeyframeEase objects for the outgoing temporal ease. If not supplied, set to the `inTemporalEase` value. |

<HorizontalLine />

### setValue

Returns: *void*

Since: **27.0**

Sets the static value of a property with no keyframes. Throws if the property has keyframes - use `setValueAtTime`/`setValueAtKey` instead.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| newValue | *any* | A value appropriate for the property's type; see `propertyValueType`. |

<HorizontalLine />

### setValueAtKey

Returns: *void*

Since: **27.0**

Finds the specified keyframe and sets its value. Throws if no matching keyframe exists.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| keyIndex | *number* | The index of the keyframe to set. |
| newValue | *any* | A value appropriate for the property's type; see `propertyValueType`. |

<HorizontalLine />

### setValueAtTime

Returns: *void*

Since: **27.0**

Sets the value at the specified time, creating a new keyframe there if one doesn't exist.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| time | *number* | The time, in seconds, at which to set the value. |
| newValue | *any* | A value appropriate for the property's type; see `propertyValueType`. |

<HorizontalLine />

### setValuesAtTimes

Returns: *void*

Since: **27.0**

Sets values for a set of keyframes at specified times (parallel arrays), creating new keyframes as needed.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| times | *number[]* | An array of times, in seconds. |
| values | *any[]* | An array of values appropriate for the property's type, matching `times` in length; see `propertyValueType`. |

<HorizontalLine />

### valueAtTime

Returns: *any*

Since: **27.0**

The property's value evaluated at the specified time. `preExpression = true` returns the pre-expression value; `false` evaluates the expression. Ignored if there's no expression.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| time | *number* | The time, in seconds, at which to evaluate the property. |
| preExpression | *boolean* | Optional. If the property has an expression and this is `true`, returns the value at the specified time without applying the expression. When `false`, returns the result of evaluating the expression. Ignored if the property has no expression. |

<HorizontalLine />
