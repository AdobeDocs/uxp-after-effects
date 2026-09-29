---
id: "preferences"
title: "Preferences"
sidebar_label: "Preferences"
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

# Preferences  


## Instance Methods

### deletePref

Returns: *boolean*

Since: **27.0**

Deletes a preference from the preference file.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| section | *string* | The name of a preferences section. |
| key | *string* | The key name of the preference. |
| prefType | *number* | Which preference file to use, a `PREFType` enum value. Optional; defaults to `PREF_Type_MACHINE_SPECIFIC` if not specified. |

<HorizontalLine />

### getPrefAsBool

Returns: *boolean*

Since: **27.0**

Retrieves a preference value from the preferences file, and parses it as a boolean.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| section | *string* | The name of a preferences section. |
| key | *string* | The key name of the preference. |
| prefType | *number* | Which preference file to use, a `PREFType` enum value. Optional; defaults to `PREF_Type_MACHINE_SPECIFIC` if not specified. |

<HorizontalLine />

### getPrefAsFloat

Returns: *number*

Since: **27.0**

Retrieves a preference value from the preferences file, and parses it as a float.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| section | *string* | The name of a preferences section. |
| key | *string* | The key name of the preference. |
| prefType | *number* | Which preference file to use, a `PREFType` enum value. Optional; defaults to `PREF_Type_MACHINE_SPECIFIC` if not specified. |

<HorizontalLine />

### getPrefAsLong

Returns: *number*

Since: **27.0**

Retrieves a preference value from the preferences file, and parses it as a long (number).

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| section | *string* | The name of a preferences section. |
| key | *string* | The key name of the preference. |
| prefType | *number* | Which preference file to use, a `PREFType` enum value. Optional; defaults to `PREF_Type_MACHINE_SPECIFIC` if not specified. |

<HorizontalLine />

### getPrefAsString

Returns: *string*

Since: **27.0**

Retrieves a preference value from the preferences file, and parses it as a string.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| section | *string* | The name of a preferences section. |
| key | *string* | The key name of the preference. |
| prefType | *number* | Which preference file to use, a `PREFType` enum value. Optional; defaults to `PREF_Type_MACHINE_SPECIFIC` if not specified. |

<HorizontalLine />

### havePref

Returns: *boolean*

Since: **27.0**

Returns `true` if the specified preference item exists and has a value.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| section | *string* | The name of a preferences section. |
| key | *string* | The key name of the preference. |
| prefType | *number* | Which preference file to use, a `PREFType` enum value. Optional; defaults to `PREF_Type_MACHINE_SPECIFIC` if not specified. |

<HorizontalLine />

### reload

Returns: *boolean*

Since: **27.0**

Reloads the preferences file manually. Otherwise, changes to preferences will only be accessible by scripting after an application restart.

<HorizontalLine />

### savePrefAsBool

Returns: *boolean*

Since: **27.0**

Saves a preference item as a boolean.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| section | *string* | The name of a preferences section. |
| key | *string* | The key name of the preference. |
| value | *boolean* | The boolean value to save. |
| prefType | *number* | Which preference file to use, a `PREFType` enum value. Optional; defaults to `PREF_Type_MACHINE_SPECIFIC` if not specified. |

<HorizontalLine />

### savePrefAsFloat

Returns: *boolean*

Since: **27.0**

Saves a preference item as a float.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| section | *string* | The name of a preferences section. |
| key | *string* | The key name of the preference. |
| value | *number* | The float value to save. |
| prefType | *number* | Which preference file to use, a `PREFType` enum value. Optional; defaults to `PREF_Type_MACHINE_SPECIFIC` if not specified. |

<HorizontalLine />

### savePrefAsLong

Returns: *boolean*

Since: **27.0**

Saves a preference item as a long.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| section | *string* | The name of a preferences section. |
| key | *string* | The key name of the preference. |
| value | *number* | The long (number) value to save. |
| prefType | *number* | Which preference file to use, a `PREFType` enum value. Optional; defaults to `PREF_Type_MACHINE_SPECIFIC` if not specified. |

<HorizontalLine />

### savePrefAsString

Returns: *boolean*

Since: **27.0**

Saves a preference item as a string.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| section | *string* | The name of a preferences section. |
| key | *string* | The key name of the preference. |
| value | *string* | The string value to save. |
| prefType | *number* | Which preference file to use, a `PREFType` enum value. Optional; defaults to `PREF_Type_MACHINE_SPECIFIC` if not specified. |

<HorizontalLine />

### saveToDisk

Returns: *boolean*

Since: **27.0**

Saves the preferences to disk manually. Otherwise, changes to preferences will only be accessible by scripting after an application restart.

<HorizontalLine />
