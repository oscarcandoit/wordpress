---
url: https://developer.wordpress.org/reference/functions/wp_update_plugins
scraped_at: 2025-10-20T03:20:28.541Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/wp_update_plugins/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp\_update\_plugins()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)wp\_update\_plugins()

Search

# wp\_update\_plugins( array$extra\_stats = array() )

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/wp_update_plugins/#description)
- [Parameters](https://developer.wordpress.org/reference/functions/wp_update_plugins/#parameters)
- [Source](https://developer.wordpress.org/reference/functions/wp_update_plugins/#source)
- [Hooks](https://developer.wordpress.org/reference/functions/wp_update_plugins/#hooks)
- [Related](https://developer.wordpress.org/reference/functions/wp_update_plugins/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/wp_update_plugins/#changelog)

[↑ Back to top](https://developer.wordpress.org/reference/functions/wp_update_plugins/#wp--skip-link--target)

Checks for available updates to plugins based on the latest versions hosted on WordPress.org.

## [Description](https://developer.wordpress.org/reference/functions/wp_update_plugins/\#description)

Despite its name this function does not actually perform any updates, it only checks for available updates.

A list of all plugins installed is sent to api.wordpress.org, along with the site locale.

Checks against the WordPress server at api.wordpress.org. Will only check if WordPress isn’t installing.

## [Parameters](https://developer.wordpress.org/reference/functions/wp_update_plugins/\#parameters)

`$extra_stats` arrayoptional

Extra statistics to report to the WordPress.org API.

Default: `array()`

## [Source](https://developer.wordpress.org/reference/functions/wp_update_plugins/\#source)

`wp-includes/update.php`
[Expand code](https://developer.wordpress.org/reference/functions/wp_update_plugins/#)

[Copy](https://developer.wordpress.org/reference/functions/wp_update_plugins/#)

```php
function wp_update_plugins( $extra_stats = array() ) {
	if ( wp_installing() ) {
		return;
	}

	// If running blog-side, bail unless we've not checked in the last 12 hours.
	if ( ! function_exists( 'get_plugins' ) ) {
		require_once ABSPATH . 'wp-admin/includes/plugin.php';
	}

	$plugins      = get_plugins();
	$translations = wp_get_installed_translations( 'plugins' );

	$active  = get_option( 'active_plugins', array() );
	$current = get_site_transient( 'update_plugins' );

	if ( ! is_object( $current ) ) {
		$current = new stdClass();
	}

	$doing_cron = wp_doing_cron();

	// Check for update on a different schedule, depending on the page.
	switch ( current_filter() ) {
		case 'upgrader_process_complete':
			$timeout = 0;
			break;
		case 'load-update-core.php':
			$timeout = MINUTE_IN_SECONDS;
			break;
		case 'load-plugins.php':
		case 'load-update.php':
			$timeout = HOUR_IN_SECONDS;
			break;
		default:
			if ( $doing_cron ) {
				$timeout = 2 * HOUR_IN_SECONDS;
			} else {
				$timeout = 12 * HOUR_IN_SECONDS;
			}
	}

	$time_not_changed = isset( $current->last_checked ) && $timeout > ( time() - $current->last_checked );

	if ( $time_not_changed && ! $extra_stats ) {
		$plugin_changed = false;

		foreach ( $plugins as $file => $p ) {
			if ( ! isset( $current->checked[ $file ] ) || (string) $current->checked[ $file ] !== (string) $p['Version'] ) {
				$plugin_changed = true;
			}
		}

		if ( isset( $current->response ) && is_array( $current->response ) ) {
			foreach ( $current->response as $plugin_file => $update_details ) {
				if ( ! isset( $plugins[ $plugin_file ] ) ) {
					$plugin_changed = true;
					break;
				}
			}
		}

		// Bail if we've checked recently and if nothing has changed.
		if ( ! $plugin_changed ) {
			return;
		}
	}

	// Update last_checked for current to prevent multiple blocking requests if request hangs.
	$current->last_checked = time();
	set_site_transient( 'update_plugins', $current );

	$to_send = compact( 'plugins', 'active' );

	$locales = array_values( get_available_languages() );

	/**
	 * Filters the locales requested for plugin translations.
	 *
	 * @since 3.7.0
	 * @since 4.5.0 The default value of the `$locales` parameter changed to include all locales.
	 *
	 * @param string[] $locales Plugin locales. Default is all available locales of the site.
	 */
	$locales = apply_filters( 'plugins_update_check_locales', $locales );
	$locales = array_unique( $locales );

	if ( $doing_cron ) {
		$timeout = 30; // 30 seconds.
	} else {
		// Three seconds, plus one extra second for every 10 plugins.
		$timeout = 3 + (int) ( count( $plugins ) / 10 );
	}

	$options = array(
		'timeout'    => $timeout,
		'body'       => array(
			'plugins'      => wp_json_encode( $to_send ),
			'translations' => wp_json_encode( $translations ),
			'locale'       => wp_json_encode( $locales ),
			'all'          => wp_json_encode( true ),
		),
		'user-agent' => 'WordPress/' . wp_get_wp_version() . '; ' . home_url( '/' ),
	);

	if ( $extra_stats ) {
		$options['body']['update_stats'] = wp_json_encode( $extra_stats );
	}

	$url      = 'https://api.wordpress.org/plugins/update-check/1.1/';
	$http_url = $url;
	$ssl      = wp_http_supports( array( 'ssl' ) );

	if ( $ssl ) {
		$url = set_url_scheme( $url, 'https' );
	}

	$raw_response = wp_remote_post( $url, $options );

	if ( $ssl && is_wp_error( $raw_response ) ) {
		wp_trigger_error(
			__FUNCTION__,
			sprintf(
				/* translators: %s: Support forums URL. */
				__( 'An unexpected error occurred. Something may be wrong with WordPress.org or this server&#8217;s configuration. If you continue to have problems, please try the <a href="%s">support forums</a>.' ),
				__( 'https://wordpress.org/support/forums/' )
			) . ' ' . __( '(WordPress could not establish a secure connection to WordPress.org. Please contact your server administrator.)' ),
			headers_sent() || WP_DEBUG ? E_USER_WARNING : E_USER_NOTICE
		);
		$raw_response = wp_remote_post( $http_url, $options );
	}

	if ( is_wp_error( $raw_response ) || 200 !== wp_remote_retrieve_response_code( $raw_response ) ) {
		return;
	}

	$updates               = new stdClass();
	$updates->last_checked = time();
	$updates->response     = array();
	$updates->translations = array();
	$updates->no_update    = array();
	foreach ( $plugins as $file => $p ) {
		$updates->checked[ $file ] = $p['Version'];
	}

	$response = json_decode( wp_remote_retrieve_body( $raw_response ), true );

	if ( $response && is_array( $response ) ) {
		$updates->response     = $response['plugins'];
		$updates->translations = $response['translations'];
		$updates->no_update    = $response['no_update'];
	}

	// Support updates for any plugins using the `Update URI` header field.
	foreach ( $plugins as $plugin_file => $plugin_data ) {
		if ( ! $plugin_data['UpdateURI'] || isset( $updates->response[ $plugin_file ] ) ) {
			continue;
		}

		$hostname = wp_parse_url( sanitize_url( $plugin_data['UpdateURI'] ), PHP_URL_HOST );

		/**
		 * Filters the update response for a given plugin hostname.
		 *
		 * The dynamic portion of the hook name, `$hostname`, refers to the hostname
		 * of the URI specified in the `Update URI` header field.
		 *
		 * @since 5.8.0
		 *
		 * @param array|false $update {
		 *     The plugin update data with the latest details. Default false.
		 *
		 *     @type string   $id           Optional. ID of the plugin for update purposes, should be a URI
		 *                                  specified in the `Update URI` header field.
		 *     @type string   $slug         Slug of the plugin.
		 *     @type string   $version      The version of the plugin.
		 *     @type string   $url          The URL for details of the plugin.
		 *     @type string   $package      Optional. The update ZIP for the plugin.
		 *     @type string   $tested       Optional. The version of WordPress the plugin is tested against.
		 *     @type string   $requires_php Optional. The version of PHP which the plugin requires.
		 *     @type bool     $autoupdate   Optional. Whether the plugin should automatically update.
		 *     @type string[] $icons        Optional. Array of plugin icons.
		 *     @type string[] $banners      Optional. Array of plugin banners.
		 *     @type string[] $banners_rtl  Optional. Array of plugin RTL banners.
		 *     @type array    $translations {
		 *         Optional. List of translation updates for the plugin.
		 *
		 *         @type string $language   The language the translation update is for.
		 *         @type string $version    The version of the plugin this translation is for.
		 *                                  This is not the version of the language file.
		 *         @type string $updated    The update timestamp of the translation file.
		 *                                  Should be a date in the `YYYY-MM-DD HH:MM:SS` format.
		 *         @type string $package    The ZIP location containing the translation update.
		 *         @type string $autoupdate Whether the translation should be automatically installed.
		 *     }
		 * }
		 * @param array       $plugin_data      Plugin headers.
		 * @param string      $plugin_file      Plugin filename.
		 * @param string[]    $locales          Installed locales to look up translations for.
		 */
		$update = apply_filters( "update_plugins_{$hostname}", false, $plugin_data, $plugin_file, $locales );

		if ( ! $update ) {
			continue;
		}

		$update = (object) $update;

		// Is it valid? We require at least a version.
		if ( ! isset( $update->version ) ) {
			continue;
		}

		// These should remain constant.
		$update->id     = $plugin_data['UpdateURI'];
		$update->plugin = $plugin_file;

		// WordPress needs the version field specified as 'new_version'.
		if ( ! isset( $update->new_version ) ) {
			$update->new_version = $update->version;
		}

		// Handle any translation updates.
		if ( ! empty( $update->translations ) ) {
			foreach ( $update->translations as $translation ) {
				if ( isset( $translation['language'], $translation['package'] ) ) {
					$translation['type'] = 'plugin';
					$translation['slug'] = isset( $update->slug ) ? $update->slug : $update->id;

					$updates->translations[] = $translation;
				}
			}
		}

		unset( $updates->no_update[ $plugin_file ], $updates->response[ $plugin_file ] );

		if ( version_compare( $update->new_version, $plugin_data['Version'], '>' ) ) {
			$updates->response[ $plugin_file ] = $update;
		} else {
			$updates->no_update[ $plugin_file ] = $update;
		}
	}

	$sanitize_plugin_update_payload = static function ( &$item ) {
		$item = (object) $item;

		unset( $item->translations, $item->compatibility );

		return $item;
	};

	array_walk( $updates->response, $sanitize_plugin_update_payload );
	array_walk( $updates->no_update, $sanitize_plugin_update_payload );

	set_site_transient( 'update_plugins', $updates );
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/update.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/update.php#L324) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/update.php#L324-L579)

## [Hooks](https://developer.wordpress.org/reference/functions/wp_update_plugins/\#hooks)

[apply\_filters( ‘plugins\_update\_check\_locales’, string\[\]$locales )](https://developer.wordpress.org/reference/hooks/plugins_update_check_locales/)

Filters the locales requested for plugin translations.

[apply\_filters( “update\_plugins\_{$hostname}”, array\|false$update, array$plugin\_data, string$plugin\_file, string\[\]$locales )](https://developer.wordpress.org/reference/hooks/update_plugins_hostname/)

Filters the update response for a given plugin hostname.

## [Related](https://developer.wordpress.org/reference/functions/wp_update_plugins/\#related)

| Uses | Description |
| --- | --- |
| [wp\_get\_wp\_version()](https://developer.wordpress.org/reference/functions/wp_get_wp_version/) `wp-includes/functions.php` | Returns the current WordPress version. |
| [wp\_trigger\_error()](https://developer.wordpress.org/reference/functions/wp_trigger_error/) `wp-includes/functions.php` | Generates a user-level error/warning/notice/deprecation message. |
| [wp\_doing\_cron()](https://developer.wordpress.org/reference/functions/wp_doing_cron/) `wp-includes/load.php` | Determines whether the current request is a WordPress cron request. |
| [wp\_installing()](https://developer.wordpress.org/reference/functions/wp_installing/) `wp-includes/load.php` | Checks or sets whether WordPress is in “installation” mode. |
| [wp\_parse\_url()](https://developer.wordpress.org/reference/functions/wp_parse_url/) `wp-includes/http.php` | A wrapper for PHP’s parse\_url() function that handles consistency in the return values across PHP versions. |
| [get\_plugins()](https://developer.wordpress.org/reference/functions/get_plugins/) `wp-admin/includes/plugin.php` | Checks the plugins directory and retrieve all plugin files with plugin data. |
| [sanitize\_url()](https://developer.wordpress.org/reference/functions/sanitize_url/) `wp-includes/formatting.php` | Sanitizes a URL for database or redirect usage. |
| [set\_url\_scheme()](https://developer.wordpress.org/reference/functions/set_url_scheme/) `wp-includes/link-template.php` | Sets the scheme for a URL. |
| [wp\_http\_supports()](https://developer.wordpress.org/reference/functions/wp_http_supports/) `wp-includes/http.php` | Determines if there is an HTTP Transport that can process this request. |
| [wp\_remote\_post()](https://developer.wordpress.org/reference/functions/wp_remote_post/) `wp-includes/http.php` | Performs an HTTP request using the POST method and returns its response. |
| [wp\_remote\_retrieve\_response\_code()](https://developer.wordpress.org/reference/functions/wp_remote_retrieve_response_code/) `wp-includes/http.php` | Retrieves only the response code from the raw response. |
| [wp\_remote\_retrieve\_body()](https://developer.wordpress.org/reference/functions/wp_remote_retrieve_body/) `wp-includes/http.php` | Retrieves only the body from the raw response. |
| [current\_filter()](https://developer.wordpress.org/reference/functions/current_filter/) `wp-includes/plugin.php` | Retrieves the name of the current filter hook. |
| [set\_site\_transient()](https://developer.wordpress.org/reference/functions/set_site_transient/) `wp-includes/option.php` | Sets/updates the value of a site transient. |
| [get\_site\_transient()](https://developer.wordpress.org/reference/functions/get_site_transient/) `wp-includes/option.php` | Retrieves the value of a site transient. |
| [wp\_json\_encode()](https://developer.wordpress.org/reference/functions/wp_json_encode/) `wp-includes/functions.php` | Encodes a variable into JSON, with some confidence checks. |
| [home\_url()](https://developer.wordpress.org/reference/functions/home_url/) `wp-includes/link-template.php` | Retrieves the URL for the current site where the front end is accessible. |
| [apply\_filters()](https://developer.wordpress.org/reference/functions/apply_filters/) `wp-includes/plugin.php` | Calls the callback functions that have been added to a filter hook. |
| [get\_option()](https://developer.wordpress.org/reference/functions/get_option/) `wp-includes/option.php` | Retrieves an option value based on an option name. |
| [is\_wp\_error()](https://developer.wordpress.org/reference/functions/is_wp_error/) `wp-includes/load.php` | Checks whether the given variable is a WordPress Error. |

[Show 15 more](https://developer.wordpress.org/reference/functions/wp_update_plugins/#) [Show less](https://developer.wordpress.org/reference/functions/wp_update_plugins/#)

| Used by | Description |
| --- | --- |
| [wp\_ajax\_update\_plugin()](https://developer.wordpress.org/reference/functions/wp_ajax_update_plugin/) `wp-admin/includes/ajax-actions.php` | Handles updating a plugin via AJAX. |
| [WP\_Automatic\_Updater::run()](https://developer.wordpress.org/reference/classes/wp_automatic_updater/run/) `wp-admin/includes/class-wp-automatic-updater.php` | Kicks off the background update process, looping through all pending updates. |
| [install\_plugin\_install\_status()](https://developer.wordpress.org/reference/functions/install_plugin_install_status/) `wp-admin/includes/plugin-install.php` | Determines the status we can perform on a plugin. |
| [\_maybe\_update\_plugins()](https://developer.wordpress.org/reference/functions/_maybe_update_plugins/) `wp-includes/update.php` | Checks the last time plugins were run before checking plugin versions. |

## [Changelog](https://developer.wordpress.org/reference/functions/wp_update_plugins/\#changelog)

| Version | Description |
| --- | --- |
| [2.3.0](https://developer.wordpress.org/reference/since/2.3.0/) | Introduced. |

## User Contributed Notes

You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_update_plugins%2F) before being able to contribute a note or feedback.

Notifications