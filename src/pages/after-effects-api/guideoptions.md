---
id: "guideoptions"
title: "GuideOptions"
description: "Represents a single guide added to a composition's viewer."
sidebar_label: "GuideOptions"
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

# GuideOptions  

## Properties

| Name | Type | Access | Min Version | Description |
| :------ | :------ | :------ | :------ | :------ |
| color | *number[]* | RW | 27.0 | The guide's color as an array of three floats, `[R, G, B]`, each in the range `0.0`-`1.0`. |
| orientationType | *number* | RW | 27.0 | The guide's orientation: `GuideOrientationType.HORIZONTAL` or `GuideOrientationType.VERTICAL`. |
| pinned | *boolean* | RW | 27.0 | When `true`, the guide is pinned to the opposite edge (bottom for horizontal guides, right for vertical guides). |
| position | *number* | RW | 27.0 | The guide's position, in pixels or percent depending on `positionType`. Clamped to ±100,000 px or ±300%; non-finite values are rejected. |
| positionType | *number* | RW | 27.0 | How `position` is interpreted: `GuidePositionType.PIXEL` or `GuidePositionType.PERCENTAGE`. |


