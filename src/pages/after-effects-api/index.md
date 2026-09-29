---
title: After Effects API Reference
description: "Reference for the Adobe After Effects APIs available to UXP plugins: application state, project items, layers, properties, fonts, import options, and settings."
keywords:
  - UXP
  - Adobe After Effects
  - After Effects API
  - After Effects scripting
  - UXP plugins
  - JavaScript
contributors:
  - https://github.com/AdobeDocs/uxp-after-effects
---

# After Effects API Reference

The After Effects API is the host-specific layer that After Effects adds on top
of UXP. Use it to inspect and update application state, project items, layers,
properties, fonts, import options, and settings from a UXP plugin.

## Access the API

Load the After Effects host module to access the application API. For example,
group related changes into one undo step:

```javascript
const app = require("aftereffects");

app.beginUndoGroup("Update composition");

// Make changes to the active project.

app.endUndoGroup();
```

## Browse the API

| Area | Use it to |
| --- | --- |
| [Application](application.md) | Access the running After Effects application, project, preferences, settings, and application commands. |
| [CharacterRange](characterrange.md) | Read and set character-level styling for a range of text in a Text layer. |
| [CompItem](compitem.md) | Access and modify composition settings, layers, and markers. |
| [ComposedLineRange](composedlinerange.md) | Inspect a single composed line of text within a Text layer. |
| [DeferredCall](deferredcall.md) | Track an asynchronous function call deferred until the script call stack clears. |
| [FileSource](filesource.md) | Inspect the file source associated with a project item. |
| [FolderItem](folderitem.md) | Organize project items into folders. |
| [Font](font.md) | Read font properties and metadata. |
| [Fonts](fonts.md) | Find and manage fonts available to After Effects. |
| [FootageItem](footageitem.md) | Inspect imported footage or solid-color items used as layer sources. |
| [GuideOptions](guideoptions.md) | Read and set the properties of a guide in a composition's viewer. |
| [ImportOptions](importoptions.md) | Configure how files and footage are imported into a project. |
| [ItemCollection](itemcollection.md) | Create, access, and organize project items. |
| [KeyframeEase](keyframeease.md) | Read and set the ease applied to a property's keyframe. |
| [Layer](layer.md) | Inspect and modify layers in a composition. |
| [MarkerValue](markervalue.md) | Add and configure markers on layers. |
| [MaskPropertyGroup](maskpropertygroup.md) | Read and set properties within a mask. |
| [OMCollection](omcollection.md) | Access the output modules in a render-queue item. |
| [OutputModule](outputmodule.md) | Configure how a render-queue item is rendered and saved. |
| [ParagraphRange](paragraphrange.md) | Read and set paragraph-level styling for text in a Text layer. |
| [PlaceholderSource](placeholdersource.md) | Inspect the source of a placeholder footage item. |
| [Property](property.md) | Read, set, and animate layer and effect properties. |
| [RenderQueue](renderqueue.md) | Queue and manage compositions for rendering. |
| [RenderQueueItem](renderqueueitem.md) | Configure a composition queued for rendering. |
| [RQItemCollection](rqitemcollection.md) | Access the items in the render queue. |
| [Settings](settings.md) | Store and retrieve After Effects application settings. |
| [Shape](shape.md) | Read and set the outline used by a mask or shape layer path. |
| [SolidSource](solidsource.md) | Inspect the source of a solid-color footage item. |
| [TextDocument](textdocument.md) | Read and set the text and formatting of a Text layer's source text. |
| [View](view.md) | Inspect a view shown in a viewer panel. |
| [Viewer](viewer.md) | Access and configure a Composition, Layer, or Footage viewer panel. |
| [ViewOptions](viewoptions.md) | Configure the display options of a view. |

## Minimum Version Tags

Property and method tables include the minimum After Effects version where a
member is available. Check the **Min Version** column before using an API so your
plugin can support the intended host versions.

## Shared UXP APIs

Use the After Effects API together with the shared UXP platform APIs for file
access, storage, networking, HTML, CSS, and Spectrum UI. For those platform
capabilities, start with the [UXP Hub](https://developer.adobe.com/uxp/?aio_external).
