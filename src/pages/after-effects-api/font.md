---
id: "font"
title: "Font"
description: "Provides information about a specific font and the font technology used, helping disambiguate fonts that share a PostScript name."
sidebar_label: "Font"
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

# Font  

## Properties

| Name | Type | Access | Min Version | Description |
| :------ | :------ | :------ | :------ | :------ |
| designVector | *number[]* | R | 27.0 | For Variable fonts will return an ordered array with a length matching the number of design axes defined by the font. Returns `undefined` for non-variable fonts. |
| designVectorIsDefault | *boolean* | R | 27.0 | When `true`, this Font instance represents the default design-vector instance of a variable font. When `false`, it represents a non-default named instance sharing the same font dictionary. `undefined` for non-variable fonts. |
| familyName | *string* | R | 27.0 | The family name of the font, in the ASCII character set. |
| familyPrefix | *string* | R | 27.0 | The family prefix of the variable font. For example, the family of the PostScript name "SFPro-Bold" is "SFPro". Returns `undefined` for non-variable fonts. |
| fontID | *number* | R | 27.0 | A unique number assigned to the Font instance when it is created, greater than or equal to 1. It never changes during the application session but may differ across subsequent launches. Can be used to compare two Font instances to see if they refer to the same underlying native font instance. |
| fullName | *string* | R | 27.0 | The full name of the font, in the ASCII character set. Usually composed of the family name and the style name. |
| hasDesignAxes | *boolean* | R | 27.0 | When `true`, the font is a variable font. |
| isFromAdobeFonts | *boolean* | R | 27.0 | When `true`, the font is from Adobe Fonts. |
| isSubstitute | *boolean* | R | 27.0 | When `true`, this font instance represents a font reference which was missing on project open. |
| location | *string* | R | 27.0 | The location of the font file on your system. Not guaranteed to be returned for all font types; may be an empty string for some kinds of fonts. |
| nativeFamilyName | *string* | R | 27.0 | The native family name of the font in full 16-bit Unicode. Often different than `familyName` for non-Latin fonts. |
| nativeFullName | *string* | R | 27.0 | The native full name of the font in full 16-bit Unicode. Often different than `fullName` for non-Latin fonts. |
| nativeStyleName | *string* | R | 27.0 | The native style name of the font in full 16-bit Unicode. Often different than `styleName` for non-Latin fonts. |
| otherFontsWithSameDict | *Array* | R | 27.0 | Returns an array of Font instances which share the same font dictionary as this Font. Returns an empty array if this Font is not a variable font, or the variable font only has one instance. |
| postScriptName | *string* | R | 27.0 | The postscript name of the font. |
| styleName | *string* | R | 27.0 | The style name of the font, in the ASCII character set. |
| technology | *number* | R | 27.0 | The technology used by the font. |
| type | *number* | R | 27.0 | The internal type of the font. |
| version | *string* | R | 27.0 | The version number of the font. |
| writingScripts | *number[]* | R | 27.0 | The supported character sets of the font. |
| designAxesData | *\{ min: number; max: number; default: number; name: string; tag: string }[] \| undefined* | R | 27.0 | Returns an array of objects containing the design axes data from the font. Each object is composed of the axis name, tag, min value, max value, and default value. Returns `undefined` for non-variable fonts. |


## Instance Methods

### hasGlyphsFor

Returns: *boolean*

Since: **27.0**

Fonts do not contain glyphs for all possible ranges of Unicode - this method lets the caller query the Font for support of one or more characters. Returns `true` if the font has a glyph for every character in the given string. Character order does not matter, and for a multi-character string it's not possible to determine which character had no glyph support.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *string* | Text that will be checked for support in the Font object. |

<HorizontalLine />

### hasSameDict

Returns: *boolean*

Since: **27.0**

Returns `true` if the Font object passed as an argument shares the same variable font dictionary as the Font this is called on. Can only return `true` when called on a variable Font with the argument also being a variable Font.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *object* | The Font object to check. |

<HorizontalLine />

### postScriptNameForDesignVector

Returns: *string*

Since: **27.0**

Returns the postscript name of the variable font for the specific design vector passed as the argument.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| designVector | *number[]* | An array of design-axis values, matching the length of `designAxesData`, to check against this font's `designVector`. |

<HorizontalLine />
