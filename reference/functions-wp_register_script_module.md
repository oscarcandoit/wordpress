---
url: https://developer.wordpress.org/reference/functions/wp_register_script_module
scraped_at: 2025-10-20T03:16:33.843Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/wp_register_script_module/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp\_register\_script\_module()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)wp\_register\_script\_module()

Search

# wp\_register\_script\_module( string$id, string$src, array$deps = array(), string\|false\|null$version = false )

## In this article

Table of Contents

- [Parameters](https://developer.wordpress.org/reference/functions/wp_register_script_module/#parameters)
- [Source](https://developer.wordpress.org/reference/functions/wp_register_script_module/#source)
- [Related](https://developer.wordpress.org/reference/functions/wp_register_script_module/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/wp_register_script_module/#changelog)

[↑ Back to top](https://developer.wordpress.org/reference/functions/wp_register_script_module/#wp--skip-link--target)

Registers the script module if no script module with that script module identifier has already been registered.

## [Parameters](https://developer.wordpress.org/reference/functions/wp_register_script_module/\#parameters)

`$id` stringrequired

The identifier of the script module. Should be unique. It will be used in the final import map.

`$src` stringoptional

Full URL of the script module, or path of the script module relative to the WordPress root directory. If it is provided and the script module has not been registered yet, it will be registered.

`$deps` arrayoptional

List of dependencies.

- `...$0` string\|array
An array of script module identifiers of the dependencies of this script module. The dependencies can be strings or arrays. If they are arrays, they need an `id` key with the script module identifier, and can contain an `import` key with either `static` or `dynamic`. By default, dependencies that don’t contain an `import` key are considered static.

- `id` string
The script module identifier.

- `import` string
Optional. Import type. May be either `static` or `dynamic`. Defaults to `static`.


Default: `array()`

`$version` string\|false\|nulloptional

String specifying the script module version number. Defaults to false.

It is added to the URL as a query string for cache busting purposes. If $version is set to false, the version number is the currently installed WordPress version.

If $version is set to null, no version is added.

Default: `false`

## [Source](https://developer.wordpress.org/reference/functions/wp_register_script_module/\#source)

`wp-includes/script-modules.php`
[Copy](https://developer.wordpress.org/reference/functions/wp_register_script_module/#)

```php
function wp_register_script_module( string $id, string $src, array $deps = array(), $version = false ) {
	wp_script_modules()->register( $id, $src, $deps, $version );
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/script-modules.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/script-modules.php#L64) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/script-modules.php#L64-L66)

## [Related](https://developer.wordpress.org/reference/functions/wp_register_script_module/\#related)

| Uses | Description |
| --- | --- |
| [WP\_Script\_Modules::register()](https://developer.wordpress.org/reference/classes/wp_script_modules/register/) `wp-includes/class-wp-script-modules.php` | Registers the script module if no script module with that script module identifier has already been registered. |
| [wp\_script\_modules()](https://developer.wordpress.org/reference/functions/wp_script_modules/) `wp-includes/script-modules.php` | Retrieves the main [WP\_Script\_Modules](https://developer.wordpress.org/reference/classes/wp_script_modules/) instance. |

| Used by | Description |
| --- | --- |
| [wp\_default\_script\_modules()](https://developer.wordpress.org/reference/functions/wp_default_script_modules/) `wp-includes/script-modules.php` | Registers all the default WordPress Script Modules. |
| [register\_block\_script\_module\_id()](https://developer.wordpress.org/reference/functions/register_block_script_module_id/) `wp-includes/blocks.php` | Finds a script module ID for the selected block metadata field. It detects when a path to file was provided and optionally finds a corresponding asset file with details necessary to register the script module under with an automatically generated module ID. It returns unprocessed script module ID otherwise. |

## [Changelog](https://developer.wordpress.org/reference/functions/wp_register_script_module/\#changelog)

| Version | Description |
| --- | --- |
| [6.5.0](https://developer.wordpress.org/reference/since/6.5.0/) | Introduced. |

## User Contributed Notes

You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_register_script_module%2F) before being able to contribute a note or feedback.

Notifications