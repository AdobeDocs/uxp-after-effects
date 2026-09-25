---
id: "textdocument"
title: "TextDocument"
description: "Represents the text and formatting in a Text layer's Source Text property."
sidebar_label: "TextDocument"
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

# TextDocument  

## Properties

| Name | Type | Access | Min Version | Description |
| :------ | :------ | :------ | :------ | :------ |
| allCaps | *boolean* | R | 27.0 | `true` if a Text layer has All Caps enabled; otherwise `false`. To set this value, use `fontCapsOption`. Only reflects the first character in the Text layer. |
| applyFill | *boolean* | RW | 27.0 | When `true`, the Text layer shows a fill. Access `fillColor` for the actual color. When `false`, only a stroke is shown. |
| applyStroke | *boolean* | RW | 27.0 | When `true`, the Text layer shows a stroke. Access `strokeColor` for the actual color and `strokeWidth` for its thickness. When `false`, only a fill is shown. |
| autoHyphenate | *boolean* | RW | 27.0 | The Text layer's auto hyphenate paragraph option. Reflects and sets all paragraphs in the Text layer. |
| autoKernType | *number* | RW | 27.0 | The Text layer's auto kern type option. One of `AutoKernType.NO_AUTO_KERN`, `AutoKernType.METRIC_KERN`, `AutoKernType.OPTICAL_KERN`. Only reflects the first character; setting it applies to all characters. |
| autoLeading | *boolean* | RW | 27.0 | The Text layer's auto leading character option. Reflects and sets all paragraphs in the Text layer. |
| baselineDirection | *number* | RW | 27.0 | The Text layer's baseline direction option, significant for Japanese vertical text. One of `BaselineDirection.BASELINE_WITH_STREAM`, `BaselineDirection.BASELINE_VERTICAL_ROTATED`, `BaselineDirection.BASELINE_VERTICAL_CROSS_STREAM`. Only reflects the first character; setting it applies to all characters. |
| baselineLocs | *number[]* | R | 27.0 | The baseline (x,y) locations for a Text layer, as a flat array of `[line.start_x, line.start_y, line.end_x, line.end_y, ...]` values per composed line. If a line has no characters, its x/y values are the maximum float value. |
| baselineShift | *number* | RW | 27.0 | The Text layer's baseline shift in pixels. Only reflects the first character; setting it applies to all characters. |
| boxAutoFitPolicy | *number* | RW | 27.0 | Enables automated change of the box height to fit the text content; the box only grows down. Defaults to `BoxAutoFitPolicy.NONE`. Disabled if `boxVerticalAlignment` is anything other than `BoxVerticalAlignment.TOP`. |
| boxFirstBaselineAlignment | *number* | RW | 27.0 | Controls the position of the first line of composed text relative to the top of the box. Disabled if `boxFirstBaselineAlignmentMinimum` is non-zero. Defaults to `BoxFirstBaselineAlignment.ASCENT`. |
| boxFirstBaselineAlignmentMinimum | *number* | RW | 27.0 | Manually controls the position of the first line of composed text relative to the top of the box, overriding `boxFirstBaselineAlignment` when non-zero. Defaults to zero. |
| boxInsetSpacing | *number* | RW | 27.0 | The inner space between the box bounds and where the composable text box begins, applied to all four sides. Defaults to zero. |
| boxOverflow | *boolean* | R | 27.0 | `true` if some part of the text did not compose into the box. |
| boxText | *boolean* | R | 27.0 | `true` if a Text layer is a layer of paragraph (bounded) text; otherwise `false`. |
| boxTextPos | *number[]* | RW | 27.0 | The layer coordinates from a paragraph (box) Text layer's anchor point, as a `[width, height]` array of pixel dimensions. Throws an exception if `boxText` is not `true`. |
| boxTextSize | *number[]* | RW | 27.0 | The size of a paragraph (box) Text layer, as a `[width, height]` array of pixel dimensions (minimum value of 1). Throws an exception if `boxText` is not `true`. |
| boxVerticalAlignment | *number* | RW | 27.0 | Enables automated vertical alignment of the composed text in the box. Defaults to `BoxVerticalAlignment.TOP`. |
| composedLineCount | *number* | R | 27.0 | The number of composed lines in the Text layer; may be zero if all text is overset. Reflects the composed state when this TextDocument was initialized; not updated by subsequent changes. |
| composerEngine | *number* | RW | 27.0 | The Text layer's paragraph composer engine option. Defaults to `ComposerEngine.UNIVERSAL_TYPE_ENGINE` for new layers; `ComposerEngine.LATIN_CJK_ENGINE` only appears in older projects and can't be set back to. Reflects and sets all paragraphs in the Text layer. |
| digitSet | *number* | RW | 27.0 | The Text layer's digit set option. One of `DigitSet.DEFAULT_DIGITS`, `DigitSet.ARABIC_DIGITS`, `DigitSet.HINDI_DIGITS`, `DigitSet.FARSI_DIGITS`, `DigitSet.ARABIC_DIGITS_RTL`. Only reflects the first character; setting it applies to all characters. |
| direction | *number* | RW | 27.0 | The Text layer's paragraph direction option. One of `ParagraphDirection.DIRECTION_LEFT_TO_RIGHT`, `ParagraphDirection.DIRECTION_RIGHT_TO_LEFT`. Reflects and sets all paragraphs in the Text layer. |
| endIndent | *number* | RW | 27.0 | The Text layer's paragraph end indent option. Reflects and sets all paragraphs in the Text layer. |
| everyLineComposer | *boolean* | RW | 27.0 | The Text layer's Every-Line Composer paragraph option; if `false`, uses the Single-Line Composer instead. Reflects and sets all paragraphs in the Text layer. |
| fauxBold | *boolean* | R | 27.0 | `true` if a Text layer has faux bold enabled; otherwise `false`. Only reflects the first character in the Text layer. |
| fauxItalic | *boolean* | R | 27.0 | `true` if a Text layer has faux italic enabled; otherwise `false`. Only reflects the first character in the Text layer. |
| fillColor | *number[]* | RW | 27.0 | The Text layer's fill color, as `[r, g, b]` floating-point values (values above 1.0 possible in 32-bpc projects). Throws an exception on read if `applyFill` is not `true`. Setting this also sets `applyFill` to `true`. Only reflects the first character; setting it applies to all characters. |
| firstLineIndent | *number* | RW | 27.0 | The Text layer's paragraph first line indent option. Reflects and sets all paragraphs in the Text layer. |
| font | *string* | RW | 27.0 | The Text layer's font, specified by its PostScript name. On write, a substitute Font instance is created if no match exists for the supplied name. Only reflects the first character; setting it applies to all characters. |
| fontBaselineOption | *number* | RW | 27.0 | The Text layer's font baseline option, for setting superscript or subscript. One of `FontBaselineOption.FONT_NORMAL_BASELINE`, `FontBaselineOption.FONT_FAUXED_SUPERSCRIPT`, `FontBaselineOption.FONT_FAUXED_SUBSCRIPT`. Only reflects the first character; setting it applies to all characters. |
| fontCapsOption | *number* | RW | 27.0 | The Text layer's font caps option. One of `FontCapsOption.FONT_NORMAL_CAPS`, `FontCapsOption.FONT_SMALL_CAPS`, `FontCapsOption.FONT_ALL_CAPS`, `FontCapsOption.FONT_ALL_SMALL_CAPS`. Only reflects the first character; setting it applies to all characters. |
| fontFamily | *string* | R | 27.0 | The name of the font family. Only reflects the first character in the Text layer. |
| fontLocation | *string* | R | 27.0 | The path of the font file, providing its location on disk. Not guaranteed to be returned for all font types; may be an empty string. Only reflects the first character in the Text layer. |
| fontObject | *Font* | RW | 27.0 | The Text layer's Font object, specified by its PostScript name. Only reflects the first character in the Text layer. |
| fontSize | *number* | RW | 27.0 | The Text layer's font size in pixels, from 0.1 to 1296. Only reflects the first character; setting it applies to all characters. |
| fontStyle | *string* | R | 27.0 | String with style information, e.g. "bold", "italic". Only reflects the first character in the Text layer. |
| hangingRoman | *boolean* | RW | 27.0 | The Text layer's Roman Hanging Punctuation paragraph option; meaningful only for box Text layers, letting punctuation fit outside the box instead of flowing to the next line. Reflects and sets all paragraphs in the Text layer. |
| horizontalScale | *number* | RW | 27.0 | The Text layer's horizontal scale in pixels. Only reflects the first character; setting it applies to all characters. |
| justification | *number* | RW | 27.0 | The paragraph justification for the Text layer. A `ParagraphJustification` enumerated value. Mixed values are read as `ParagraphJustification.MULTIPLE_JUSTIFICATIONS`; setting that value results in `CENTER_JUSTIFY` instead. Reflects and sets all paragraphs in the Text layer. |
| kerning | *number* | RW | 27.0 | The Text layer's kerning option. Returns zero for `AutoKernType.METRIC_KERN` and `AutoKernType.OPTICAL_KERN`. Setting this also sets `AutoKernType.NO_AUTO_KERN`. Only reflects the first character; setting it applies to all characters. |
| leading | *number* | RW | 27.0 | The Text layer's spacing between lines. Returns zero if `autoLeading` is `true`. Setting this also sets `autoLeading` to `true`. Minimum settable value is 0 (silently clipped to 0.01). Only reflects the first character; setting it applies to all characters. |
| leadingType | *number* | RW | 27.0 | The Text layer's paragraph leading type option. One of `LeadingType.ROMAN_LEADING_TYPE`, `LeadingType.JAPANESE_LEADING_TYPE`. Reflects and sets all paragraphs in the Text layer. |
| ligature | *boolean* | RW | 27.0 | The Text layer's ligature option. Only reflects the first character; setting it applies to all characters. |
| lineJoinType | *number* | RW | 27.0 | The Text layer's line join type option for Stroke. One of `LineJoinType.LINE_JOIN_MITER`, `LineJoinType.LINE_JOIN_ROUND`, `LineJoinType.LINE_JOIN_BEVEL`. Only reflects the first character; setting it applies to all characters. |
| lineOrientation | *number* | RW | 27.0 | The Text layer's line orientation (horizontal vs. vertical), affecting how all text in the layer is composed. One of `LineOrientation.HORIZONTAL`, `LineOrientation.VERTICAL_RIGHT_TO_LEFT`, `LineOrientation.VERTICAL_LEFT_TO_RIGHT`. |
| noBreak | *boolean* | RW | 27.0 | The Text layer's no break attribute. Only reflects the first character; setting it applies to all characters. |
| paragraphCount | *number* | R | 27.0 | The number of paragraphs in the Text layer; always greater than or equal to 1. |
| pointText | *boolean* | R | 27.0 | `true` if a Text layer is a layer of point (unbounded) text; otherwise `false`. |
| smallCaps | *boolean* | R | 27.0 | `true` if a Text layer has small caps enabled; otherwise `false`. To set this value, use `fontCapsOption`. Only reflects the first character in the Text layer. |
| spaceAfter | *number* | RW | 27.0 | The Text layer's paragraph space after option. Reflects and sets all paragraphs in the Text layer. |
| spaceBefore | *number* | RW | 27.0 | The Text layer's paragraph space before option. Reflects and sets all paragraphs in the Text layer. |
| startIndent | *number* | RW | 27.0 | The Text layer's paragraph start indent option. Reflects and sets all paragraphs in the Text layer. |
| strokeColor | *number[]* | RW | 27.0 | The Text layer's stroke color, as `[r, g, b]` floating-point values. Throws an exception on read if `applyStroke` is not `true`. Setting this also sets `applyStroke` to `true`. Only reflects the first character; setting it applies to all characters. |
| strokeOverFill | *boolean* | RW | 27.0 | When `true`, the stroke appears over the fill for a Text layer. The layer's Character Panel render-order setting can override the per-character value returned here. Only reflects the first character; setting it applies to all characters. |
| strokeWidth | *number* | RW | 27.0 | The Text layer's stroke thickness in pixels, from 0 to 1000 (minimum settable value is 0, silently clipped to 0.01). Only reflects the first character; setting it applies to all characters. |
| subscript | *boolean* | R | 27.0 | `true` if a Text layer has subscript enabled; otherwise `false`. To set this value, use `fontBaselineOption`. Only reflects the first character in the Text layer. |
| superscript | *boolean* | R | 27.0 | `true` if a Text layer has superscript enabled; otherwise `false`. To set this value, use `fontBaselineOption`. Only reflects the first character in the Text layer. |
| text | *string* | RW | 27.0 | The text value for the Text layer's Source Text property. |
| tracking | *number* | RW | 27.0 | The Text layer's spacing between characters. Only reflects the first character; setting it applies to all characters. |
| tsume | *number* | RW | 27.0 | This Text layer's tsume value as a normalized percentage, from 0.0 to 1.0. Values above 1.0 (up to 100.0) are accepted but produce unexpected results, since AE's Character Panel clamps display at 100% despite the higher scripted value. Only reflects the first character; setting it applies to all characters. |
| verticalScale | *number* | RW | 27.0 | This Text layer's vertical scale in pixels. Only reflects the first character; setting it applies to all characters. |


