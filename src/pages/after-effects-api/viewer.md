---
id: "viewer"
title: "Viewer"
description: "Represents a viewer panel, such as the Composition, Layer, or Footage panel."
sidebar_label: "Viewer"
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

# Viewer  

## Properties

| Name | Type | Access | Min Version | Description |
| :------ | :------ | :------ | :------ | :------ |
| active | *boolean* | R | 27.0 | When `true`, indicates if the viewer panel is focused, and thereby frontmost. |
| activeViewIndex | *number* | RW | 27.0 | The index of the current active View object, in the `views` array. |
| maximized | *boolean* | RW | 27.0 | When `true`, indicates if the viewer panel is at its maximized size. |
| numViews | *number* | R | 27.0 | The number of Views associated with this viewer, equal to the length of the `views` array. |
| type | *number* | R | 27.0 | The content in the viewer panel. |
| views | *Array* | R | 27.0 | All of the Views associated with this viewer. |


## Instance Methods

### setActive

Returns: *boolean*

Since: **27.0**

Moves the viewer panel to the front and places focus on it, making it active. Calling this method will set the viewer's active attribute to `true`.

<HorizontalLine />
