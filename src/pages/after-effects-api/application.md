---
id: "application"
title: "Application"
description: "Provides access to objects and application settings within the After Effects application; the single global object, always available as app."
sidebar_label: "Application"
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

# Application  

## Properties

| Name | Type | Access | Min Version | Description |
| :------ | :------ | :------ | :------ | :------ |
| activeViewer | *Viewer* | R | 27.0 | The Viewer object for the currently focused or active-focused viewer (Composition, Layer, or Footage) panel. Returns `null` if no viewers are open. |
| areToolTipsEnabled | *boolean* | R | 27.0 | Whether tooltips are currently enabled in the application's user interface. |
| availableGPUAccelTypes | *number[]* | R | 27.0 | Use this in conjunction with `app.project.gpuAccelType` to set the value for Project Settings > Video Rendering and Effects > Use. |
| disableRendering | *boolean* | RW | 27.0 | When `false` (the default), rendering proceeds as normal. Set to `true` to disable rendering as if Caps Lock were turned on. |
| disableScriptingProgressDialog | *boolean* | RW | 27.0 | When `true`, suppresses the progress dialog that would otherwise be shown while a script is running. |
| exitAfterLaunchAndEval | *boolean* | RW | 27.0 | This attribute is used only when executing a script from a command line on Windows. When the application is launched from the command line, the `-r` or `-s` command line flag causes the application to run a script (from a file or from a string, respectively). If this attribute is set to `true`, After Effects will exit after the script is run; if it is `false`, the application will remain open. This attribute only has an effect when After Effects is run from the Windows command line. It has no effect in Mac OS. |
| exitCode | *number* | RW | 27.0 | A numeric status code used when executing a script externally (that is, from a command line or AppleScript). |
| fonts | *Fonts* | R | 27.0 | Returns an object to navigate and retreive all the fonts currently available on your system. |
| getAllowedAppThemes | *string[]* | R | 27.0 | The available UI theme names the application's `getAppTheme` can be set to (`light`, `dark`, `darkest`). |
| getAppTheme | *string* | R | 27.0 | The name of the UI theme currently applied to the application, one of the values returned by `getAllowedAppThemes`. |
| getUseReducedContrast | *boolean* | R | 27.0 | Whether the operating system's reduced-contrast accessibility setting is currently enabled. |
| isAdvanced3DHardwareSupported | *boolean* | R | 27.0 | Whether the current system's graphics hardware supports advanced 3D rendering features. |
| isRenderEngine | *boolean* | R | 27.0 | `true` if After Effects is running as a render engine. |
| isUISuppressed | *boolean* | R | 27.0 | Whether the application is currently running with its user interface suppressed. |
| isWatchFolder | *boolean* | R | 27.0 | `true` if the Watch Folder dialog box is currently displayed and the application is currently watching a folder for rendering. |
| isoLanguage | *string* | R | 27.0 | A string indicating the locale (language and regional designations) After Effects is running. |
| language | *number* | R | 27.0 | The `Language` enumeration value corresponding to the language After Effects is currently running in. |
| memoryInUse | *number* | R | 27.0 | The number of bytes of memory currently used by this application. |
| preferences | *Preferences* | R | 27.0 | The currently loaded AE app preferences. See Preferences object. |
| reportErrorOnMissingFrame | *boolean* | RW | 27.0 | When `true`, causes an error to be reported if a frame of footage referenced by the project is missing. |
| saveProjectOnCrash | *boolean* | RW | 27.0 | When `true` (the default), After Effects attempts to display a dialog box that allows you to save the current project if an error causes the application to quit unexpectedly. Set to `false` to suppress this dialog box and quit without saving. |
| settings | *Settings* | R | 27.0 | The currently loaded settings. See [Settings object](./settings.md). |
| appName | *string* | R | 27.0 | The display name of the application, either `"After Effects"` or `"After Effects (Beta)"`. |
| buildName | *string* | R | 27.0 | The name of the build of After Effects being run, used internally by Adobe for testing and troubleshooting. |
| buildNumber | *number* | R | 27.0 | The number of the build of After Effects being run, used internally by Adobe for testing and troubleshooting. |
| isBeta | *boolean* | R | 27.0 | Whether this build of the application is a beta build. |
| isProfessionalVersion | *boolean* | R | 27.0 | Whether the running copy of the application is the professional version. |
| version | *string* | R | 27.0 | An alphanumeric string indicating which version of After Effects is running. |
| effects | *\{ displayName: string; matchName: string; category: string; version: string }[]* | R | 27.0 | The effects available in the application. |
| project | *Project* | R | 27.0 | The project that is currently loaded. See Project object. |