## Instance Methods

### characterRange

Returns: *CharacterRange*

Since: **27.0**

Returns an instance of the Text layer range accessor CharacterRange. The instance remembers the constructor parameters; they remain constant, and changes to the TextDocument's length may cause it to throw exceptions on access until the length changes back to a value that makes the range valid again. Use `toString()` on the result to find the constructed parameters.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| characterStart | *number* | Starts at zero; must be less than or equal to the (text) length of the TextDocument. |
| signedCharacterIndexEnd | *number* | Optional. Defaults to `characterStart + 1`. If `-1`, dynamically calculated as the TextDocument's text length on access. Must be greater than or equal to `characterStart` and less than or equal to the TextDocument's length. |

<HorizontalLine />

### composedLineCharacterIndexesAt

Returns: *\{ start: number; end: number }*

Since: **27.0**

Returns the character index bounds of the composed line intersecting the given text index. `start` is the composed line's start text index (greater than or equal to zero); `end` is its end index (greater than `start`, or equal to `start` if it's the last line). Throws if the computed bounds fall outside the current TextDocument.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| at | *number* | A text index in the Text layer, mapped to the composed line it intersects. |

<HorizontalLine />

### composedLineRange

Returns: *ComposedLineRange*

Since: **27.0**

Returns an instance of the Text layer range accessor ComposedLineRange. The instance remembers the constructor parameters; they remain constant, and changes to the TextDocument's contents may cause it to throw exceptions on access until the contents change back to a value that makes the range valid again. Use `toString()` on the result to find the constructed parameters.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| composedLineIndexStart | *number* | Starts at zero; must be less than the number of composed lines in the TextDocument. |
| signedLineIndexEnd | *number* | Optional. Defaults to `composedLineIndexStart + 1`. If `-1`, dynamically calculated as the last composed line on access. Must be greater than `composedLineIndexStart` and less than or equal to the number of composed lines. |

