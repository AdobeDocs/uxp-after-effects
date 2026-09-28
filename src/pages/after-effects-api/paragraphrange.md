---
id: "paragraphrange"
title: "ParagraphRange"
description: "Represents a single paragraph's worth of text in a Text layer's source text, used to read and set paragraph-level styling."
sidebar_label: "ParagraphRange"
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

# ParagraphRange  

## Properties

| Name | Type | Access | Min Version | Description |
| :------ | :------ | :------ | :------ | :------ |
| characterEnd | *number* | R | 27.0 | The Text layer range calculated character end value. Throws an exception on access if the effective value would exceed the bounds of the related TextDocument object. |
| characterStart | *number* | R | 27.0 | The Text layer range calculated character start value. Throws an exception on access if the effective value would exceed the bounds of the related TextDocument object. |
| isRangeValid | *boolean* | R | 27.0 | Returns `true` if the current range is within the bounds of the related TextDocument object, otherwise `false`. |


## Instance Methods

### characterRange

Returns: *CharacterRange*

Since: **27.0**

Returns a CharacterRange object initialized from characterStart and characterEnd. Will throw an exception if isRangeValid would return `false`. The returned instance, once created, is independent of subsequent changes to the ParagraphRange it came from.

<HorizontalLine />

### toString

Returns: *string*

Since: **27.0**

Returns a string with the parameters used to create the ParagraphRange instance, e.g. "ParagraphRange(0,-1)". This may be safely called on an instance where isRangeValid returns `false`.

<HorizontalLine />
