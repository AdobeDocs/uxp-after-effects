---
id: "characterrange"
title: "CharacterRange"
description: "Represents a range of characters within a Text layer's source text, used to read and set character-level text styling."
sidebar_label: "CharacterRange"
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

# CharacterRange  

## Properties

| Name | Type | Access | Min Version | Description |
| :------ | :------ | :------ | :------ | :------ |
| allCaps | *boolean* | R | 27.0 | `true` if a Text layer has All Caps enabled; otherwise `false`. To set this value, use `fontCapsOption` added in After Effects 24.0. |
| applyFill | *boolean* | RW | 27.0 | When `true`, the Text layer shows a fill. Access the `fillColor` attribute for the actual color. When `false`, only a stroke is shown. |
| applyStroke | *boolean* | RW | 27.0 | When `true`, the Text layer shows a stroke. Access the `strokeColor` attribute for the actual color and `strokeWidth` for its thickness. When `false`, only a fill is shown. |
| autoHyphenate | *boolean* | RW | 27.0 | The Text layer's auto hyphenate paragraph option. If this attribute has a mixed value, it will be read as `undefined`. |
| autoKernType | *number* | RW | 27.0 | The Text layer's auto kern type option. |
| autoLeading | *boolean* | RW | 27.0 | The Text layer's auto leading character option. If this attribute has a mixed value, it will be read as `undefined`. |
| baselineDirection | *number* | RW | 27.0 | The Text layer's baseline direction option. This is significant for Japanese language in vertical texts. "BASELINE_VERTICAL_CROSS_STREAM" is also know as Tate-Chu-Yoko. |
| baselineShift | *number* | RW | 27.0 | This Text layer's baseline shift in pixels. |
| characterEnd | *number* | R | 27.0 | The Text layer range calculated character end value. Throws an exception on access if the effective value would exceed the bounds of the related TextDocument object. |
| characterStart | *number* | R | 27.0 | The Text layer range calculated character start value. Throws an exception on access if the effective value would exceed the bounds of the related TextDocument object. |
| composerEngine | *number* | RW | 27.0 | The Text layer's paragraph composer engine option. By default new Text layers will use the `ComposerEngine.UNIVERSAL_TYPE_ENGINE`; the other enum value will only be encountered in projects created before the Universal Type Engine engine (formerly known as the South Asian and Middle Eastern engine) became the default in After Effects 22.1.1. If this attribute has a mixed value, it will be read as `undefined`. This attrribute is read-write, but an exception will be thrown if any enum value other than `ComposerEngine.UNIVERSAL_TYPE_ENGINE` is written. In effect, you can change an older document from `ComposerEngine.LATIN_CJK_ENGINE` to `ComposerEngine.UNIVERSAL_TYPE_ENGINE`, but not the reverse. |
| digitSet | *number* | RW | 27.0 | The Text layer's digit set option. |
| direction | *number* | RW | 27.0 | The Text layer's paragraph direction option. If this attribute has a mixed value, it will be read as `undefined`. |
| endIndent | *number* | RW | 27.0 | The Text layer's paragraph end indent option. If this attribute has a mixed value, it will be read as `undefined`. |
| everyLineComposer | *boolean* | RW | 27.0 | The Text layer's Every-Line Composer paragraph option. If set to `false`, the TextDocument will use the Single-Line Composer. If this attribute has a mixed value, it will be read as `undefined`. |
| fauxBold | *boolean* | RW | 27.0 | `true` if a Text layer has faux bold enabled; otherwise `false`. |
| fauxItalic | *boolean* | RW | 27.0 | `true` if a Text layer has faux italic enabled; otherwise `false`. |
| fillColor | *number[]* | RW | 27.0 | The Text layer range CharacterRange attribute Fill Color, as an array of `[r, g, b]` floating-point values. For example, in an 8-bpc project, a red value of 255 would be 1.0, and in a 32-bpc project, an overbright blue value can be something like 3.2. Setting this value will also set `applyFill` to `true` across the affected characters. If this attribute has a mixed value for the range of characters, it will be read as `undefined`. In contrast to the same attribute on the TextDocument API, we will not throw an exception on read if `applyFill` is not `true`. |
| firstLineIndent | *number* | RW | 27.0 | The Text layer's paragraph first line indent option. If this attribute has a mixed value, it will be read as `undefined`. |
| font | *string* | RW | 27.0 | The Text layer's font specified by its PostScript name. On write, there are very few resrictions on what can be supplied - if the underlying font management system does not have a matching Font object instance matching the supplied PostScript name a substitute instance will be created. The Font instance returned in the case of duplicate PostScript names will be the 0th element of the array returned from FontsObject.getFontsByPostScriptName(). You should use the Font object attribute for precise control. |
| fontBaselineOption | *number* | RW | 27.0 | The Text layer's font baseline option. This is for setting a textDocument to superscript or subscript. |
| fontCapsOption | *number* | RW | 27.0 | The Text layer's font caps option. |
| fontFamily | *string* | R | 27.0 | String with with the name of the font family. |
| fontLocation | *string* | R | 27.0 | Path of font file, providing its location on disk. Not guaranteed to be returned for all font types; return value may be empty string for some kinds of fonts. |
| fontObject | *Font* | RW | 27.0 | The Text layer's Font object specified by its PostScript name. |
| fontSize | *number* | RW | 27.0 | The Text layer's font size in pixels. |
| fontStyle | *string* | R | 27.0 | String with style information, e.g., "bold", "italic" |
| hangingRoman | *boolean* | RW | 27.0 | The Text layer's Roman Hanging Punctuation paragraph option. This is only meaningful to box Text layers - it allows punctuation to fit outside the box rather than flow to the next line. If this attribute has a mixed value, it will be read as `undefined`. |
| horizontalScale | *number* | RW | 27.0 | This Text layer's horizontal scale in pixels. |
| isRangeValid | *boolean* | R | 27.0 | Returns `true` if the current range is within the bounds of the related TextDocument object, otherwise `false`. |
| justification | *number* | RW | 27.0 | The paragraph justification for the Text layer. |
| kerning | *number* | RW | 27.0 | The Text layer range character attribute kerning option. This effectively reports the manual kerning value, and not the calculated kerning value from auto kerning. If autoKernType in the range is set to `AutoKernType.METRIC_KERN`, `AutoKernType.OPTICAL_KERN`, or is mixed, then this attribute will be returned as `undefined`. If autoKernType in the range is set to `AutoKernType.NO_AUTO_KERN`, and this attribute has a mixed value, it will be read as `undefined`. Setting this value will also set `AutoKernType.NO_AUTO_KERN` to `true` across the affected characters. |
| leading | *number* | RW | 27.0 | The Text layer's spacing between lines. Returns zero if `autoLeading` is `true`. Setting this value will also set `autoLeading` to `true` across the affected characters. The minimum accepted value to set is 0, but this will be silently clipped to 0.01. |
| leadingType | *number* | RW | 27.0 | The Text layer's paragraph leading type option. If this attribute has a mixed value, it will be read as `undefined`. |
| ligature | *boolean* | RW | 27.0 | The Text layer's ligature option. |
| lineJoinType | *number* | RW | 27.0 | The Text layer's line join type option for Stroke. |
| noBreak | *boolean* | RW | 27.0 | The Text layer's no break attribute. |
| smallCaps | *boolean* | R | 27.0 | `true` if a Text layer has small caps enabled; otherwise `false`. To set this value, use `fontCapsOption` added in After Effects 24.0. |
| spaceAfter | *number* | RW | 27.0 | The Text layer's paragraph space after option. If this attribute has a mixed value, it will be read as `undefined`. |
| spaceBefore | *number* | RW | 27.0 | The Text layer's paragraph space before option. If this attribute has a mixed value, it will be read as `undefined`. |
| startIndent | *number* | RW | 27.0 | The Text layer's paragraph start indent option. If this attribute has a mixed value, it will be read as `undefined`. |
| strokeColor | *number[]* | RW | 27.0 | The Text layer CharacterRange stroke color character property, as an array of [r, g, b] floating-point values. For example, in an 8-bpc project, a red value of 255 would be 1.0, and in a 32-bpc project, an overbright blue value can be something like 3.2. If this attribute has a mixed value, it will be read as `undefined`. Setting this value will also set `applyStroke` to `true` across the affected characters. In contrast to the same attribute on the TextDocument API, we will not throw an exception on read if `applyStroke` is not `true`. |
| strokeOverFill | *boolean* | RW | 27.0 | The Text layer CharacterRange Stroke Over Fill character property. Indicates the rendering order for the fill and stroke for characters in the range. When `true`, the stroke appears over the fill. If this attribute has a mixed value, it will be read as `undefined`. The Text layer can override per-character attribute setting via the All Strokes First or All Fills First setting on the CharPanel. The value returned here represents what is applied to the characters, without regard to the possible Text layer override. |
| strokeWidth | *number* | RW | 27.0 | The Text layer's stroke thickness in pixels. The minimum accepted value to set is 0, but this will be silently clipped to 0.01. |
| subscript | *boolean* | R | 27.0 | `true` if a Text layer has subscript enabled; otherwise `false`. To set this value, use `fontBaselineOption` added in After Effects 24.0. |
| superscript | *boolean* | R | 27.0 | `true` if a Text layer has superscript enabled; otherwise `false`. To set this value, use `fontBaselineOption` added in After Effects 24.0. |
| taggedRanges | *Array* | R | 27.0 | The tagged ranges (each an object with `start`, `end`, and `tag`) that overlap this character range. |
| text | *string* | RW | 27.0 | The text value for the Text layer range. On read, the same number of characters as the span of the range will be returned. If the span is zero (an insertion point) it return an empty string. On write, the characters in the range will be replaced with whatever string value is supplied. If an empty string, then the characters in the range will be effectively deleted. To insert characters without deleting any existing, call TextDocument.characterRange() with the same value for start as end to get an insertion point range. |
| tracking | *number* | RW | 27.0 | The Text layer's spacing between characters. |
| tsume | *number* | RW | 27.0 | This Text layer's tsume value as a normalized percentage, from 0.0 -> 1.0. This attribute accepts values from 0.0 -> 100.0, however the value IS expecting a normalized value from 0.0 -> 1.0. Using a value higher than 1.0 will produce unexpected results; AE's Character Panel will clamp the value at 100%, despite the higher value set by scripting (ie `TextDocument.tsume = 100` really sets a value of 10,000%) |
| verticalScale | *number* | RW | 27.0 | This Text layer's vertical scale in pixels. |