## Instance Methods

### activate

Returns: *boolean*

Since: **27.0**

Opens the application main window if it is minimized or iconified, and brings it to the front of the desktop.

<HorizontalLine />

### beginSuppressDialogs

Returns: *boolean*

Since: **27.0**

Begins suppression of script error dialog boxes in the user interface. Use `app.endSuppressDialogs()` to resume the display of error dialogs.

<HorizontalLine />

### beginUndoGroup

Returns: *boolean*

Since: **27.0**

Marks the beginning of an undo group, which allows a script to logically group all of its actions as a single undoable action (for use with the Edit > Undo/Redo menu items). Use the `app.endUndoGroup()` method to mark the end of the group. `beginUndoGroup()` and `endUndoGroup()` pairs can be nested. Groups within groups become part of the larger group, and will undo correctly. In this case, the names of inner groups are ignored.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *string* | The text that will appear for the Undo command in the Edit menu (that is, "Undo") |

<HorizontalLine />

### endSuppressDialogs

Returns: *boolean*

Since: **27.0**

Ends the suppression of script error dialog boxes in the user interface. Error dialogs are displayed by default;call this method only if `app.beginSuppressDialogs()` has previously been called.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *boolean* | When `true`, errors that have occurred following the call to `beginSuppressDialogs()` are displayed in a dialog box. |

<HorizontalLine />

### endUndoGroup

Returns: *boolean*

Since: **27.0**

Marks the end of an undo group begun with the `app.beginUndoGroup()` method. You can use this method to place an end to an undo group in the middle of a script, should you wish to use more than one undo group for a single script. If you are using only a single undo group for a given script, you do not need to use this method; in its absence at the end of a script, the system will close the undo group automatically. Calling this method without having set a `beginUndoGroup()` method yields an error.

<HorizontalLine />

### endWatchFolder

Returns: *boolean*

Since: **27.0**

Ends Watch Folder mode.

<HorizontalLine />

### executeCommand

Returns: *boolean*

Since: **27.0**

Menu Commands in the GUI application have an individual ID number, which can be used as the parameter for this method. For some functions not included in the API this is the only way to access them. The `app.findMenuCommandId()` method can be used to find the ID number for a command.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *number* | The ID number of the command. |

<HorizontalLine />

### findMenuCommandId

Returns: *number*

Since: **27.0**

Menu Commands in the GUI application have an individual ID number, which can be used as a parameter for the `app.executeCommand()` command. For some functions not included in the API this is the only way to access them. It should be noted that this method is not reliable across different language packages of AE, so you'll likely want to find the command ID number during development and then call it directly using the number in production.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *string* | The text of the menu command, exactly as it is shown in the UI. |

<HorizontalLine />

### log

Returns: *boolean*

Since: **27.0**

Writes a message to the application's log, optionally tagged with a category.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *string* | The message to write to the log. |
| category | *string* | An optional category label for the log message. |

<HorizontalLine />

### newProject

Returns: *Project*

Since: **27.0**

Creates a new project in After Effects, replicating the File > New > New Project menu command. If the current project has been edited, the user is prompted to save it. If the user cancels out of the Save dialog box, the new project is not created and the method returns `null`. Use `app.project.close(CloseOptions.DO_NOT_SAVE_CHANGES)` to close the current project before opening a new one.

<HorizontalLine />

### newTeamProject

Returns: *boolean*

Since: **27.0**

Creates a new Team Project, After Effects's cloud-based collaborative project format.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *string* | The name to give the new Team Project. |
| productionDescriptionP0 | *string* | A description for the new Team Project's production. |

<HorizontalLine />

