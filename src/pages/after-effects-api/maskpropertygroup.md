---
id: "maskpropertygroup"
title: "MaskPropertyGroup"
description: "Represents a group of related mask properties within a layer."
sidebar_label: "MaskPropertyGroup"
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

# MaskPropertyGroup  

## Properties

| Name | Type | Access | Min Version | Description |
| :------ | :------ | :------ | :------ | :------ |
| active | *boolean* | R | 27.0 | For a layer, corresponds to the eyeball icon; `true` when the layer's video is active at the current time (enabled, not overridden by another soloed layer, and within `inPoint`/`outPoint`). Never `true` for an audio layer. For an effect or property, same as `enabled` but read-only. |
| canSetEnabled | *boolean* | R | 27.0 | `true` if the `enabled` attribute value can be set. Generally `true` if the UI shows an eyeball icon for this property; always `true` for layers. |
| color | *number[]* | RW | 27.0 | The color used to draw the mask outline as it appears in the UI (Composition, Layer, and Timeline panels), as `[R, G, B]` in the range `[0.0..1.0]`. |
| elided | *boolean* | R | 27.0 | `true` if this property is an organizational group not shown in the UI, whose children are not indented in the Timeline panel. |
| enabled | *boolean* | RW | 27.0 | For a layer, the video switch state in the Timeline panel. For an effect or property, the eyeball icon setting, if present. |
| inverted | *boolean* | RW | 27.0 | When `true`, the mask is inverted. |
| isEffect | *boolean* | R | 27.0 | `true` if this property is an effect PropertyGroup. |
| isMask | *boolean* | R | 27.0 | `true` if this property is a mask PropertyGroup. |
| isModified | *boolean* | R | 27.0 | `true` if this property has changed since it was created. |
| locked | *boolean* | RW | 27.0 | When `true`, the mask is locked and cannot be edited in the UI. |
| maskFeatherFalloff | *number* | RW | 27.0 | The feather falloff mode for the mask (Layer > Mask > Feather Falloff). One of `MaskFeatherFalloff.FFO_LINEAR`, `MaskFeatherFalloff.FFO_SMOOTH`. |
| maskMode | *number* | RW | 27.0 | The masking mode for this mask. One of `MaskMode.NONE`, `ADD`, `SUBTRACT`, `INTERSECT`, `LIGHTEN`, `DARKEN`, `DIFFERENCE`. |
| maskMotionBlur | *number* | RW | 27.0 | How motion blur is applied to this mask. One of `MaskMotionBlur.SAME_AS_LAYER`, `ON`, `OFF`. |
| matchName | *string* | R | 27.0 | A stable, unlocalized identifier for the property used to build unique naming paths. Unlike `name`, it doesn't change across versions. |
| name | *string* | RW | 27.0 | For a layer, its name (same as source name unless `isNameSet` is `false`). For an effect or property, its display name; settable only for children of an indexed group. |
| numProperties | *number* | R | 27.0 | The number of indexed properties in this group. For layers, this returns 3 (the mask, effect, and motion tracker groups). Other properties are available only by name; see `property()`. |
| parentProperty | *PropertyGroup \| Layer* | R | 27.0 | The immediate parent property group of this property, or `null` if this is a layer. |
| propertyDepth | *number* | R | 27.0 | The number of parent group levels between this property and its containing layer. `0` for a layer. |
| propertyIndex | *number* | R | 27.0 | The position index of this property within its parent group, if it's a child of an indexed group. |
| propertyType | *number* | R | 27.0 | The type of this property: `PropertyType.PROPERTY`, `PropertyType.INDEXED_GROUP`, or `PropertyType.NAMED_GROUP`. |
| rotoBezier | *boolean* | RW | 27.0 | When `true`, the mask is a RotoBezier shape. |
| selected | *boolean* | RW | 27.0 | `true` if this property is selected in the UI. |


## Instance Methods

### addProperty

Returns: *PropertyGroup*

Since: **27.0**

Creates and returns a PropertyBase object with the specified name, and adds it to this group. In general, you can only add properties to an indexed group (a property group that has the type `PropertyType.INDEXED_GROUP`). The only exception is a text animator property, which can be added to a named group (type `PropertyType.NAMED_GROUP`). If this method cannot create a property with the specified name, it generates an exception. To check that you can add a particular property to this group, call `canAddProperty` before calling this method. Warning: when you add a new property to an indexed group, the indexed group gets recreated from scratch, invalidating all existing references to properties. One workaround is to store the index of the added property with `propertyIndex`.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| matchName | *string* | The display name or matchName of the property to add. Supported forms: any match name addable through the UI (e.g. "ADBE Mask Atom", "ADBE Paint Atom", "ADBE Text Position", "ADBE Text Anchor Point"); when adding to an ADBE Mask Parade, "ADBE Mask Atom" or "Mask"; when adding to an ADBE Effect Parade, any effect by match name (e.g. "ADBE Bulge", "ADBE Glo2", "APC Vegas") or display name (e.g. "Bulge", "Glow", "Vegas"); for text animators, "ADBE Text Animator"; for selectors, "ADBE Text Selector" (Range), "ADBE Text Wiggly Selector" (Wiggly), or "ADBE Text Expressible Selector" (Expression). |

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

### addVariableFontAxis

Returns: *Property*

Since: **27.0**

Creates and returns a Property object for a variable font axis, and adds it to this property group. This method can only be called on the "ADBE Text Animator Properties" property group within a text animator. Common axis tags include (but are not limited to): "wght" - Weight (100-900 typical range), "wdth" - Width (percentage of normal width), "slnt" - Slant (angle in degrees), "ital" - Italic (0-1 range), "opsz" - Optical Size (point size). Fonts may also include custom axes with 4-character uppercase tags (e.g., "INFM" for Informality).

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| axisTag | *string* | The 4-character tag identifying the variable font axis (e.g., "wght", "wdth", "slnt", "ital"). |

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

Tests whether this property can be added to the Essential Graphics panel for the specified composition. Supported types: Checkbox, Color, Numerical Slider, Source Text.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| comp | *object* | The composition to test. |

<HorizontalLine />

### duplicate

Returns: *MaskPropertyGroup*

Since: **27.0**

If a child of an indexed group, creates and returns a copy of this property group with the same values. Throws otherwise.

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