## Instance Methods

### createTaggedRange

Returns: *boolean*

Since: **27.0**

Tags this character range with the given string, creating a new tagged range. Returns `false` if the range is empty (e.g. an insertion point in an empty document).

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| url | *string* | The tag string to apply to this range. |

<HorizontalLine />

### deleteTaggedRanges

Returns: *boolean*

Since: **27.0**

Removes any tagged ranges that overlap this character range.

<HorizontalLine />

### pasteFrom

Returns: *boolean*

Since: **27.0**

Copies, using paste semantics, from the characterRange parameter to the callee CharacterRange object. The two instances may be the same, and the spans may be different. Checks will be made that both CharacterRange object instances are valid. The internal steps of the operation are: Delete the text from the target instance. Paste the text from the source instance. As the span of the CharacterRange object is not adjusted by this call, when the source CharacterRange object instance has a shorter span than the target CharacterRange object instance, the target instance may become invalid.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *object* | Object whose text and styling will be pasted in place of the callee CharacterRange object. |

<HorizontalLine />

### resetCharStyle

Returns: *boolean*

Since: **27.0**

Restores the characters in this range to the default text character characteristics in the Character panel.

<HorizontalLine />

### resetParagraphStyle

Returns: *boolean*

Since: **27.0**

Restores the paragraphs touched by this range to the default text paragraph characteristics in the Paragraph panel.

<HorizontalLine />

### toString

Returns: *string*

Since: **27.0**

Returns a string with the parameters used to create the CharacterRange instance, e.g. "CharacterRange(0,-1)". This may be safely called on an instance where isRangeValid returns `false`.

<HorizontalLine />
