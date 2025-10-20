---
url: https://developer.wordpress.org/plugins/plugin-basics/uninstall-methods
scraped_at: 2025-10-20T03:16:38.423Z
---

[Skip to content](https://developer.wordpress.org/plugins/plugin-basics/uninstall-methods/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Uninstall Methods


[Home](https://developer.wordpress.org/)[Plugin Handbook](https://developer.wordpress.org/plugins/)[Plugin Basics](https://developer.wordpress.org/plugins/plugin-basics/)Uninstall Methods

Search

# Uninstall Methods

## In this article

Table of Contents

- [Method 1: register\_uninstall\_hook](https://developer.wordpress.org/plugins/plugin-basics/uninstall-methods/#method-1-register_uninstall_hook)
- [Method 2: uninstall.php](https://developer.wordpress.org/plugins/plugin-basics/uninstall-methods/#method-2-uninstall-php)

[↑ Back to top](https://developer.wordpress.org/plugins/plugin-basics/uninstall-methods/#wp--skip-link--target)

Your plugin may need to do some clean-up when it is uninstalled from a site.

A plugin is considered uninstalled if a user has deactivated the plugin, and then clicks the delete link within the WordPress Admin.

When your plugin is uninstalled, you’ll want to clear out any plugin options and/or settings specific to the plugin, and/or other database entities such as tables.

Less experienced developers sometimes make the mistake of using the deactivation hook for this purpose.

This table illustrates the differences between deactivation and uninstall.

| Scenario | Deactivation Hook | Uninstall Hook |
| --- | --- | --- |
| Flush Cache/Temp | Yes | No |
| Flush Permalinks | Yes | No |
| Remove Options from {$ [wpdb](https://developer.wordpress.org/reference/classes/wpdb/)->prefix}\_options | No | Yes |
| Remove Tables from [wpdb](https://developer.wordpress.org/reference/classes/wpdb/) | No | Yes |

## [Method 1: register\_uninstall\_hook](https://developer.wordpress.org/plugins/plugin-basics/uninstall-methods/\#method-1-register_uninstall_hook)

To set up an uninstall hook, use the [register\_uninstall\_hook()](https://developer.wordpress.org/reference/functions/register_uninstall_hook/) function:

``
[Copy](https://developer.wordpress.org/plugins/plugin-basics/uninstall-methods/#)

```php
register_uninstall_hook(
	__FILE__,
	'pluginprefix_function_to_run'
);
```

## [Method 2: uninstall.php](https://developer.wordpress.org/plugins/plugin-basics/uninstall-methods/\#method-2-uninstall-php)

To use this method you need to create an `uninstall.php` file inside the root folder of your plugin. This magic file is run automatically when the users deletes the plugin.

For example: `/plugin-name/uninstall.php`

Always check for the constant `WP_UNINSTALL_PLUGIN` in `uninstall.php` before doing anything. This protects against direct access.

The constant will be defined by WordPress during the `uninstall.php` invocation.

The constant is **NOT** defined when uninstall is performed by [register\_uninstall\_hook()](https://developer.wordpress.org/reference/functions/register_uninstall_hook/) .

Here is an example deleting option entries and dropping a database table:

``
[Expand code](https://developer.wordpress.org/plugins/plugin-basics/uninstall-methods/#)

[Copy](https://developer.wordpress.org/plugins/plugin-basics/uninstall-methods/#)

```php
// if uninstall.php is not called by WordPress, die
if ( ! defined( 'WP_UNINSTALL_PLUGIN' ) ) {
    die;
}

$option_name = 'wporg_option';

delete_option( $option_name );

// for site options in Multisite
delete_site_option( $option_name );

// drop a custom database table
global $wpdb;
$wpdb->query( "DROP TABLE IF EXISTS {$wpdb->prefix}mytable" );
```

In Multisite, looping through all blogs to delete options can be very resource intensive.

First published

September 16, 2014

Last updated

February 20, 2024

[PreviousIncluding a Software LicensePrevious: Including a Software License](https://developer.wordpress.org/plugins/plugin-basics/including-a-software-license/)

[NextPlugin SecurityNext: Plugin Security](https://developer.wordpress.org/plugins/security/)

Notifications