---
url: https://developer.wordpress.org/reference/functions/wp_is_auto_update_enabled_for_type
scraped_at: 2025-10-20T03:12:49.973Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/wp_is_auto_update_enabled_for_type/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp\_is\_auto\_update\_enabled\_for\_type()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)wp\_is\_auto\_update\_enabled\_for\_type()

Search

# wp\_is\_auto\_update\_enabled\_for\_type( string$type ): bool

## In this article

Table of Contents

- [Parameters](https://developer.wordpress.org/reference/functions/wp_is_auto_update_enabled_for_type/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/wp_is_auto_update_enabled_for_type/#return)
- [Source](https://developer.wordpress.org/reference/functions/wp_is_auto_update_enabled_for_type/#source)
- [Hooks](https://developer.wordpress.org/reference/functions/wp_is_auto_update_enabled_for_type/#hooks)
- [Related](https://developer.wordpress.org/reference/functions/wp_is_auto_update_enabled_for_type/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/wp_is_auto_update_enabled_for_type/#changelog)

[↑ Back to top](https://developer.wordpress.org/reference/functions/wp_is_auto_update_enabled_for_type/#wp--skip-link--target)

Checks whether auto-updates are enabled.

## [Parameters](https://developer.wordpress.org/reference/functions/wp_is_auto_update_enabled_for_type/\#parameters)

`$type` stringrequired

The type of update being checked: Either `'theme'` or `'plugin'`.

## [Return](https://developer.wordpress.org/reference/functions/wp_is_auto_update_enabled_for_type/\#return)

bool True if auto-updates are enabled for `$type`, false otherwise.

## [Source](https://developer.wordpress.org/reference/functions/wp_is_auto_update_enabled_for_type/\#source)

`wp-admin/includes/update.php`
[Expand code](https://developer.wordpress.org/reference/functions/wp_is_auto_update_enabled_for_type/#)

[Copy](https://developer.wordpress.org/reference/functions/wp_is_auto_update_enabled_for_type/#)

```php
function wp_is_auto_update_enabled_for_type( $type ) {
	if ( ! class_exists( 'WP_Automatic_Updater' ) ) {
		require_once ABSPATH . 'wp-admin/includes/class-wp-automatic-updater.php';
	}

	$updater = new WP_Automatic_Updater();
	$enabled = ! $updater->is_disabled();

	switch ( $type ) {
		case 'plugin':
			/**
			 * Filters whether plugins auto-update is enabled.
			 *
			 * @since 5.5.0
			 *
			 * @param bool $enabled True if plugins auto-update is enabled, false otherwise.
			 */
			return apply_filters( 'plugins_auto_update_enabled', $enabled );
		case 'theme':
			/**
			 * Filters whether themes auto-update is enabled.
			 *
			 * @since 5.5.0
			 *
			 * @param bool $enabled True if themes auto-update is enabled, false otherwise.
			 */
			return apply_filters( 'themes_auto_update_enabled', $enabled );
	}

	return false;
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-admin/includes/update.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-admin/includes/update.php#L1044) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-admin/includes/update.php#L1044-L1074)

## [Hooks](https://developer.wordpress.org/reference/functions/wp_is_auto_update_enabled_for_type/\#hooks)

[apply\_filters( ‘plugins\_auto\_update\_enabled’, bool$enabled )](https://developer.wordpress.org/reference/hooks/plugins_auto_update_enabled/)

Filters whether plugins auto-update is enabled.

[apply\_filters( ‘themes\_auto\_update\_enabled’, bool$enabled )](https://developer.wordpress.org/reference/hooks/themes_auto_update_enabled/)

Filters whether themes auto-update is enabled.

## [Related](https://developer.wordpress.org/reference/functions/wp_is_auto_update_enabled_for_type/\#related)

| Uses | Description |
| --- | --- |
| [apply\_filters()](https://developer.wordpress.org/reference/functions/apply_filters/) `wp-includes/plugin.php` | Calls the callback functions that have been added to a filter hook. |

| Used by | Description |
| --- | --- |
| [WP\_Site\_Health::detect\_plugin\_theme\_auto\_update\_issues()](https://developer.wordpress.org/reference/classes/wp_site_health/detect_plugin_theme_auto_update_issues/) `wp-admin/includes/class-wp-site-health.php` | Checks for potential issues with plugin and theme auto-updates. |
| [WP\_Automatic\_Updater::should\_update()](https://developer.wordpress.org/reference/classes/wp_automatic_updater/should_update/) `wp-admin/includes/class-wp-automatic-updater.php` | Tests to see if we can and should update a specific item. |
| [wp\_prepare\_themes\_for\_js()](https://developer.wordpress.org/reference/functions/wp_prepare_themes_for_js/) `wp-admin/includes/theme.php` | Prepares themes for JavaScript. |
| [WP\_Plugins\_List\_Table::\_\_construct()](https://developer.wordpress.org/reference/classes/wp_plugins_list_table/__construct/) `wp-admin/includes/class-wp-plugins-list-table.php` | Constructor. |
| [WP\_MS\_Themes\_List\_Table::\_\_construct()](https://developer.wordpress.org/reference/classes/wp_ms_themes_list_table/__construct/) `wp-admin/includes/class-wp-ms-themes-list-table.php` | Constructor. |
| [list\_plugin\_updates()](https://developer.wordpress.org/reference/functions/list_plugin_updates/) `wp-admin/update-core.php` | Display the upgrade plugins form. |
| [list\_theme\_updates()](https://developer.wordpress.org/reference/functions/list_theme_updates/) `wp-admin/update-core.php` | Display the upgrade themes form. |

[Show 2 more](https://developer.wordpress.org/reference/functions/wp_is_auto_update_enabled_for_type/#) [Show less](https://developer.wordpress.org/reference/functions/wp_is_auto_update_enabled_for_type/#)

## [Changelog](https://developer.wordpress.org/reference/functions/wp_is_auto_update_enabled_for_type/\#changelog)

| Version | Description |
| --- | --- |
| [5.5.0](https://developer.wordpress.org/reference/since/5.5.0/) | Introduced. |

## User Contributed Notes

You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_is_auto_update_enabled_for_type%2F) before being able to contribute a note or feedback.

Notifications