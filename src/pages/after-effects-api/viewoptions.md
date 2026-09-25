---
id: "viewoptions"
title: "ViewOptions"
description: "Represents the display options for a View within a Viewer panel."
sidebar_label: "ViewOptions"
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

# ViewOptions  

## Properties

| Name | Type | Access | Min Version | Description |
| :------ | :------ | :------ | :------ | :------ |
| channels | *number* | RW | 27.0 | The state of the Channels menu. |
| checkerboards | *boolean* | RW | 27.0 | When `true`, checkerboards (transparency grid) is enabled in the current view. |
| exposure | *number* | RW | 27.0 | The exposure value for the current view. |
| fastPreview | *number* | RW | 27.0 | The state of the Fast Previews menu. This is a read/write attribute using an enumerated value. If you try to get or set the attribute's value in the Layer or Footage panel, you'll get an error message. The Draft preview mode is only available in ray-traced 3D compositions. If you try to use it in a Classic 3D composition, you'll get an error: "Cannot set Draft fast preview mode in a Classic 3D composition." |
| guidesLocked | *boolean* | RW | 27.0 | When `true`, indicates guides are locked in the view. |
| guidesSnap | *boolean* | RW | 27.0 | When `true`, indicates layers snap to guides when dragged in the view. |
| guidesVisibility | *boolean* | RW | 27.0 | When `true`, indicates guides are visible in the view. |
| rulers | *boolean* | RW | 27.0 | When `true`, indicates rulers are shown in the view. |
| zoom | *number* | RW | 27.0 | Sets the current zoom value for the view, as a normalized percentage between 1% (0.01) and 1600% (16). |


