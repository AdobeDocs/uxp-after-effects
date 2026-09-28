---
id: "outputmodule"
title: "OutputModule"
description: "Represents an output module belonging to a render-queue item, used to configure how a render is saved."
sidebar_label: "OutputModule"
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

# OutputModule  

## Properties

| Name | Type | Access | Min Version | Description |
| :------ | :------ | :------ | :------ | :------ |
| file | *string* | RW | 27.0 | The Extendscript File object for the file this output module is set to render. |
| includeSourceXMP | *boolean* | RW | 27.0 | When `true`, writes all source footage XMP metadata to the output file. Corresponds to the Include Source XMP Metadata option in the Output Module Settings dialog box. |
| name | *string* | R | 27.0 | The name of the output module, as shown in the user interface. |
| postRenderAction | *number* | RW | 27.0 | An action to be performed when the render operation is completed. |
| templates | *string[]* | R | 27.0 | The names of all output-module templates available in the local installation of After Effects. |


## Instance Methods

### applyTemplate

Returns: *boolean*

Since: **27.0**

Applies the specified existing output-module template.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *string* | The name of the template to be applied. |

<HorizontalLine />

### getSetting

Returns: *string*

Since: **27.0**

Gets a specific setting for a given Output Module. Suffixing the key with `-str` returns the setting's display string instead of its raw value.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *string* | The name of the setting to retrieve. |

<HorizontalLine />

### getSettings

Returns: *\{ [settingName: string]: string \| number \| boolean \| \{ [key: string]: string \| number } }*

Since: **27.0**

Gets all settings for a given Output Module, as a nested settings object.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *number* | Optional. A `GetSettingsFormat` value controlling whether values are returned as display strings or numbers, and whether only settable keys are included. |

<HorizontalLine />

### normalizeSettings

Returns: *\{ [settingName: string]: string \| number \| boolean \| \{ [key: string]: string \| number } }*

Since: **27.0**

Normalizes an "Output File Info" settings object, collapsing `Base Path`, `Subfolder Path`, and `File Name` into a single `File Template` string that uses tokens like `[fileExtension]`, and returns the normalized settings object.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *Object* | The settings object to normalize, in the same shape returned by `getSettings()`. |

<HorizontalLine />

### remove

Returns: *boolean*

Since: **27.0**

Removes this OutputModule object from the collection. Throws if this is the last output module on its RenderQueueItem, since a render queue item must always have at least one.

<HorizontalLine />

### saveAsTemplate

Returns: *boolean*

Since: **27.0**

Saves this output module as a template and adds it to the templates array.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| templateName | *string* | The name of the new template. |

<HorizontalLine />

### setSetting

Returns: *boolean*

Since: **27.0**

Sets a specific setting for a given Output Module. Returns `true` if the value was applied.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *string* | The name of the setting to change. |
| arg1 | *string* | The new value for the setting. |

<HorizontalLine />

### setSettings

Returns: *boolean*

Since: **27.0**

Sets multiple settings at once for a given Output Module, from a settings object in the same shape returned by `getSettings()`. Returns `true` if the settings were applied.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *Object* | The settings object to apply. |

<HorizontalLine />
