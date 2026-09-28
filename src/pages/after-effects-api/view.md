---
id: "view"
title: "View"
description: "Represents a view displayed in a Viewer panel."
sidebar_label: "View"
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

# View  

## Properties

| Name | Type | Access | Min Version | Description |
| :------ | :------ | :------ | :------ | :------ |
| active | *boolean* | R | 27.0 | When `true`, indicates if the viewer panel is focused, and thereby frontmost. |
| options | *ViewOptions* | R | 27.0 | Options object for this View. |


## Instance Methods

### setActive

Returns: *boolean*

Since: **27.0**

Moves this view panel to the front and places focus on it, making it active. Calling this method will set the view's active attribute to `true`.

<HorizontalLine />

### stopPlayback

Returns: *boolean*

Since: **27.0**

Stops any preview or playback of this view currently in progress.

<HorizontalLine />