<HorizontalLine />

### paragraphCharacterIndexesAt

Returns: *\{ start: number; end: number }*

Since: **27.0**

Returns the character index bounds of the paragraph intersecting the given text index. `start` is the paragraph's start text index (greater than or equal to zero); `end` is its end index (greater than `start`, or equal to `start` if it's the last paragraph).

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| at | *number* | A text index in the Text layer, mapped to the paragraph it intersects. |

<HorizontalLine />

### paragraphRange

Returns: *ParagraphRange*

Since: **27.0**

Returns an instance of the Text layer range accessor ParagraphRange. The instance remembers the constructor parameters; they remain constant, and changes to the TextDocument's contents may cause it to throw exceptions on access until the contents change back to a value that makes the range valid again. Use `toString()` on the result to find the constructed parameters.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| paragraphIndexStart | *number* | Starts at zero; must be less than the number of paragraphs in the TextDocument. |
| signedParagraphIndexEnd | *number* | Optional. Defaults to `paragraphIndexStart + 1`. If `-1`, dynamically calculated as the last paragraph on access. Must be greater than `paragraphIndexStart` and less than or equal to the number of paragraphs. |

<HorizontalLine />

### resetCharStyle

Returns: *boolean*

Since: **27.0**

Restores all characters in the Text layer to the default text character characteristics in the Character panel.

<HorizontalLine />

### resetParagraphStyle

Returns: *boolean*

Since: **27.0**

Restores all paragraphs in the Text layer to the default text paragraph characteristics in the Paragraph panel.

<HorizontalLine />

### toString

Returns: *string*

Since: **27.0**

<HorizontalLine />
