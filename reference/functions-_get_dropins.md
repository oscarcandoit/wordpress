---
url: https://developer.wordpress.org/reference/functions/_get_dropins
scraped_at: 2025-10-20T03:17:02.527Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/_get_dropins/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

\_get\_dropins()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)\_get\_dropins()

Search

# \_get\_dropins(): array\[\]

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/_get_dropins/#description)
- [Return](https://developer.wordpress.org/reference/functions/_get_dropins/#return)
- [Source](https://developer.wordpress.org/reference/functions/_get_dropins/#source)
- [Related](https://developer.wordpress.org/reference/functions/_get_dropins/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/_get_dropins/#changelog)

[↑ Back to top](https://developer.wordpress.org/reference/functions/_get_dropins/#wp--skip-link--target)

Returns drop-in plugins that WordPress uses.

## [Description](https://developer.wordpress.org/reference/functions/_get_dropins/\#description)

Includes Multisite drop-ins only when [is\_multisite()](https://developer.wordpress.org/reference/functions/is_multisite/)

## [Return](https://developer.wordpress.org/reference/functions/_get_dropins/\#return)

array\[\] Key is file name. The value is an array of data about the drop-in.

- `...$0` array
Data about the drop-in.

- `0` string
The purpose of the drop-in.

- `1` string\|true
Name of the constant that must be true for the drop-in to be used, or true if no constant is required.


## [Source](https://developer.wordpress.org/reference/functions/_get_dropins/\#source)

`wp-admin/includes/plugin.php`
[Expand code](https://developer.wordpress.org/reference/functions/_get_dropins/#)

[Copy](https://developer.wordpress.org/reference/functions/_get_dropins/#)

```php
function _get_dropins() {
	$dropins = array(
		'advanced-cache.php'      => array( __( 'Advanced caching plugin.' ), 'WP_CACHE' ),  // WP_CACHE
		'db.php'                  => array( __( 'Custom database class.' ), true ),          // Auto on load.
		'db-error.php'            => array( __( 'Custom database error message.' ), true ),  // Auto on error.
		'install.php'             => array( __( 'Custom installation script.' ), true ),     // Auto on installation.
		'maintenance.php'         => array( __( 'Custom maintenance message.' ), true ),     // Auto on maintenance.
		'object-cache.php'        => array( __( 'External object cache.' ), true ),          // Auto on load.
		'php-error.php'           => array( __( 'Custom PHP error message.' ), true ),       // Auto on error.
		'fatal-error-handler.php' => array( __( 'Custom PHP fatal error handler.' ), true ), // Auto on error.
	);

	if ( is_multisite() ) {
		$dropins['sunrise.php']        = array( __( 'Executed before Multisite is loaded.' ), 'SUNRISE' ); // SUNRISE
		$dropins['blog-deleted.php']   = array( __( 'Custom site deleted message.' ), true );   // Auto on deleted blog.
		$dropins['blog-inactive.php']  = array( __( 'Custom site inactive message.' ), true );  // Auto on inactive blog.
		$dropins['blog-suspended.php'] = array( __( 'Custom site suspended message.' ), true ); // Auto on archived or spammed blog.
	}

	return $dropins;
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-admin/includes/plugin.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-admin/includes/plugin.php#L500) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-admin/includes/plugin.php#L500-L520)

## [Related](https://developer.wordpress.org/reference/functions/_get_dropins/\#related)

| Uses | Description |
| --- | --- |
| [is\_multisite()](https://developer.wordpress.org/reference/functions/is_multisite/) `wp-includes/load.php` | Determines whether Multisite is enabled. |

| Used by | Description |
| --- | --- |
| [WP\_Plugins\_List\_Table::single\_row()](https://developer.wordpress.org/reference/classes/wp_plugins_list_table/single_row/) `wp-admin/includes/class-wp-plugins-list-table.php` |  |
| [get\_dropins()](https://developer.wordpress.org/reference/functions/get_dropins/) `wp-admin/includes/plugin.php` | Checks the wp-content directory and retrieve all drop-ins with any plugin data. |

## [Changelog](https://developer.wordpress.org/reference/functions/_get_dropins/\#changelog)

| Version | Description |
| --- | --- |
| [3.0.0](https://developer.wordpress.org/reference/since/3.0.0/) | Introduced. |

## User Contributed Notes

You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2F_get_dropins%2F) before being able to contribute a note or feedback.

Notifications