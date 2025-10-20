---
url: https://developer.wordpress.org/reference/functions/get_site_transient
scraped_at: 2025-10-20T03:26:17.458Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/get_site_transient/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

get\_site\_transient()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)get\_site\_transient()

Search

# get\_site\_transient( string$transient ): mixed

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/get_site_transient/#description)
  - [See also](https://developer.wordpress.org/reference/functions/get_site_transient/#see-also)
- [Parameters](https://developer.wordpress.org/reference/functions/get_site_transient/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/get_site_transient/#return)
- [Source](https://developer.wordpress.org/reference/functions/get_site_transient/#source)
- [Hooks](https://developer.wordpress.org/reference/functions/get_site_transient/#hooks)
- [Related](https://developer.wordpress.org/reference/functions/get_site_transient/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/get_site_transient/#changelog)

[↑ Back to top](https://developer.wordpress.org/reference/functions/get_site_transient/#wp--skip-link--target)

Retrieves the value of a site transient.

## [Description](https://developer.wordpress.org/reference/functions/get_site_transient/\#description)

If the transient does not exist, does not have a value, or has expired, then the return value will be false.

### [See also](https://developer.wordpress.org/reference/functions/get_site_transient/\#see-also)

- [get\_transient()](https://developer.wordpress.org/reference/functions/get_transient)

## [Parameters](https://developer.wordpress.org/reference/functions/get_site_transient/\#parameters)

`$transient` stringrequired

Transient name. Expected to not be SQL-escaped.

## [Return](https://developer.wordpress.org/reference/functions/get_site_transient/\#return)

mixed Value of transient.

## [Source](https://developer.wordpress.org/reference/functions/get_site_transient/\#source)

`wp-includes/option.php`
[Expand code](https://developer.wordpress.org/reference/functions/get_site_transient/#)

[Copy](https://developer.wordpress.org/reference/functions/get_site_transient/#)

```php
function get_site_transient( $transient ) {

	/**
	 * Filters the value of an existing site transient before it is retrieved.
	 *
	 * The dynamic portion of the hook name, `$transient`, refers to the transient name.
	 *
	 * Returning a value other than boolean false will short-circuit retrieval and
	 * return that value instead.
	 *
	 * @since 2.9.0
	 * @since 4.4.0 The `$transient` parameter was added.
	 *
	 * @param mixed  $pre_site_transient The default value to return if the site transient does not exist.
	 *                                   Any value other than false will short-circuit the retrieval
	 *                                   of the transient, and return that value.
	 * @param string $transient          Transient name.
	 */
	$pre = apply_filters( "pre_site_transient_{$transient}", false, $transient );

	if ( false !== $pre ) {
		return $pre;
	}

	if ( wp_using_ext_object_cache() || wp_installing() ) {
		$value = wp_cache_get( $transient, 'site-transient' );
	} else {
		// Core transients that do not have a timeout. Listed here so querying timeouts can be avoided.
		$no_timeout       = array( 'update_core', 'update_plugins', 'update_themes' );
		$transient_option = '_site_transient_' . $transient;
		if ( ! in_array( $transient, $no_timeout, true ) ) {
			$transient_timeout = '_site_transient_timeout_' . $transient;
			wp_prime_site_option_caches( array( $transient_option, $transient_timeout ) );

			$timeout = get_site_option( $transient_timeout );
			if ( false !== $timeout && $timeout < time() ) {
				delete_site_option( $transient_option );
				delete_site_option( $transient_timeout );
				$value = false;
			}
		}

		if ( ! isset( $value ) ) {
			$value = get_site_option( $transient_option );
		}
	}

	/**
	 * Filters the value of an existing site transient.
	 *
	 * The dynamic portion of the hook name, `$transient`, refers to the transient name.
	 *
	 * @since 2.9.0
	 * @since 4.4.0 The `$transient` parameter was added.
	 *
	 * @param mixed  $value     Value of site transient.
	 * @param string $transient Transient name.
	 */
	return apply_filters( "site_transient_{$transient}", $value, $transient );
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/option.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/option.php#L2545) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/option.php#L2545-L2604)

## [Hooks](https://developer.wordpress.org/reference/functions/get_site_transient/\#hooks)

[apply\_filters( “pre\_site\_transient\_{$transient}”, mixed$pre\_site\_transient, string$transient )](https://developer.wordpress.org/reference/hooks/pre_site_transient_transient/)

Filters the value of an existing site transient before it is retrieved.

[apply\_filters( “site\_transient\_{$transient}”, mixed$value, string$transient )](https://developer.wordpress.org/reference/hooks/site_transient_transient/)

Filters the value of an existing site transient.

## [Related](https://developer.wordpress.org/reference/functions/get_site_transient/\#related)

| Uses | Description |
| --- | --- |
| [wp\_prime\_site\_option\_caches()](https://developer.wordpress.org/reference/functions/wp_prime_site_option_caches/) `wp-includes/option.php` | Primes specific network options for the current network into the cache with a single database query. |
| [wp\_installing()](https://developer.wordpress.org/reference/functions/wp_installing/) `wp-includes/load.php` | Checks or sets whether WordPress is in “installation” mode. |
| [wp\_using\_ext\_object\_cache()](https://developer.wordpress.org/reference/functions/wp_using_ext_object_cache/) `wp-includes/load.php` | Toggles `$_wp_using_ext_object_cache` on and off without directly touching global. |
| [delete\_site\_option()](https://developer.wordpress.org/reference/functions/delete_site_option/) `wp-includes/option.php` | Removes an option by name for the current network. |
| [wp\_cache\_get()](https://developer.wordpress.org/reference/functions/wp_cache_get/) `wp-includes/cache.php` | Retrieves the cache contents from the cache by key and group. |
| [apply\_filters()](https://developer.wordpress.org/reference/functions/apply_filters/) `wp-includes/plugin.php` | Calls the callback functions that have been added to a filter hook. |
| [get\_site\_option()](https://developer.wordpress.org/reference/functions/get_site_option/) `wp-includes/option.php` | Retrieve an option value for the current network based on name of option. |

[Show 3 more](https://developer.wordpress.org/reference/functions/get_site_transient/#) [Show less](https://developer.wordpress.org/reference/functions/get_site_transient/#)

| Used by | Description |
| --- | --- |
| [WP\_Plugin\_Dependencies::get\_dependency\_api\_data()](https://developer.wordpress.org/reference/classes/wp_plugin_dependencies/get_dependency_api_data/) `wp-includes/class-wp-plugin-dependencies.php` | Retrieves and stores dependency plugin data from the WordPress.org Plugin API. |
| [WP\_Font\_Collection::load\_from\_url()](https://developer.wordpress.org/reference/classes/wp_font_collection/load_from_url/) `wp-includes/fonts/class-wp-font-collection.php` | Loads the font collection data from a JSON file URL. |
| [WP\_Theme::get\_pattern\_cache()](https://developer.wordpress.org/reference/classes/wp_theme/get_pattern_cache/) `wp-includes/class-wp-theme.php` | Gets block pattern cache. |
| [WP\_REST\_URL\_Details\_Controller::get\_cache()](https://developer.wordpress.org/reference/classes/wp_rest_url_details_controller/get_cache/) `wp-includes/rest-api/endpoints/class-wp-rest-url-details-controller.php` | Utility function to retrieve a value from the cache at a given key. |
| [WP\_REST\_Pattern\_Directory\_Controller::get\_items()](https://developer.wordpress.org/reference/classes/wp_rest_pattern_directory_controller/get_items/) `wp-includes/rest-api/endpoints/class-wp-rest-pattern-directory-controller.php` | Search and retrieve block patterns metadata |
| [WP\_MS\_Themes\_List\_Table::column\_autoupdates()](https://developer.wordpress.org/reference/classes/wp_ms_themes_list_table/column_autoupdates/) `wp-admin/includes/class-wp-ms-themes-list-table.php` | Handles the auto-updates column output. |
| [wp\_check\_php\_version()](https://developer.wordpress.org/reference/functions/wp_check_php_version/) `wp-admin/includes/misc.php` | Checks if the user needs to update PHP. |
| [WP\_Plugin\_Install\_List\_Table::get\_installed\_plugins()](https://developer.wordpress.org/reference/classes/wp_plugin_install_list_table/get_installed_plugins/) `wp-admin/includes/class-wp-plugin-install-list-table.php` | Returns the list of known plugins. |
| [WP\_Community\_Events::get\_cached\_events()](https://developer.wordpress.org/reference/classes/wp_community_events/get_cached_events/) `wp-admin/includes/class-wp-community-events.php` | Gets cached events. |
| [wp\_ajax\_update\_theme()](https://developer.wordpress.org/reference/functions/wp_ajax_update_theme/) `wp-admin/includes/ajax-actions.php` | Handles updating a theme via AJAX. |
| [wp\_get\_available\_translations()](https://developer.wordpress.org/reference/functions/wp_get_available_translations/) `wp-admin/includes/translation-install.php` | Get available translations from the WordPress.org API. |
| [WP\_Automatic\_Updater::run()](https://developer.wordpress.org/reference/classes/wp_automatic_updater/run/) `wp-admin/includes/class-wp-automatic-updater.php` | Kicks off the background update process, looping through all pending updates. |
| [Plugin\_Upgrader::bulk\_upgrade()](https://developer.wordpress.org/reference/classes/plugin_upgrader/bulk_upgrade/) `wp-admin/includes/class-plugin-upgrader.php` | Upgrades several plugins at once. |
| [Theme\_Upgrader::upgrade()](https://developer.wordpress.org/reference/classes/theme_upgrader/upgrade/) `wp-admin/includes/class-theme-upgrader.php` | Upgrades a theme. |
| [Theme\_Upgrader::bulk\_upgrade()](https://developer.wordpress.org/reference/classes/theme_upgrader/bulk_upgrade/) `wp-admin/includes/class-theme-upgrader.php` | Upgrades several themes at once. |
| [Plugin\_Upgrader::upgrade()](https://developer.wordpress.org/reference/classes/plugin_upgrader/upgrade/) `wp-admin/includes/class-plugin-upgrader.php` | Upgrades a plugin. |
| [wp\_prepare\_themes\_for\_js()](https://developer.wordpress.org/reference/functions/wp_prepare_themes_for_js/) `wp-admin/includes/theme.php` | Prepares themes for JavaScript. |
| [get\_theme\_update\_available()](https://developer.wordpress.org/reference/functions/get_theme_update_available/) `wp-admin/includes/theme.php` | Retrieves the update link if there is a theme update available. |
| [get\_theme\_feature\_list()](https://developer.wordpress.org/reference/functions/get_theme_feature_list/) `wp-admin/includes/theme.php` | Retrieves list of WordPress theme features (aka theme tags). |
| [WP\_Plugins\_List\_Table::prepare\_items()](https://developer.wordpress.org/reference/classes/wp_plugins_list_table/prepare_items/) `wp-admin/includes/class-wp-plugins-list-table.php` |  |
| [WP\_MS\_Themes\_List\_Table::prepare\_items()](https://developer.wordpress.org/reference/classes/wp_ms_themes_list_table/prepare_items/) `wp-admin/includes/class-wp-ms-themes-list-table.php` |  |
| [get\_core\_updates()](https://developer.wordpress.org/reference/functions/get_core_updates/) `wp-admin/includes/update.php` | Gets available core updates. |
| [find\_core\_auto\_update()](https://developer.wordpress.org/reference/functions/find_core_auto_update/) `wp-admin/includes/update.php` | Gets the best available (and enabled) Auto-Update for WordPress core. |
| [find\_core\_update()](https://developer.wordpress.org/reference/functions/find_core_update/) `wp-admin/includes/update.php` | Finds the available update for WordPress core. |
| [get\_plugin\_updates()](https://developer.wordpress.org/reference/functions/get_plugin_updates/) `wp-admin/includes/update.php` | Retrieves plugins with updates available. |
| [wp\_plugin\_update\_rows()](https://developer.wordpress.org/reference/functions/wp_plugin_update_rows/) `wp-admin/includes/update.php` | Adds a callback to display update information for plugins with updates available. |
| [wp\_plugin\_update\_row()](https://developer.wordpress.org/reference/functions/wp_plugin_update_row/) `wp-admin/includes/update.php` | Displays update information for a plugin. |
| [get\_theme\_updates()](https://developer.wordpress.org/reference/functions/get_theme_updates/) `wp-admin/includes/update.php` | Retrieves themes with updates available. |
| [wp\_theme\_update\_rows()](https://developer.wordpress.org/reference/functions/wp_theme_update_rows/) `wp-admin/includes/update.php` | Adds a callback to display update information for themes with updates available. |
| [wp\_theme\_update\_row()](https://developer.wordpress.org/reference/functions/wp_theme_update_row/) `wp-admin/includes/update.php` | Displays update information for a theme. |
| [wp\_check\_browser\_version()](https://developer.wordpress.org/reference/functions/wp_check_browser_version/) `wp-admin/includes/dashboard.php` | Checks if the user needs a browser update. |
| [install\_popular\_tags()](https://developer.wordpress.org/reference/functions/install_popular_tags/) `wp-admin/includes/plugin-install.php` | Retrieves popular WordPress plugin tags. |
| [install\_plugin\_install\_status()](https://developer.wordpress.org/reference/functions/install_plugin_install_status/) `wp-admin/includes/plugin-install.php` | Determines the status we can perform on a plugin. |
| [delete\_plugins()](https://developer.wordpress.org/reference/functions/delete_plugins/) `wp-admin/includes/plugin.php` | Removes directory and files of a plugin for a list of plugins. |
| [wp\_get\_popular\_importers()](https://developer.wordpress.org/reference/functions/wp_get_popular_importers/) `wp-admin/includes/import.php` | Returns a list from WordPress.org of popular importer plugins. |
| [wp\_credits()](https://developer.wordpress.org/reference/functions/wp_credits/) `wp-admin/includes/credits.php` | Retrieves the contributor credits. |
| [get\_theme\_roots()](https://developer.wordpress.org/reference/functions/get_theme_roots/) `wp-includes/theme.php` | Retrieves theme roots. |
| [search\_theme\_directories()](https://developer.wordpress.org/reference/functions/search_theme_directories/) `wp-includes/theme.php` | Searches all registered theme directories for complete and valid themes. |
| [\_maybe\_update\_plugins()](https://developer.wordpress.org/reference/functions/_maybe_update_plugins/) `wp-includes/update.php` | Checks the last time plugins were run before checking plugin versions. |
| [\_maybe\_update\_themes()](https://developer.wordpress.org/reference/functions/_maybe_update_themes/) `wp-includes/update.php` | Checks themes versions only after a duration of time. |
| [wp\_version\_check()](https://developer.wordpress.org/reference/functions/wp_version_check/) `wp-includes/update.php` | Checks WordPress version against the newest version. |
| [wp\_update\_plugins()](https://developer.wordpress.org/reference/functions/wp_update_plugins/) `wp-includes/update.php` | Checks for available updates to plugins based on the latest versions hosted on WordPress.org. |
| [wp\_update\_themes()](https://developer.wordpress.org/reference/functions/wp_update_themes/) `wp-includes/update.php` | Checks for available updates to themes based on the latest versions hosted on WordPress.org. |
| [wp\_get\_translation\_updates()](https://developer.wordpress.org/reference/functions/wp_get_translation_updates/) `wp-includes/update.php` | Retrieves a list of all language updates available. |
| [wp\_get\_update\_data()](https://developer.wordpress.org/reference/functions/wp_get_update_data/) `wp-includes/update.php` | Collects counts and UI strings for available updates. |
| [\_maybe\_update\_core()](https://developer.wordpress.org/reference/functions/_maybe_update_core/) `wp-includes/update.php` | Determines whether core should be updated. |

[Show 41 more](https://developer.wordpress.org/reference/functions/get_site_transient/#) [Show less](https://developer.wordpress.org/reference/functions/get_site_transient/#)

## [Changelog](https://developer.wordpress.org/reference/functions/get_site_transient/\#changelog)

| Version | Description |
| --- | --- |
| [2.9.0](https://developer.wordpress.org/reference/since/2.9.0/) | Introduced. |

## User Contributed Notes

You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_site_transient%2F) before being able to contribute a note or feedback.

Notifications