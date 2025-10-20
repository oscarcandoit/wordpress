---
url: https://developer.wordpress.org/plugins/settings/using-settings-api
scraped_at: 2025-10-20T03:16:31.109Z
---

[Skip to content](https://developer.wordpress.org/plugins/settings/using-settings-api/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Using Settings API


[Home](https://developer.wordpress.org/)[Plugin Handbook](https://developer.wordpress.org/plugins/)[Settings](https://developer.wordpress.org/plugins/settings/)Using Settings API

Search

# Using Settings API

## In this article

Table of Contents

- [Adding Settings](https://developer.wordpress.org/plugins/settings/using-settings-api/#adding-settings)
  - [Add a Setting](https://developer.wordpress.org/plugins/settings/using-settings-api/#add-a-setting)
  - [Add a Section](https://developer.wordpress.org/plugins/settings/using-settings-api/#add-a-section)
  - [Add a Field](https://developer.wordpress.org/plugins/settings/using-settings-api/#add-a-field)
  - [Example](https://developer.wordpress.org/plugins/settings/using-settings-api/#example)
- [Getting Settings](https://developer.wordpress.org/plugins/settings/using-settings-api/#getting-settings)
  - [Example](https://developer.wordpress.org/plugins/settings/using-settings-api/#example-2)

[↑ Back to top](https://developer.wordpress.org/plugins/settings/using-settings-api/#wp--skip-link--target)

## [Adding Settings](https://developer.wordpress.org/plugins/settings/using-settings-api/\#adding-settings)

You must define a new setting using [register\_setting()](https://developer.wordpress.org/reference/functions/register_setting/) , it will create an entry in the `{$wpdb->prefix}_options` table.

You can add new sections on existing pages using [add\_settings\_section()](https://developer.wordpress.org/reference/functions/add_settings_section/) .

You can add new fields to existing sections using [add\_settings\_field()](https://developer.wordpress.org/reference/functions/add_settings_field/) .

[register\_setting()](https://developer.wordpress.org/reference/functions/register_setting/) as well as the mentioned `add_settings_*()` functions should all be added to the `admin_init` action hook.

### [Add a Setting](https://developer.wordpress.org/plugins/settings/using-settings-api/\#add-a-setting)

``
[Copy](https://developer.wordpress.org/plugins/settings/using-settings-api/#)

```php
register_setting(    string $option_group,    string $option_name,    array $args = []);
```

Please refer to the Function Reference about [register\_setting()](https://developer.wordpress.org/reference/functions/register_setting/) for full explanation about the used parameters.

### [Add a Section](https://developer.wordpress.org/plugins/settings/using-settings-api/\#add-a-section)

``
[Copy](https://developer.wordpress.org/plugins/settings/using-settings-api/#)

```php
add_settings_section(    string $id,    string $title,    callable $callback,    string $page,    array $args = []);
```

Sections are the groups of settings you see on WordPress settings pages with a shared heading. In your plugin you can add new sections to existing settings pages rather than creating a whole new page. This makes your plugin simpler to maintain and creates fewer new pages for users to learn.

Please refer to the Function Reference about [add\_settings\_section()](https://developer.wordpress.org/reference/functions/add_settings_section/) for full explanation about the used parameters.

### [Add a Field](https://developer.wordpress.org/plugins/settings/using-settings-api/\#add-a-field)

``
[Copy](https://developer.wordpress.org/plugins/settings/using-settings-api/#)

```php
add_settings_field(
    string $id,
    string $title,
    callable $callback,
    string $page,
    string $section = 'default',
    array $args = []
);
```

Please refer to the Function Reference about [add\_settings\_field()](https://developer.wordpress.org/reference/functions/add_settings_field/) for full explanation about the used parameters.

### [Example](https://developer.wordpress.org/plugins/settings/using-settings-api/\#example)

``
[Expand code](https://developer.wordpress.org/plugins/settings/using-settings-api/#)

[Copy](https://developer.wordpress.org/plugins/settings/using-settings-api/#)

```php
function wporg_settings_init() {
	// register a new setting for "reading" page
	register_setting('reading', 'wporg_setting_name');

	// register a new section in the "reading" page
	add_settings_section(
		'wporg_settings_section',
		'WPOrg Settings Section', 'wporg_settings_section_callback',
		'reading'
	);

	// register a new field in the "wporg_settings_section" section, inside the "reading" page
	add_settings_field(
		'wporg_settings_field',
		'WPOrg Setting', 'wporg_settings_field_callback',
		'reading',
		'wporg_settings_section'
	);
}

/**
 * register wporg_settings_init to the admin_init action hook
 */
add_action('admin_init', 'wporg_settings_init');

/**
 * callback functions
 */

// section content cb
function wporg_settings_section_callback() {
	echo '<p>WPOrg Section Introduction.</p>';
}

// field content cb
function wporg_settings_field_callback() {
	// get the value of the setting we've registered with register_setting()
	$setting = get_option('wporg_setting_name');
	// output the field
	?>
	<input type="text" name="wporg_setting_name" value="<?php echo isset( $setting ) ? esc_attr( $setting ) : ''; ?>">
    <?php
}
```

## [Getting Settings](https://developer.wordpress.org/plugins/settings/using-settings-api/\#getting-settings)

``
[Copy](https://developer.wordpress.org/plugins/settings/using-settings-api/#)

```php
get_option(
    string $option,
    mixed $default = false
);
```

Getting settings is accomplished with the [get\_option()](https://developer.wordpress.org/reference/functions/get_option/) function.

The function accepts two parameters: the name of the option and an optional default value for that option.

### [Example](https://developer.wordpress.org/plugins/settings/using-settings-api/\#example-2)

``
[Copy](https://developer.wordpress.org/plugins/settings/using-settings-api/#)

```php
// Get the value of the setting we've registered with register_setting()
$setting = get_option('wporg_setting_name');
```

First published

September 24, 2014

Last updated

February 5, 2024

[PreviousSettings APIPrevious: Settings API](https://developer.wordpress.org/plugins/settings/settings-api/)

[NextMetadataNext: Metadata](https://developer.wordpress.org/plugins/metadata/)

Notifications