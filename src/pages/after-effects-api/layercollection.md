---
id: "layercollection"
title: LayerCollection
sidebar_label: "LayerCollection"
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

# LayerCollection  

## Properties

| Name | Type | Access | Min Version | Description |
| :------ | :------ | :------ | :------ | :------ |
| length | *number* | R | 27.0 | The number of objects in the collection. |


## Instance Methods

### add

Returns: *AVLayer*

Since: **27.0**

Creates a new AVLayer object containing the specified item, and adds it to this collection. The new layer honors the "Create Layers at Composition Start Time" preference. This method generates an exception if the item cannot be added as a layer to this CompItem.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| item_for_layer | *object* | The item to be added. |
| duration | *number* | Optional. The length of a still layer in seconds. Used only if the item contains a piece of still footage. Has no effect on movies, sequences or audio. If supplied, sets the duration value of the new layer. Otherwise, the duration value is set according to user preferences. By default, this is the same as the duration of the containing CompItem. To set another preferred value, open Edit > Preferences > Import (Windows) or After Effects > Preferences > Import (Mac OS), and specify options under Still Footage. |

<HorizontalLine />

### addBoxText

Returns: *TextLayer*

Since: **27.0**

Creates a new paragraph (box) text layer with TextDocument.lineOrientation set to LineOrientation.HORIZONTAL and adds the new TextLayer object to this collection. To create a point text layer, use the LayerCollection.addText() method.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| param | *number[]* | The dimensions of the new text box. |
| arg1 | *string* | Optional text to set as the initial content of the new text layer. |

<HorizontalLine />

### addCamera

Returns: *CameraLayer*

Since: **27.0**

Creates a new camera layer and adds the CameraLayer object to this collection. The new layer honors the "Create Layers at Composition Start Time" preference.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| name | *string* | The name of the new layer. |
| centerPointV | *number[]* | The initial X and Y values of the new camera's Point of Interest property. The z value is set to 0. |

<HorizontalLine />

### addLight

Returns: *LightLayer*

Since: **27.0**

Creates a new light layer and adds the LightLayer object to this collection. The new layer honors the "Create Layers at Composition Start Time" preference.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| name | *string* | The name of the new layer. |
| centerPointV | *number[]* | The center of the new light |

<HorizontalLine />

### addNull

Returns: *AVLayer*

Since: **27.0**

Creates a new null layer and adds the AVLayer object to this collection. This is the same as choosing Layer > New > Null Object.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| duration | *number* | Optional. The length of a still layer in seconds. If supplied, sets the duration value of the new layer. Otherwise, the duration value is set according to user preferences. By default, this is the same as the duration of the containing CompItem. To set another preferred value, open Edit > Preferences > Import (Windows) or After Effects > Preferences > Import (Mac OS), and specify options under Still Footage. |

<HorizontalLine />

### addParametricMesh

Returns: *ParametricMeshLayer*

Since: **27.0**

Creates a new parametric 3D mesh layer.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| name | *string* | The name of the new layer. |
| arg1 | *number* | The mesh type of the new layer. |

<HorizontalLine />

### addShape

Returns: *ShapeLayer*

Since: **27.0**

Creates a new ShapeLayer object for a new, empty Shape layer. Use the ShapeLayer object to add properties, such as shape, fill, stroke, and path filters. This is the same as using a shape tool in "Tool Creates Shape" mode. Tools automatically add a vector group that includes Fill and Stroke as specified in the tool options.

<HorizontalLine />

### addSolid

Returns: *AVLayer*

Since: **27.0**

Creates a new SolidSource object, with values set as specified; sets the new SolidSource as the mainSource value of a new FootageItem object, and adds the FootageItem to the project. Creates a new AVLayer object, sets the new Footage Item as its source, and adds the layer to this collection.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| color | *number[]* | The color of the solid. Three numbers, [R, G, B], in the range [0.0..1.0] |
| name | *string* | The name of the solid. |
| width | *number* | The width of the solid in pixels, in the range [1..30000] |
| height | *number* | The height of the solid in pixels, in the range [1..30000] |
| pixelAspect | *number* | The pixel aspect ratio of the solid, in the range [0.01..100.0] |
| duration | *number* | Optional. The length of a still layer in seconds. If supplied, sets the duration value of the new layer. Otherwise, the duration value is set according to user preferences. By default, this is the same as the duration of the containing CompItem. To set another preferred value, open Edit > Preferences > Import (Windows) or After Effects > Preferences > Import (MacOS), and specify options under Still Footage. |

<HorizontalLine />

### addText

Returns: *AVLayer*

Since: **27.0**

Creates a new point text layer with TextDocument.lineOrientation set to LineOrientation.HORIZONTAL and adds the new TextLayer object to this collection. To create a paragraph (box) text layer, use LayerCollection.addBoxText().

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| sourceText | *string* or [*TextDocument*](/ae_reference/classes/textdocument.md) | Optional. The source text of the new layer, or a TextDocument object containing the source text of the new layer. |

<HorizontalLine />

### addVerticalBoxText

Returns: *TextLayer*

Since: **27.0**

Creates a new paragraph (box) text layer with TextDocument.lineOrientation set to LineOrientation.VERTICAL_RIGHT_TO_LEFT and adds the new TextLayer object to this collection. To create a point text layer, use the LayerCollection.addText() or LayerCollection.addVerticalText() methods.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| param | *number[]* | The dimensions of the new text box. |
| arg1 | *string* | Optional text to set as the initial content of the new text layer. |

<HorizontalLine />

### addVerticalText

Returns: *AVLayer*

Since: **27.0**

Creates a new point text layer with TextDocument.lineOrientation set to LineOrientation.VERTICAL_RIGHT_TO_LEFT and adds the new TextLayer object to this collection. To create a paragraph (box) text layer, use the LayerCollection.addBoxText() or LayerCollection.addVerticalBoxText() methods.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| sourceText | *string* or [*TextDocument*](/ae_reference/classes/textdocument.md) | Optional. The source text of the new layer, or a TextDocument object containing the source text of the new layer. |

<HorizontalLine />

### byIndex

Returns: *Layer*

Since: **27.0**

Retrieves an object in the collection by its index number. The first object is at index 1.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| oneBasedIndex | *number* | The one-based index of the layer to retrieve; the first layer in the collection is at index 1. |

<HorizontalLine />

### byName

Returns: *Layer*

Since: **27.0**

Returns the first (topmost) layer found in this collection with the specified name, or null if no layer with the given name is found.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| name | *string* | A string containing the name. |

<HorizontalLine />

### precompose

Returns: *CompItem*

Since: **27.0**

Creates a new CompItem object and moves the specified layers into its layer collection. It removes the individual layers from this collection, and adds the new CompItem to this collection.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| param | *number[]* | The position indexes of the layers to be collected. |
| name | *string* | The name of the new CompItem object. |
| arg2 | *boolean* | Optional. When true (the default), retains all attributes in the new composition. This is the same as selecting the "Move all attributes into the new composition" option in the Pre-compose dialog box. You can only set this to false if there is just one index in the layerIndices array. This is the same as selecting the "Leave all attributes in" option in the Pre-compose dialog box. |

<HorizontalLine />

### relativeTo

Returns: *Layer*

Since: **27.0**

Returns the layer whose position is found by adding relIndex to otherLayer's index.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| otherLayer | *object* | The layer in this composition to use as the reference point for the returned layer's position. |
| relIndex | *number* | The offset added to otherLayer's index to determine the absolute index of the layer to return. |

<HorizontalLine />
