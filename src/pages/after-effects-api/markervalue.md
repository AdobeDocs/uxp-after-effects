---
id: "markervalue"
title: "MarkerValue"
description: "Represents a layer marker, used to associate a comment or navigation cue with a point in time."
sidebar_label: "MarkerValue"
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

# MarkerValue  

## Properties

| Name | Type | Access | Min Version | Description |
| :------ | :------ | :------ | :------ | :------ |
| chapter | *string* | RW | 27.0 | A text chapter link for this marker. Chapter links initiate a jump to a chapter in a QuickTime movie or in other formats that support chapter marks. |
| comment | *string* | RW | 27.0 | A text comment for this marker. This comment appears in the Timeline panel next to the layer marker. |
| cuePointName | *string* | RW | 27.0 | The Flash Video cue point name, as shown in the Marker dialog box. |
| duration | *number* | RW | 27.0 | The marker's duration, in seconds. The duration appears in the Timeline panel as a short bar extending from the marker location. |
| eventCuePoint | *boolean* | RW | 27.0 | When `true`, the FlashVideo cue point is for an event; otherwise, it is for navigation. |
| frameTarget | *string* | RW | 27.0 | A text frame target for this marker. Together with the URL value, this targets a specific frame within a Web page. |
| label | *number* | RW | 27.0 | The label color for a composition or layer marker. Colors are represented by their number (0 for None, or 1 to 16 for one of the preset colors in the Labels preferences). Custom label colors cannot be set programmatically. |
| protectedRegion | *boolean* | RW | 27.0 | State of the Protected Region option in the Composition Marker dialog box. When `true`, the composition marker behaves as a protected region. Also returns `true` for protected region markers on nested composition layers, but is otherwise not applicable to layer markers. |
| url | *string* | RW | 27.0 | A URL for this marker. This URL is an automatic link to a Web page. |


## Instance Methods

### getParameters

Returns: *\{ [key: string]: string }*

Since: **27.0**

Returns the key-value pairs for Flash Video cue-point parameters, for a cue point associated with this marker value.

<HorizontalLine />

### setParameters

Returns: *boolean*

Since: **27.0**

Associates a set of key-value pairs for Flash Video cue-point parameters, for a cue point associated with this marker value. A cue point can have any number of parameters, but you can add only three through the user interface; use this method to add more than three parameters.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *Object* | Object containing the key-value pairs as attributes and values. |

<HorizontalLine />