### open

Returns: *Project*

Since: **27.0**

Opens a project.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *string* | The file path of the project to open. |

<HorizontalLine />

### openFast

Returns: *Project*

Since: **27.0**

Opens a project faster than `app.open()` by skipping some checks.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *string* | The file path of the project to open. |

<HorizontalLine />

### openTeamProject

Returns: *boolean*

Since: **27.0**

Opens an existing Team Project.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *string* | The identifier of the Team Project to open. |

<HorizontalLine />

### openTemplate

Returns: *Project*

Since: **27.0**

Opens a project from an After Effects project template (.aet) file.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *string* | The path to the project template file to open. |

<HorizontalLine />

### parseSwatchFile

Returns: *\{ majorVersion: number; minorVersion: number; values: number[] }*

Since: **27.0**

Loads color swatch data from an Adobe Swatch Exchange (ASE) file.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| file | *string* | The file path of the ASE file to parse. |

<HorizontalLine />

### pauseWatchFolder

Returns: *boolean*

Since: **27.0**

Pauses or resumes the search of the target watch folder for items to render.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *boolean* | `true` to pause, `false` to resume. |

<HorizontalLine />

### purge

Returns: *boolean*

Since: **27.0**

Purges unused data of the specified types. Replicates the Purge options in the Edit menu.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *number* | The type of elements to purge from memory. One of: `PurgeTarget.ALL_CACHES`, `PurgeTarget.ALL_MEMORY_CACHES`, `PurgeTarget.UNDO_CACHES`, `PurgeTarget.SNAPSHOT_CACHES`, `PurgeTarget.IMAGE_CACHES`. |

<HorizontalLine />

### quit

Returns: *boolean*

Since: **27.0**

Quits the After Effects application.

<HorizontalLine />

### restart

Returns: *boolean*

Since: **27.0**

Restarts the After Effects application.

<HorizontalLine />

### scheduleTask

Returns: *number*

Since: **27.0**

Schedules the specified JavaScript for delayed execution.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| task | *string* | A string containing JavaScript to be executed. |
| delayInMilliseconds | *number* | A number of milliseconds to wait before executing the JavaScript. |
| repeat | *boolean* | When `true`, execute the script repeatedly, with the specified delay between each execution. When `false`, the script is executed only once. |

<HorizontalLine />

### setMemoryUsageLimits

Returns: *boolean*

Since: **27.0**

Sets memory usage limits as in the Memory & Cache preferences area. For both values, if installed RAM is less than a given amount (`n` gigabytes), the value is a percentage of the installed RAM, and is otherwise a percentage of `n`. The value of `n` is: 2 GB for 32-bit Windows, 4 GB for 64-bit Windows, 3.5 GB for Mac OS.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg1 | *number* | The percentage of memory assigned to image cache. |
| arg2 | *number* | The maximum usable percentage of memory. |

<HorizontalLine />

### setMultiFrameRenderingConfig

Returns: *boolean*

Since: **27.0**

Calling this function from a script will set the Multi-Frame Rendering configuration for the next render. After execution of the script is complete, these settings will be reset to what was previously set in the UI.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *boolean* | Set to `true` to enable Multi-Frame Rendering. |
| arg2 | *number* | The maximum CPU percentage Multi-Frame Rendering should utilize. If `mfr_on` is set to `false`, pass in 100. |

<HorizontalLine />

### setSavePreferencesOnQuit

Returns: *boolean*

Since: **27.0**

Set or clears the flag that determines whether preferences are saved when the application is closed.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *boolean* | When `true`, preferences saved on quit, when `false` they are not. |

<HorizontalLine />

### themeColor

Returns: *number[]*

Since: **27.0**

Deprecated and no longer available; calling this always throws an error directing you to use `getAppTheme`, `getUseReducedContrast`, and `getAllowedAppThemes` instead.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *number* | Unused; retained for backward compatibility with the removed API. |

<HorizontalLine />

### watchFolder

Returns: *boolean*

Since: **27.0**

Starts a Watch Folder (network rendering) process pointed at a specified folder.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *string* | The folder to watch. |

<HorizontalLine />
