---
id: "project"
title: Project
sidebar_label: "Project"
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

# Project  

## Properties

| Name | Type | Access | Min Version | Description |
| :------ | :------ | :------ | :------ | :------ |
| activeItem | *Item \| null* | R | 27.0 | The item that is currently active and is to be acted upon, or `null` if no item is currently selected or if multiple items are selected. |
| bitsPerChannel | *number* | RW | 27.0 | The color depth of the current project: 8, 16, or 32 bits. |
| colorManagementSystem | *number* | RW | 27.0 | The project's color management system. One of: `0` (Adobe's built-in color management), `1` (OCIO, OpenColor IO). |
| compensateForSceneReferredProfiles | *boolean* | RW | 27.0 | `true` if Compensate for Scene-referred Profiles should be enabled for this project; otherwise `false`. |
| displayStartFrame | *number* | RW | 27.0 | An alternate way of setting the Frame Count menu setting in the Project Settings dialog box to 0 or 1, equivalent to using `FramesCountType.FC_START_0`/`FC_START_1` for `framesCountType`. |
| expressionEngine | *string* | RW | 27.0 | The Expressions Engine setting in the Project Settings dialog box, as a string. One of `extendscript` or `javascript-1.0`. |
| feetFramesFilmType | *number* | RW | 27.0 | The Use Feet + Frames menu setting in the Project Settings dialog box. |
| file | *string* | R | 27.0 | The absolute file path of the file containing the project that is currently open, or an empty string if the project has not been saved. |
| footageTimecodeDisplayStartType | *number* | RW | 27.0 | The Footage Start Time setting in the Project Settings dialog box, enabled when Timecode is selected as the time display style. |
| framesCountType | *number* | RW | 27.0 | The Frame Count menu setting in the Project Settings dialog box. Setting this to the timecode-conversion value resets `displayStartFrame` to 0. |
| framesUseFeetFrames | *boolean* | RW | 27.0 | The Use Feet + Frames setting in the Project Settings dialog box. `true` if using Feet + Frames; `false` if using Frames. |
| gpuAccelType | *number* | RW | 27.0 | Gets or sets the current project's GPU Acceleration option (Project Settings > Video Rendering and Effects > Use). |
| items | *ItemCollection* | R | 27.0 | All of the items in the project. |
| linearBlending | *boolean* | RW | 27.0 | `true` if linear blending should be used for this project; otherwise `false`. |
| linearizeWorkingSpace | *boolean* | RW | 27.0 | `true` if Linearize Working Space should be enabled for this project; otherwise `false`. |
| lutInterpolationMethod | *number* | RW | 27.0 | The 3D LUT interpolation algorithm used for color management. One of: `0` (Trilinear), `1` (Tetrahedral). |
| ocioConfigurationFile | *string* | RW | 27.0 | The path to the OCIO (OpenColor IO) configuration file used when `colorManagementSystem` is set to OCIO. Empty string if none is set. |
| renderQueue | *RenderQueue* | R | 27.0 | The Render Queue of the project. |
| revision | *number* | R | 27.0 | The current revision of the project. Every user action increases the revision number; a new project starts at revision 1. |
| rootFolder | *FolderItem* | R | 27.0 | The root folder containing the contents of the project; a virtual folder containing all items in the Project panel, but not items nested inside other folders. |
| selection | *Array* | R | 27.0 | All items selected in the Project panel, in the sort order shown in the Project panel. |
| telemetryGuid | *Guid* | R | 27.0 | A stable, GUID-formatted identifier associated with the project, used for telemetry purposes. |
| timeDisplayType | *number* | RW | 27.0 | The time display style, corresponding to the Time Display Style section in the Project Settings dialog box. |
| toolType | *number* | RW | 27.0 | Gets and sets the active tool in the Tools panel. |
| transparencyGridThumbnails | *boolean* | RW | 27.0 | When `true`, thumbnail views use the transparency checkerboard pattern. |
| workingGamma | *number* | RW | 27.0 | The current project's working gamma value, either 2.2 or 2.4. Setting any other value causes a scripting error. Ignored by After Effects when the project's color working space is set. |
| workingSpace | *string* | RW | 27.0 | The color profile description for the project's color working space. Set to an empty string to use None. Use `listColorProfiles()` to get valid values. |
| xmpPacket | *string* | RW | 27.0 | The project's XMP metadata, stored as RDF (XML-based). |
| dirty | *boolean* | R | 27.0 | `true` if the project has been modified since the last save; otherwise `false`. |
| numItems | *number* | R | 27.0 | The total number of items contained in the project, including folders and all types of footage. |
| textSelection | *\{ layerID: number; layerTimeD: number; start: number; end: number } \| undefined* | R | 27.0 | The current text selection, as an object giving the layerID and layerTimeD of the selected text layer along with the start and end character offsets of the selection, or `undefined` if there is no text selection. There is no way to set the text selection via scripting; this is read-only. |
| usedFonts | *\{ font: Font; usedAt: \{ layerID: number; layerTimeD: number }[] }[]* | R | 27.0 | An array of objects containing references to fonts used in the current project and the Text layers and times on which they appear. Each object is composed of `font`, a Font object, and `usedAt`, an array of objects each composed of `layerID` (a Layer's `id`) and `layerTimeD` (the time, in Layer Time, at which the font is used). Use `layerByID()` to retrieve the layers. |


## Instance Methods

### autoFixExpressions

Returns: *boolean*

Since: **27.0**

Automatically replaces text found in broken expressions in the project, if the new text causes the expression to evaluate without errors.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| oldText | *string* | The text to replace. |
| newText | *string* | The new text. |

<HorizontalLine />

### close

Returns: *boolean*

Since: **27.0**

Closes the project, with the option to save changes automatically, prompt the user to save, or close without saving. Returns `true` on success; `false` if the file has never been saved, the user is prompted, and cancels.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| closeOptions | *number* | Action to perform on close: `CloseOptions.DO_NOT_SAVE_CHANGES`, `CloseOptions.PROMPT_TO_SAVE_CHANGES`, or `CloseOptions.SAVE_CHANGES`. |

<HorizontalLine />

### closeTeamProject

Returns: *boolean*

Since: **27.0**

Closes a currently open team project. `true` if successfully closed.

<HorizontalLine />

### consolidateFootage

Returns: *number*

Since: **27.0**

Consolidates all footage in the project (same as File > Consolidate All Footage). Returns the total number of footage items removed.

<HorizontalLine />

### convertTeamProjectToProject

Returns: *boolean*

Since: **27.0**

Converts a team project to an After Effects project on local disk. `true` if successfully converted.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| projectFile | *string* | The local After Effects project file path. Extension should be `.aep` or `.aet` (`.aepx` not supported). |

<HorizontalLine />

### importFile

Returns: *FootageItem*

Since: **27.0**

Imports the file specified in the specified ImportOptions object, using the specified options (same as the File > Import File command). Creates and returns a new FootageItem object from the file, and adds it to the project's items array.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| importOptions | *object* | Options specifying the file to import and the options for the operation. |

<HorizontalLine />

### importFileWithDialog

Returns: *Array*

Since: **27.0**

Shows an Import File dialog box (same as File > Import > File). Returns an array of Item objects created during import, or `null` if the user cancels the dialog box.

<HorizontalLine />

### importPlaceholder

Returns: *FootageItem*

Since: **27.0**

Creates and returns a new PlaceholderItem, adding it to the project's items array (same as File > Import > Placeholder).

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| name | *string* | The name of the placeholder. |
| width | *number* | The width of the placeholder in pixels, in the range `[4..30000]`. |
| height | *number* | The height of the placeholder in pixels, in the range `[4..30000]`. |
| frameRate | *number* | The frame rate of the placeholder, in the range `[1.0..99.0]`. |
| duration | *number* | The duration of the placeholder in seconds, in the range `[0.0..10800.0]`. |

<HorizontalLine />

### isAnyTeamProjectOpen

Returns: *boolean*

Since: **27.0**

`true` if any team project is currently open.

<HorizontalLine />

### isLoggedInToTeamProject

Returns: *boolean*

Since: **27.0**

`true` if After Effects is currently logged into the team project server.

<HorizontalLine />

### isResolveCommandEnabled

Returns: *boolean*

Since: **27.0**

`true` if the team projects Resolve command is enabled.

<HorizontalLine />

### isShareCommandEnabled

Returns: *boolean*

Since: **27.0**

`true` if the team projects Share command is enabled.

<HorizontalLine />

### isSyncCommandEnabled

Returns: *boolean*

Since: **27.0**

`true` if the team projects Sync command is enabled.

<HorizontalLine />

### isTeamProjectEnabled

Returns: *boolean*

Since: **27.0**

`true` if team projects are enabled for After Effects (almost always `true`).

<HorizontalLine />

### isTeamProjectOpen

Returns: *boolean*

Since: **27.0**

Checks whether the specified team project is currently open.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| productionName | *string* | The team project name. |

<HorizontalLine />

### item

Returns: *Item*

Since: **27.0**

Retrieves an item at a specified index position; the first item is at index 1.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| index | *number* | The index position of the item. The first item is at index 1. |

<HorizontalLine />

### itemByID

Returns: *Item*

Since: **27.0**

Retrieves an item by its Item ID.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| id | *number* | The ID of an item. |

<HorizontalLine />

### layerByID

Returns: *Layer*

Since: **27.0**

Returns the Layer with the given ID in the project, or `null` if none exists. Non-valid IDs throw an exception.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| id | *number* | The ID of the Layer to retrieve from the project (non-negative integer). |

<HorizontalLine />

### listColorProfiles

Returns: *string[]*

Since: **27.0**

Returns an array of color profile descriptions that can be set as the project's color working space.

<HorizontalLine />

### listTeamProjects

Returns: *string[]*

Since: **27.0**

Returns an array of the name strings for all team projects available for the current user. Archived team projects are not included.

<HorizontalLine />

### newTeamProject

Returns: *boolean*

Since: **27.0**

Creates a new team project. `true` if successfully created.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| teamProjectName | *string* | The team project name. |
| description | *string* | Optional. The project description. |

<HorizontalLine />

### openTeamProject

Returns: *boolean*

Since: **27.0**

Opens a team project. `true` if successfully opened.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| teamProjectName | *string* | The team project name. |

<HorizontalLine />

### reduceProject

Returns: *number*

Since: **27.0**

Removes all items from the project except those specified (same as File > Reduce Project). Returns the total number of items removed.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| items | *Item* or *Item[]* | The items to keep; all others are removed. |

<HorizontalLine />

### removeUnusedFootage

Returns: *number*

Since: **27.0**

Removes unused footage from the project (same as File > Remove Unused Footage). Returns the total number of FootageItem objects removed.

<HorizontalLine />

### replaceFont

Returns: *void*

Since: **27.0**

Replaces all usages of the `fromFont` Font object with the `toFont` Font object throughout the project, including on TextDocuments with mixed styling. This operation is not undoable.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| fromFont | [*Font*](/ae_reference/classes/font.md) | The Font to be replaced. |
| toFont | [*Font*](/ae_reference/classes/font.md) | The Font to replace it with. |
| noFontLocking | *boolean* | Optional, defaults to `false`. By default, a fallback font with the necessary glyphs is substituted if `toFont` is missing glyphs for the affected text. Set to `true` to disable this fallback, which may result in missing glyphs. |

<HorizontalLine />

### resolveConflict

Returns: *boolean*

Since: **27.0**

Resolves a conflict between the open team project and the server version, using the specified resolution method. `true` if successful.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| resolveType | *number* | The conflict resolution method: `ResolveType.ACCEPT_THEIRS`, `ResolveType.ACCEPT_YOURS`, or `ResolveType.ACCEPT_THEIRS_AND_COPY`. |

<HorizontalLine />

### save

Returns: *boolean*

Since: **27.0**

Saves the project (same as File > Save or File > Save As). If never previously saved and no file is given, prompts the user for a location and name.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| file | *string* | Optional. The file path to save to. If omitted and never previously saved, the user is prompted. |

<HorizontalLine />

### saveWithDialog

Returns: *boolean*

Since: **27.0**

Shows the Save dialog box; the user names a file/location and saves, or cancels. `true` if the project was saved.

<HorizontalLine />

### setDefaultImportFolder

Returns: *boolean*

Since: **27.0**

Sets the folder shown in the file import dialog, as an override until called with no argument or After Effects quits. `true` if successful.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| folder | *string* | The folder path to set as the default import location. |

<HorizontalLine />

### shareTeamProject

Returns: *boolean*

Since: **27.0**

Shares the currently open team project. `true` if successfully shared.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| comment | *string* | Optional. A comment for the share. |

<HorizontalLine />

### showWindow

Returns: *boolean*

Since: **27.0**

Shows or hides the Project panel.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| doShow | *boolean* | When `true`, shows the Project panel; when `false`, hides it. |

<HorizontalLine />

### syncTeamProject

Returns: *boolean*

Since: **27.0**

Syncs the currently open team project. `true` if successfully synced.

<HorizontalLine />
