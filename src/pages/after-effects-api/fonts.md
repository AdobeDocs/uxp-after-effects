---
id: "fonts"
title: "Fonts"
description: "Provides information about the current font ecosystem on the user's device."
sidebar_label: "Fonts"
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

# Fonts  

## Properties

| Name | Type | Access | Min Version | Description |
| :------ | :------ | :------ | :------ | :------ |
| allFonts | *Array* | R | 27.0 | The list of all the fonts currently available on your system, grouped into family groups (each an array of Font objects). Fonts for which `isSubstitute` returns `true` are always sorted to the end as individual family groups. |
| favoriteFontFamilyList | *string[]* | RW | 27.0 | Provides access to the Favorites list presented in the Character panel and Properties panel. To set the Favorites, provide an (unsorted) array of strings based on `familyName`. To clear the list, assign an empty array. |
| fontServerRevision | *number* | R | 27.0 | Returns an unsigned number representing the current revision of the font environment. The revision is advanced when anything changes the contents, properties, or order of Font objects returned by `allFonts`. |
| fontsDuplicateByPostScriptName | *Array* | R | 27.0 | Reveals which Font objects share the same `postScriptName` and their relative order. Returns an array in which each element is an array of Font objects, where the 0th element is considered the primary Font object for that PostScript name. |
| fontsWithDefaultDesignAxes | *Array* | R | 27.0 | Returns an array of variable Font objects, each using a unique font dictionary and with default values for their design axes. A convenient way to quickly filter for a unique instance of each installed variable font. |
| freezeSyncSubstitutedFonts | *boolean* | RW | 27.0 | When a project is opened with fonts missing locally, After Effects automatically attempts to sync and install matches from Adobe Fonts. Setting this to `true` disables that sync/install attempt. |
| missingOrSubstitutedFonts | *Array* | R | 27.0 | The list of all the missing or substituted fonts of the current project. |
| mruFontFamilyList | *string[]* | RW | 27.0 | Provides access to the Most Recently Used (MRU) list presented in the Character panel and Properties panel. To set the MRU, provide an (unsorted) array of strings based on `familyName`. To clear the list, assign an empty array. |
| substitutedFontReplacementMatchPolicy | *number* | RW | 27.0 | Controls the rules used to determine which fonts are considered matching for automatic replacement of a substituted Font object. |
| otvLookupTable | *\{ prefix: string; values: string[] }[] \| undefined* | R | 27.0 | An internal lookup table used to identify related variable-font naming, returned as an array of objects with a `prefix` string and a `values` array of related strings for that prefix. |


## Instance Methods

### findFirstFontByFamilyNameAndStyleNameWithFallback

Returns: *\{ font: Font; matched: boolean }*

Since: **27.0**

Looks up a font by family name and style name, always returning a `{ font, matched }` object. `matched` is `true` if an exact match was found; `font` is populated with a fallback Font even when `matched` is `false`.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| familyName | *string* | The family name to look up. |
| styleName | *string* | The style name to look up. |

<HorizontalLine />

### getCTScriptForString

Returns: *\{ ctScript: number; chars: number }[]*

Since: **27.0**

Returns an array of objects describing how many characters in the given string fall under each CTScript value. If a character could belong to more than one CTScript, `preferredCTScript` breaks the tie. Returns an empty array if `charString` is empty.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| str | *string* | Characters to check. If empty, returns an empty array. |
| script | *number* | The CTScript to prefer when a character could belong to more than one. |

<HorizontalLine />

### getDefaultFontForCTScript

Returns: *Font*

Since: **27.0**

Returns the Font instance mapped as the default font for the given CTScript. After Effects uses this mapping when a font is missing a glyph for a typed character, mapping the character to a CTScript value and using this default to pick an alternate font. There's no guarantee the returned font supports any of the Unicode characters mapped to that CTScript.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *number* | The CTScript to get the default font for. |

<HorizontalLine />

### getFontByID

Returns: *Font*

Since: **27.0**

Returns the Font instance matching a previously found font's ID. Returns `undefined` if no matching font is found (e.g. an unknown ID, or the original font was removed from the font environment).

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *number* | The ID of the font. |

<HorizontalLine />

### getFontsByFamilyNameAndStyleName

Returns: *Array*

Since: **27.0**

Returns an array of Font objects matching the given family name and style name. Returns an empty array if no suitable font is found. The array can have more than one entry if multiple copies of the same font are installed.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *string* | The family name of the font. |
| arg1 | *string* | The style name of the font. |

<HorizontalLine />

### getFontsByPostScriptName

Returns: *Array*

Since: **27.0**

Returns an array of Font objects matching the given PostScript name. The entry at index 0 is used when setting `TextDocument.fontObject`. Returns an empty array if no matching font is found.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *string* | The PostScript name of the font. |

<HorizontalLine />

### pollForAndPushNonSystemFontFoldersChanges

Returns: *boolean*

Since: **27.0**

Triggers a check against the known non-system font folders (unlike system font folders, these aren't watched automatically) and schedules an asynchronous font-environment update if a change is detected. Returns `true` if a change was detected and an update was scheduled, `false` otherwise.

<HorizontalLine />

### setDefaultFontForCTScript

Returns: *boolean*

Since: **27.0**

Sets the Font instance mapped as the default font for the given CTScript. Variable fonts aren't acceptable as defaults and throw an exception. Pass `null` for `font` to reset the mapping back to its value at app launch. Returns `true` if the mapping changed, `false` if it was already set to the given value.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *number* | The CTScript to map the font to. |
| font | *object* | The font to map. If `null`, resets the mapping to its value at app launch. |

<HorizontalLine />
