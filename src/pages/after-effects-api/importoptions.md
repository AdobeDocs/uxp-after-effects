---
id: "importoptions"
title: "ImportOptions"
description: "Encapsulates the options used to import a file with Project.importFile()."
sidebar_label: "ImportOptions"
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

# ImportOptions  

## Properties

| Name | Type | Access | Min Version | Description |
| :------ | :------ | :------ | :------ | :------ |
| file | *string* | RW | 27.0 | The file to be imported. If a file is set in the constructor, you can access it through this attribute. |
| forceAlphabetical | *boolean* | RW | 27.0 | When `true`, has the same effect as setting the "Force alphabetical order" option in the File > Import > File dialog box. |
| importAs | *number* | RW | 27.0 | The type of object for which the imported file is to be the source. Use `canImportAs()` to check that a given file can be imported as the source of the given object type before setting. One of `ImportAsType.COMP_CROPPED_LAYERS`, `ImportAsType.FOOTAGE`, `ImportAsType.COMP`, `ImportAsType.PROJECT`. |
| rangeEnd | *number* | RW | 27.0 | Sets the end clipping range of the sequence to be imported. Creates "missing frames" if it exceeds the sequence's duration. Has no effect if `sequence` is `false`. Throws if `forceAlphabetical` is `true`, or if less than `rangeStart` (which also resets the range to include all files). |
| rangeStart | *number* | RW | 27.0 | Sets the start clipping range of the sequence to be imported. Has no effect if `sequence` is `false`. Throws if `forceAlphabetical` is `true`, if `rangeEnd` is 0, or if greater than `rangeEnd` (which also resets the range to include all files). |
| sequence | *boolean* | RW | 27.0 | When `true`, a sequence is imported; otherwise, an individual file is imported. |


## Instance Methods

### canImportAs

Returns: *boolean*

Since: **27.0**

Reports whether the file can be imported as the source of the specified object type. If `true`, that type can be set as `importAs`.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| type | *number* | The `ImportAsType` to test: `COMP`, `FOOTAGE`, `COMP_CROPPED_LAYERS`, or `PROJECT`. |

<HorizontalLine />

### isFileNameNumbered

Returns: *\{ isNumbered: boolean; num: number }*

Since: **27.0**

Reports whether the given file name is numbered (contains a digit). `isNumbered` is `true` if a digit is found; `num` is the number found in the name, or `0` if `isNumbered` is `false`.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| fileName | *string* | The file name (or path) to check for a numbered sequence pattern. |

<HorizontalLine />
