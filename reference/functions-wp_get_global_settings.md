---
url: https://developer.wordpress.org/reference/functions/wp_get_global_settings
scraped_at: 2025-10-20T03:20:17.310Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/wp_get_global_settings/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp\_get\_global\_settings()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)wp\_get\_global\_settings()

Search

# wp\_get\_global\_settings( array$path = array(), array$context = array() ): mixed

## In this article

Table of Contents

- [Parameters](https://developer.wordpress.org/reference/functions/wp_get_global_settings/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/wp_get_global_settings/#return)
- [Source](https://developer.wordpress.org/reference/functions/wp_get_global_settings/#source)
- [Related](https://developer.wordpress.org/reference/functions/wp_get_global_settings/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/wp_get_global_settings/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/functions/wp_get_global_settings/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/functions/wp_get_global_settings/#wp--skip-link--target)

Gets the settings resulting of merging core, theme, and user data.

## [Parameters](https://developer.wordpress.org/reference/functions/wp_get_global_settings/\#parameters)

`$path` arrayoptional

Path to the specific setting to retrieve. Optional.

If empty, will return all settings.

Default: `array()`

`$context` arrayoptional

Metadata to know where to retrieve the $path from. Optional.

- `block_name` string
Which block to retrieve the settings from.


If empty, it’ll return the settings for the global context.

- `origin` string
Which origin to take data from.


Valid values are `'all'` (core, theme, and user) or `'base'` (core and theme).


If empty or unknown, `'all'` is used.


Default: `array()`

## [Return](https://developer.wordpress.org/reference/functions/wp_get_global_settings/\#return)

mixed The settings array or individual setting value to retrieve.

## [Source](https://developer.wordpress.org/reference/functions/wp_get_global_settings/\#source)

`wp-includes/global-styles-and-settings.php`
[Expand code](https://developer.wordpress.org/reference/functions/wp_get_global_settings/#)

[Copy](https://developer.wordpress.org/reference/functions/wp_get_global_settings/#)

```php
function wp_get_global_settings( $path = array(), $context = array() ) {
	if ( ! empty( $context['block_name'] ) ) {
		$new_path = array( 'blocks', $context['block_name'] );
		foreach ( $path as $subpath ) {
			$new_path[] = $subpath;
		}
		$path = $new_path;
	}

	/*
	 * This is the default value when no origin is provided or when it is 'all'.
	 *
	 * The $origin is used as part of the cache key. Changes here need to account
	 * for clearing the cache appropriately.
	 */
	$origin = 'custom';
	if (
		! wp_theme_has_theme_json() ||
		( isset( $context['origin'] ) && 'base' === $context['origin'] )
	) {
		$origin = 'theme';
	}

	/*
	 * By using the 'theme_json' group, this data is marked to be non-persistent across requests.
	 * See `wp_cache_add_non_persistent_groups` in src/wp-includes/load.php and other places.
	 *
	 * The rationale for this is to make sure derived data from theme.json
	 * is always fresh from the potential modifications done via hooks
	 * that can use dynamic data (modify the stylesheet depending on some option,
	 * settings depending on user permissions, etc.).
	 * See some of the existing hooks to modify theme.json behavior:
	 * https://make.wordpress.org/core/2022/10/10/filters-for-theme-json-data/
	 *
	 * A different alternative considered was to invalidate the cache upon certain
	 * events such as options add/update/delete, user meta, etc.
	 * It was judged not enough, hence this approach.
	 * See https://github.com/WordPress/gutenberg/pull/45372
	 */
	$cache_group = 'theme_json';
	$cache_key   = 'wp_get_global_settings_' . $origin;

	/*
	 * Ignore cache when the development mode is set to 'theme', so it doesn't interfere with the theme
	 * developer's workflow.
	 */
	$can_use_cached = ! wp_is_development_mode( 'theme' );

	$settings = false;
	if ( $can_use_cached ) {
		$settings = wp_cache_get( $cache_key, $cache_group );
	}

	if ( false === $settings ) {
		$settings = WP_Theme_JSON_Resolver::get_merged_data( $origin )->get_settings();
		if ( $can_use_cached ) {
			wp_cache_set( $cache_key, $settings, $cache_group );
		}
	}

	return _wp_array_get( $settings, $path, $settings );
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/global-styles-and-settings.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/global-styles-and-settings.php#L26) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/global-styles-and-settings.php#L26-L87)

## [Related](https://developer.wordpress.org/reference/functions/wp_get_global_settings/\#related)

| Uses | Description |
| --- | --- |
| [wp\_is\_development\_mode()](https://developer.wordpress.org/reference/functions/wp_is_development_mode/) `wp-includes/load.php` | Checks whether the site is in the given development mode. |
| [wp\_theme\_has\_theme\_json()](https://developer.wordpress.org/reference/functions/wp_theme_has_theme_json/) `wp-includes/global-styles-and-settings.php` | Checks whether a theme or its parent has a theme.json file. |
| [WP\_Theme\_JSON\_Resolver::get\_merged\_data()](https://developer.wordpress.org/reference/classes/wp_theme_json_resolver/get_merged_data/) `wp-includes/class-wp-theme-json-resolver.php` | Returns the data merged from multiple origins. |
| [\_wp\_array\_get()](https://developer.wordpress.org/reference/functions/_wp_array_get/) `wp-includes/functions.php` | Accesses an array in depth based on a path of keys. |
| [wp\_cache\_set()](https://developer.wordpress.org/reference/functions/wp_cache_set/) `wp-includes/cache.php` | Saves the data to the cache. |
| [wp\_cache\_get()](https://developer.wordpress.org/reference/functions/wp_cache_get/) `wp-includes/cache.php` | Retrieves the cache contents from the cache by key and group. |

[Show 1 more](https://developer.wordpress.org/reference/functions/wp_get_global_settings/#) [Show less](https://developer.wordpress.org/reference/functions/wp_get_global_settings/#)

| Used by | Description |
| --- | --- |
| [WP\_Font\_Face\_Resolver::get\_fonts\_from\_theme\_json()](https://developer.wordpress.org/reference/classes/wp_font_face_resolver/get_fonts_from_theme_json/) `wp-includes/fonts/class-wp-font-face-resolver.php` | Gets fonts defined in theme.json. |
| [WP\_Duotone::get\_all\_global\_styles\_presets()](https://developer.wordpress.org/reference/classes/wp_duotone/get_all_global_styles_presets/) `wp-includes/class-wp-duotone.php` | Scrape all possible duotone presets from global and theme styles and store them in self::$global\_styles\_presets. |
| [get\_block\_editor\_settings()](https://developer.wordpress.org/reference/functions/get_block_editor_settings/) `wp-includes/block-editor.php` | Returns the contextualized block editor settings for a selected editor context. |

## [Changelog](https://developer.wordpress.org/reference/functions/wp_get_global_settings/\#changelog)

| Version | Description |
| --- | --- |
| [5.9.0](https://developer.wordpress.org/reference/since/5.9.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/functions/wp_get_global_settings/\#user-contributed-notes)

1. [Skip to note 2 content](https://developer.wordpress.org/reference/functions/wp_get_global_settings/#comment-content-6805)



To know how to use the `$path` argument with `wp_get_global_settings()` to retrieve a specific setting, you can try it without first.





`wp-includes/global-styles-and-settings.php`
[Copy](https://developer.wordpress.org/reference/functions/wp_get_global_settings/#)




```php
$settings = wp_get_global_settings();
var_dump($settings);
```





This gives you a formatted array of every available settings, from this, you can locate the setting you’d like to retrieve.



For example, **gradients** are located in `$settings['color']['gradients']['theme']`



Take the `$settings` path, here it’s : `['color']['gradients']['theme']`, and transform that in a flat array like this : `['color','gradients','theme']`, this is the value you need to pass as the `$path` argument with `wp_get_global_settings($path)`.



**Example 1**, if you’d like to retrieve gradients specified in the theme.json for example, you could use the path argument like so :





`wp-includes/global-styles-and-settings.php`
[Copy](https://developer.wordpress.org/reference/functions/wp_get_global_settings/#)




```php
$gradients = wp_get_global_settings( array( 'color', 'gradients', 'theme' ) );
```





**Example 2**, to retrieve the spacing scale :





`wp-includes/global-styles-and-settings.php`
[Copy](https://developer.wordpress.org/reference/functions/wp_get_global_settings/#)




```php
$spacingScale = wp_get_global_settings( array( 'spacing', 'spacingScale' ) );
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_get_global_settings%2F%3Freplytocom%3D6805%23feedback-editor-6805)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_get_global_settings%2F) before being able to contribute a note or feedback.

Notifications