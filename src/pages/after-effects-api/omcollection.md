---
id: "omcollection"
title: "OMCollection"
description: "Represents a collection of output modules in a render-queue item."
sidebar_label: "OMCollection"
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

# OMCollection  

## Properties

| Name | Type | Access | Min Version | Description |
| :------ | :------ | :------ | :------ | :------ |
| length | *number* | R | 27.0 | The number of objects in the collection. |


## Instance Methods

### add

Returns: *OutputModule*

Since: **27.0**

Adds a new Output Module to the Render Queue Item, creating an OutputModule.

<HorizontalLine />

### getByIndex

Returns: *OutputModule*

Since: **27.0**

Retrieves the output module in the collection by its index number. The first object is at index 1.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| arg0 | *number* | The index number of the output module to retrieve. |

<HorizontalLine />
