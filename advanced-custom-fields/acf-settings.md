---
url: https://www.advancedcustomfields.com/resources/acf-settings
scraped_at: 2025-10-20T02:23:20.593Z
---

# acf/settings

Last updated Feb 23, 2022

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-settings/#overview)

## Overview

Link copied

# acf/settings

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-settings/#description)

## Description

Link copied

Filters the various settings that are used throughout the plugin.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-settings/#changelog)

## Changelog

Link copied

- Added in version 5.0.0

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-settings/#parameters)

## Parameters

Link copied

```php
apply_filters( "acf/settings/{$name}", $value );
```

- `$value` _(mixed)_ The setting value.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-settings/#settings)

## Settings

Link copied

The following table lists the available settings which can be modified.

| Name | Type | Added | Description |
| --- | --- | --- | --- |
| `path` | string | 5.0.0 | Absolute path to ACF plugin folder including trailing slash. Defaults to `plugin_dir_path()` |
| `url` | string | 5.6.8 | URL to ACF plugin folder including trailing slash. Defaults to `plugin_dir_url()` |
| `dir` | string | 5.0.0 | URL to ACF plugin folder including trailing slash. Defaults to `plugin_dir_url()`. Deprecated in version 5.6.8. Please use **url** instead |
| `show_admin` | boolean | 5.0.0 | Show/hide ACF menu item. Defaults to true |
| `stripslashes` | boolean | 5.0.0 | Runs the function `stripslashes()` on all $\_POST data. Some servers / WP installs may require this extra functionality. Defaults to false |
| `local` | boolean | 5.0.0 | Enable/Disable local (PHP/json) fields. Defaults to true |
| `json` | boolean | 5.0.0 | Enable/Disable json fields. Defaults to true |
| `save_json` | string | 5.0.0 | Absolute path to folder where json files will be created when field groups are saved. Defaults to ‘acf-json’ folder within current theme |
| `load_json` | array | 5.0.0 | Array of absolute paths to folders where field group json files can be read. Defaults to an array containing at index 0, the ‘acf-json’ folder within current theme |
| `default_language` | string | 5.0.0 | Language code of the default language. Defaults to `''`. If WPML is active, ACF will default this to the WPML default language setting |
| `current_language` | string | 5.0.0 | Language code of the current post’s language. Defaults to `''`. If WPML is active, ACF will default this to the WPML current language |
| `capability` | string | 5.1.9 | Capability used for ACF post types and if the current user can see the ACF menu item. Defaults to ‘manage\_options’. |
| `show_updates` | boolean | 5.2.2 | Enable/Disable updates to appear in the installed plugin list and show/hide the ACF updates admin page. Defaults to `true`. |
| `export_textdomain` | string | 5.2.9 | Used during the ‘Export to PHP’ feature to wrap strings within the `__()` function. Depreciated in v5.4.4 – please see **l10n\_textdomain** |
| `export_translate` | array | 5.3.2 | Array of keys used during the ‘Export to PHP’ feature to wrap strings within the `__()` function. Defaults to `array('title', 'label', 'instructions')`. Depreciated in v5.3.4 – please see **l10n\_field** and **l10n\_field\_group** |
| `autoload` | boolean | 5.2.8 | Sets the default “autoload” setting used in `add_option()`. This function is used when saving new rows to the wp\_options table. Defaults to `false` |
| `l10n` | boolean | 5.3.4 | Allows ACF to translate field and field group settings using the `__()` function. Defaults to true. Useful to override translation without modifying the textdomain |
| `l10n_textdomain` | string | 5.3.4 | Sets the text domain used when translating field and field group settings. Defaults to `''`. Strings will not be translated if this setting is empty |
| `l10n_field` | array | 5.3.4 | An array of settings to translate when loading and exporting a field. Defaults to `array('label', 'instructions')`. Depreciated in v5.3.6 – please see `acf/translate_field` filter |
| `l10n_field_group` | array | 5.3.4 | An array of settings to translate when loading and exporting a field group. Defaults to `array('title')`. Depreciated in v5.3.6 – please see `acf/translate_field_group` filter |
| `google_api_key` | string | 5.4.0 | Specify a Google Maps API [authentication key](https://developers.google.com/maps/documentation/javascript/get-api-key) to prevent usage limits. Defaults to `''` |
| `google_api_client` | string | 5.4.0 | Specify a Google Maps API [Client ID](https://developers.google.com/maps/documentation/javascript/get-api-key) to prevent usage limits. Not needed if using `google_api_key`. Defaults to `''` |
| `enqueue_google_maps` | boolean | 5.5.0 | Allows ACF to enqueue and load the Google Maps API JS library. Defaults to true |
| `enqueue_select2` | boolean | 5.5.0 | Allows ACF to enqueue and load the Select2 JS/CSS library. Defaults to true |
| `select2_version` | numeric | 5.5.0 | Defines which version of Select2 library to enqueue. Either 3 or 4. Defaults to 4 since ACF 5.6.0 |
| `enqueue_datepicker` | boolean | 5.5.0 | Allows ACF to enqueue and load the WP datepicker JS/CSS library. Defaults to true |
| `enqueue_datetimepicker` | boolean | 5.5.0 | Allows ACF to enqueue and load the datetimepicker JS/CSS library. Defaults to true |
| `row_index_offset` | numeric | 5.5.6 | Defines the starting index used in all ‘loop’ and ‘row’ functions. Defaults to 1 (1 is the first row), can be changed to 0 (0 is the first row) |
| `remove_wp_meta_box` | boolean | 5.6.0 | Allows ACF to remove the default WP custom fields metabox. Defaults to `true` |
| `rest_api_enabled` | boolean | 5.11 | Enables/disables the ACF REST API integration.. Defaults to `true` |
| `rest_api_format` | string | 5.11 | Defines how ACF [formats field values](https://www.advancedcustomfields.com/resources/wp-rest-api-integration/#controlling-output-format) in the REST API. Defaults to `light` |
| `rest_api_embed_links` | boolean | 5.11 | Enables/disables [embed links](https://www.advancedcustomfields.com/resources/wp-rest-api-integration/#embed-links) for ACF fields in the REST API. Defaults to `true` |
| `preload_blocks` | boolean | 5.12 | Allows ACF to preload the initial render html of ACF Blocks into the block editor. Defaults to `true` |

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-settings/#examples)

## Examples

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-settings/#filter)

### Filter

Link copied

This example demonstrates how to modify a setting via the `"acf/settings/{$name}"` filter.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-settings/#functionsphp)

#### functions.php

Link copied

```php
add_filter('acf/settings/path', 'my_acf_settings_path');
function my_acf_settings_path( $path ) {
    return get_stylesheet_directory() . '/acf/';
}
```

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-settings/#function)

### Function

Link copied

This example demonstrates how to modify a setting via the function `acf_update_setting()`. This function is best used during the `acf/init` action.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-settings/#functionsphp)

#### functions.php

Link copied

```php
add_action('acf/init', 'my_acf_init');
function my_acf_init() {
    acf_update_setting('show_admin', false);
    acf_update_setting('google_api_key', 'xxx');
}
```

##### Supercharge Your Website With Premium Features Using ACF PRO

Speed up your workflow and unlock features to better develop websites using ACF Blocks and Options Pages, with the Flexible Content, Repeater,
Clone, Gallery Fields & More.


[Explore Features](https://www.advancedcustomfields.com/pro/) [View Pricing](https://www.advancedcustomfields.com/pro/#pricing-table/)

PRO Features

ACF Blocks

Options Pages

PRO Fields

Repeater

Flexible Content

Gallery

Clone

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-settings/#related)

## Related

Link copied

- Filters: [acf/update\_value](https://www.advancedcustomfields.com/resources/acf-update_value/)
- Filters: [acf/load\_value](https://www.advancedcustomfields.com/resources/acf-load_value/)
- Filters: [acf/load\_field](https://www.advancedcustomfields.com/resources/acf-load_field/)
- Filters: [acf/format\_value](https://www.advancedcustomfields.com/resources/acf-format_value/)
- Filters: [acf/update\_field](https://www.advancedcustomfields.com/resources/acf-update_field/)

Sign up for the latest Advanced Custom Fields news, updates, and developer tutorials

First name\*

Last name\*

Email\*

Anonymous ID (Segment)

GA Client ID

GA Session ID

FBC

FBP

GCLID

FBCLID

MSCLKID

LI FAT ID

Everflow Transaction ID

Kameleoon Visitor Code

UETVID

UTM Medium

UTM Content

UTM Campaign

UETSID

UTM Term

UTM Source

Logged In

MF User

Last Marketing (Form) Activity

We use cookies to offer you a better browsing experience, analyze site traffic and personalize content. Read about how we use cookies and how you can control them in our [Privacy Policy](https://wpengine.com/legal/privacy/). If you continue to use this site, you consent to our use of cookies.

[Got it](https://www.advancedcustomfields.com/resources/acf-settings/#)