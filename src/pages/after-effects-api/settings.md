---
id: "settings"
title: "Settings"
description: "Provides an easy way to manage settings for third-party scripts, persisted in the After Effects preferences file."
sidebar_label: "Settings"
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

# Settings  


## Instance Methods

### getSetting

Returns: *string*

Since: **27.0**

Retrieves a script settings item value from the preferences file.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| section | *string* | The name of a settings section. |
| key | *string* | The key name of the setting item. |
| prefType | *number* | Optional. Which preference file to use. |

<HorizontalLine />

### haveSetting

Returns: *boolean*

Since: **27.0**

Returns `true` if the specified script settings item exists and has a value.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| section | *string* | The name of a settings section. |
| key | *string* | The key name of the setting item. |
| prefType | *number* | Optional. Which preference file to use. |

<HorizontalLine />

### saveSetting

Returns: *boolean*

Since: **27.0**

Saves a value for a script settings item.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| section | *string* | The name of a settings section. |
| key | *string* | The key name of the setting item. |
| value | *string* | The new value. |
| prefType | *number* | Optional. Which preference file to use. |

<HorizontalLine />
