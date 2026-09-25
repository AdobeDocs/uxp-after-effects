---
id: "solidsource"
title: "SolidSource"
description: "Represents the source of a solid-color footage item."
sidebar_label: "SolidSource"
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

# SolidSource  

## Properties

| Name | Type | Access | Min Version | Description |
| :------ | :------ | :------ | :------ | :------ |
| alphaMode | *number* | RW | 27.0 | Defines how the alpha information in the footage is interpreted. If `hasAlpha` is `false`, this attribute has no relevant meaning. |
| color | *number[]* | RW | 27.0 | The color of the solid, expressed as red, green, and blue values, in the range `[0.0..1.0]`. |
| conformFrameRate | *number* | RW | 27.0 | A frame rate to use instead of the `nativeFrameRate` value. If set to 0, the `nativeFrameRate` is used instead. It is an error to set this value if `isStill` is `true`. It is an error to set this value to 0 if `removePulldown` is not set to `PulldownPhase.OFF`. If this is 0 when you set `removePulldown` to a value other than `PulldownPhase.OFF`, then this is automatically set to the value of `nativeFrameRate`. |
| displayFrameRate | *number* | R | 27.0 | The effective frame rate as displayed and rendered in compositions by After Effects. If `removePulldown` is `PulldownPhase.OFF`, then this is the same as the `conformFrameRate` (if non-zero) or the `nativeFrameRate` (if `conformFrameRate` is 0). If `removePulldown` is not `PulldownPhase.OFF`, this is `conformFrameRate * 0.8`, the effective frame rate after removing 1 of every 5 frames. |
| fieldSeparationType | *number* | RW | 27.0 | How the fields are to be separated in non-still footage. It is an error to set this attribute if `isStill` is `true`. It is an error to set this value to `FieldSeparationType.OFF` if `removePulldown` is not `PulldownPhase.OFF`. |
| hasAlpha | *boolean* | R | 27.0 | When `true`, the footage has an alpha component. In this case, the attributes `alphaMode`, `invertAlpha`, and `premulColor` have valid values. When `false`, those attributes have no relevant meaning for the footage. |
| highQualityFieldSeparation | *boolean* | RW | 27.0 | When `true`, After Effects uses special algorithms to determine how to perform high-quality field separation. It is an error to set this attribute if `isStill` is `true`, or if `fieldSeparationType` is `FieldSeparationType.OFF`. |
| invertAlpha | *boolean* | RW | 27.0 | When `true`, an alpha channel in a footage clip or proxy should be inverted. This attribute is valid only if an alpha is present. If `hasAlpha` is `false`, or if `alphaMode` is `AlphaMode.IGNORE`, this attribute is ignored. |
| isStill | *boolean* | R | 27.0 | When `true` the footage is still; When `false`, it has a time-based component. Examples of still footage are JPEG files, solids, and placeholders with a duration of 0. Examples of non-still footage are movie files, sound files, sequences, and placeholders of non-zero duration. |
| loop | *number* | RW | 27.0 | The number of times that the footage is to be played consecutively when used in a composition. It is an error to set this attribute if `isStill` is `true`. |
| nativeFrameRate | *number* | R | 27.0 | The native frame rate of the footage. |
| premulColor | *number[]* | RW | 27.0 | The color to be premultiplied. This attribute is valid only if the `alphaMode` is `alphaMode.PREMULTIPLIED`. |
| removePulldown | *number* | RW | 27.0 | How the pulldowns are to be removed when field separation is used. It is an error to set this attribute if `isStill` is `true`. It is an error to attempt to set this to a value other than `PulldownPhase.OFF` in the case where `fieldSeparationType` is `FieldSeparationType.OFF`. |


## Instance Methods

### guessAlphaMode

Returns: *boolean*

Since: **27.0**

Sets `alphaMode`, `premulColor`, and `invertAlpha` to the best estimates for this footage source. If `hasAlpha` is `false`, no change is made.

<HorizontalLine />

### guessPulldown

Returns: *boolean*

Since: **27.0**

Sets `fieldSeparationType` and `removePulldown` to the best estimates for this footage source. If `isStill` is `true`, no change is made.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *number* | The method to use for estimation. One of: `PulldownMethod.PULLDOWN_3_2`, `PulldownMethod.ADVANCE_24P`. |

<HorizontalLine />
