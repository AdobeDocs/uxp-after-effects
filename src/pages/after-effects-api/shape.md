---
id: "shape"
title: "Shape"
description: "Represents the outline shape used by a mask or shape layer path property."
sidebar_label: "Shape"
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

# Shape  

## Properties

| Name | Type | Access | Min Version | Description |
| :------ | :------ | :------ | :------ | :------ |
| closed | *boolean* | RW | 27.0 | When `true`, the first and last vertices are connected to form a closed curve. When `false`, the closing segment is not drawn. |
| featherInterps | *number[]* | RW | 27.0 | An array containing each feather point's radius interpolation type (0 for non-Hold feather points, 1 for Hold feather points). |
| featherRadii | *number[]* | RW | 27.0 | An array containing each feather point's radius (feather amount); inner feather points have negative values. |
| featherRelCornerAngles | *number[]* | RW | 27.0 | An array containing each feather point's relative angle percentage between the two normals on either side of a curved outer feather boundary at a corner on a mask path. The angle value is 0% for feather points not at corners. |
| featherRelSegLocs | *number[]* | RW | 27.0 | An array containing each feather point's relative position, from 0 to 1, on its mask path segment (section of the mask path between vertices, numbered starting at 0). |
| featherSegLocs | *number[]* | RW | 27.0 | An array containing each feather point's mask path segment number (section of the mask path between vertices, numbered starting at 0). |
| featherTensions | *number[]* | RW | 27.0 | An array containing each feather point's tension amount, from 0 (0% tension) to 1 (100% tension). |
| featherTypes | *number[]* | RW | 27.0 | An array containing each feather point's direction, either 0 (outer feather point) or 1 (inner feather point). |
| inTangents | *Array* | RW | 27.0 | The incoming tangent vectors, or direction handles, associated with the vertices of the shape. Specify each vector as an array of two floating-point values, and collect the vectors into an array the same length as the `vertices` array. Each tangent value defaults to [0,0]. When the mask shape is not RotoBezier, this results in a straight line segment. If the shape is in a RotoBezier mask, all tangent values are ignored and the tangents are automatically calculated. |
| outTangents | *Array* | RW | 27.0 | The outgoing tangent vectors, or direction handles, associated with the vertices of the shape. Specify each vector as an array of two floating-point values, and collect the vectors into an array the same length as the `vertices` array. Each tangent value defaults to [0,0]. When the mask shape is not RotoBezier, this results in a straight line segment. If the shape is in a RotoBezier mask, all tangent values are ignored and the tangents are automatically calculated. |
| vertices | *Array* | RW | 27.0 | The anchor points of the shape. Specify each point as an array of two floating-point values, and collect the point pairs into an array for the complete set of points. |


