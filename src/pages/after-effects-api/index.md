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
| [FileSource](filesource.md) | Inspect the file source associated with a project item. |
| [Font](font.md) | Read font properties and metadata. |
| [Fonts](fonts.md) | Find and manage fonts available to After Effects. |
| [ImportOptions](importoptions.md) | Configure how files and footage are imported into a project. |
| [ItemCollection](itemcollection.md) | Create, access, and organize project items. |
| [Layer](layer.md) | Inspect and modify layers in a composition. |
| [Property](property.md) | Read, set, and animate layer and effect properties. |
| [Settings](settings.md) | Store and retrieve After Effects application settings. |

## Minimum Version Tags

Property and method tables include the minimum After Effects version where a
member is available. Check the **Min Version** column before using an API so your
plugin can support the intended host versions.

## Shared UXP APIs

Use the After Effects API together with the shared UXP platform APIs for file
access, storage, networking, HTML, CSS, and Spectrum UI. For those platform
capabilities, start with the [UXP Hub](https://developer.adobe.com/uxp/?aio_external).
