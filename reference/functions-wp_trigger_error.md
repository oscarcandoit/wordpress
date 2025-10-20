---
url: https://developer.wordpress.org/reference/functions/wp_trigger_error
scraped_at: 2025-10-20T03:15:14.246Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/wp_trigger_error/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp\_trigger\_error()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)wp\_trigger\_error()

Search

# wp\_trigger\_error( string$function\_name, string$message, int$error\_level = E\_USER\_NOTICE )

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/wp_trigger_error/#description)
- [Parameters](https://developer.wordpress.org/reference/functions/wp_trigger_error/#parameters)
- [Source](https://developer.wordpress.org/reference/functions/wp_trigger_error/#source)
- [Hooks](https://developer.wordpress.org/reference/functions/wp_trigger_error/#hooks)
- [Related](https://developer.wordpress.org/reference/functions/wp_trigger_error/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/wp_trigger_error/#changelog)

[↑ Back to top](https://developer.wordpress.org/reference/functions/wp_trigger_error/#wp--skip-link--target)

Generates a user-level error/warning/notice/deprecation message.

## [Description](https://developer.wordpress.org/reference/functions/wp_trigger_error/\#description)

Generates the message when `WP_DEBUG` is true.

## [Parameters](https://developer.wordpress.org/reference/functions/wp_trigger_error/\#parameters)

`$function_name` stringrequired

The function that triggered the error.

`$message` stringrequired

The message explaining the error.

The message can contain allowed HTML `'a'` (with href), `'code'`, `'br'`, `'em'`, and `'strong'` tags and http or https protocols.

If it contains other HTML tags or protocols, the message should be escaped before passing to this function to avoid being stripped [wp\_kses()](https://developer.wordpress.org/reference/functions/wp_kses).

`$error_level` intoptional

The designated error type for this error.

Only works with E\_USER family of constants.

Default: `E_USER_NOTICE`

## [Source](https://developer.wordpress.org/reference/functions/wp_trigger_error/\#source)

`wp-includes/functions.php`
[Expand code](https://developer.wordpress.org/reference/functions/wp_trigger_error/#)

[Copy](https://developer.wordpress.org/reference/functions/wp_trigger_error/#)

```php
function wp_trigger_error( $function_name, $message, $error_level = E_USER_NOTICE ) {

	// Bail out if WP_DEBUG is not turned on.
	if ( ! WP_DEBUG ) {
		return;
	}

	/**
	 * Fires when the given function triggers a user-level error/warning/notice/deprecation message.
	 *
	 * Can be used for debug backtracking.
	 *
	 * @since 6.4.0
	 *
	 * @param string $function_name The function that was called.
	 * @param string $message       A message explaining what has been done incorrectly.
	 * @param int    $error_level   The designated error type for this error.
	 */
	do_action( 'wp_trigger_error_run', $function_name, $message, $error_level );

	if ( ! empty( $function_name ) ) {
		$message = sprintf( '%s(): %s', $function_name, $message );
	}

	$message = wp_kses(
		$message,
		array(
			'a'      => array( 'href' => true ),
			'br'     => array(),
			'code'   => array(),
			'em'     => array(),
			'strong' => array(),
		),
		array( 'http', 'https' )
	);

	if ( E_USER_ERROR === $error_level ) {
		throw new WP_Exception( $message );
	}

	trigger_error( $message, $error_level );
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/functions.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/functions.php#L6081) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/functions.php#L6081-L6122)

## [Hooks](https://developer.wordpress.org/reference/functions/wp_trigger_error/\#hooks)

[do\_action( ‘wp\_trigger\_error\_run’, string$function\_name, string$message, int$error\_level )](https://developer.wordpress.org/reference/hooks/wp_trigger_error_run/)

Fires when the given function triggers a user-level error/warning/notice/deprecation message.

## [Related](https://developer.wordpress.org/reference/functions/wp_trigger_error/\#related)

| Uses | Description |
| --- | --- |
| [wp\_kses()](https://developer.wordpress.org/reference/functions/wp_kses/) `wp-includes/kses.php` | Filters text content and strips out disallowed HTML. |
| [do\_action()](https://developer.wordpress.org/reference/functions/do_action/) `wp-includes/plugin.php` | Calls the callback functions that have been added to an action hook. |

| Used by | Description |
| --- | --- |
| [wp\_unique\_prefixed\_id()](https://developer.wordpress.org/reference/functions/wp_unique_prefixed_id/) `wp-includes/functions.php` | Generates an incremental ID that is independent per each different prefix. |
| [\_deprecated\_class()](https://developer.wordpress.org/reference/functions/_deprecated_class/) `wp-includes/functions.php` | Marks a class as deprecated and informs when it has been used. |
| [\_wp\_delete\_all\_temp\_backups()](https://developer.wordpress.org/reference/functions/_wp_delete_all_temp_backups/) `wp-includes/update.php` | Deletes all contents in the temporary backup directory. |
| [wp\_opcache\_invalidate\_directory()](https://developer.wordpress.org/reference/functions/wp_opcache_invalidate_directory/) `wp-admin/includes/file.php` | Attempts to clear the opcode cache for a directory of files. |
| [WP\_Theme\_JSON\_Resolver::get\_user\_data()](https://developer.wordpress.org/reference/classes/wp_theme_json_resolver/get_user_data/) `wp-includes/class-wp-theme-json-resolver.php` | Returns the user’s origin config. |
| [wp\_json\_file\_decode()](https://developer.wordpress.org/reference/functions/wp_json_file_decode/) `wp-includes/functions.php` | Reads and decodes a JSON file. |
| [\_filter\_block\_template\_part\_area()](https://developer.wordpress.org/reference/functions/_filter_block_template_part_area/) `wp-includes/block-template-utils.php` | Checks whether the input ‘area’ is a supported value. |
| [clean\_dirsize\_cache()](https://developer.wordpress.org/reference/functions/clean_dirsize_cache/) `wp-includes/functions.php` | Cleans directory size cache used by [recurse\_dirsize()](https://developer.wordpress.org/reference/functions/recurse_dirsize/) . |
| [\_deprecated\_hook()](https://developer.wordpress.org/reference/functions/_deprecated_hook/) `wp-includes/functions.php` | Marks a deprecated action or filter hook as deprecated and throws a notice. |
| [\_deprecated\_constructor()](https://developer.wordpress.org/reference/functions/_deprecated_constructor/) `wp-includes/functions.php` | Marks a constructor as deprecated and informs when it has been used. |
| [MagpieRSS::\_\_construct()](https://developer.wordpress.org/reference/classes/magpierss/__construct/) `wp-includes/rss.php` | PHP5 constructor. |
| [WP\_Text\_Diff\_Renderer\_Table::\_\_unset()](https://developer.wordpress.org/reference/classes/wp_text_diff_renderer_table/__unset/) `wp-includes/class-wp-text-diff-renderer-table.php` | Make private properties un-settable for backward compatibility. |
| [WP\_Text\_Diff\_Renderer\_Table::\_\_get()](https://developer.wordpress.org/reference/classes/wp_text_diff_renderer_table/__get/) `wp-includes/class-wp-text-diff-renderer-table.php` | Make private properties readable for backward compatibility. |
| [WP\_Text\_Diff\_Renderer\_Table::\_\_set()](https://developer.wordpress.org/reference/classes/wp_text_diff_renderer_table/__set/) `wp-includes/class-wp-text-diff-renderer-table.php` | Make private properties settable for backward compatibility. |
| [WP\_Text\_Diff\_Renderer\_Table::\_\_isset()](https://developer.wordpress.org/reference/classes/wp_text_diff_renderer_table/__isset/) `wp-includes/class-wp-text-diff-renderer-table.php` | Make private properties checkable for backward compatibility. |
| [WP\_User\_Query::\_\_get()](https://developer.wordpress.org/reference/classes/wp_user_query/__get/) `wp-includes/class-wp-user-query.php` | Makes private properties readable for backward compatibility. |
| [WP\_User\_Query::\_\_set()](https://developer.wordpress.org/reference/classes/wp_user_query/__set/) `wp-includes/class-wp-user-query.php` | Makes private properties settable for backward compatibility. |
| [WP\_User\_Query::\_\_isset()](https://developer.wordpress.org/reference/classes/wp_user_query/__isset/) `wp-includes/class-wp-user-query.php` | Makes private properties checkable for backward compatibility. |
| [WP\_User\_Query::\_\_unset()](https://developer.wordpress.org/reference/classes/wp_user_query/__unset/) `wp-includes/class-wp-user-query.php` | Makes private properties un-settable for backward compatibility. |
| [WP\_List\_Table::\_\_get()](https://developer.wordpress.org/reference/classes/wp_list_table/__get/) `wp-admin/includes/class-wp-list-table.php` | Makes private properties readable for backward compatibility. |
| [WP\_List\_Table::\_\_set()](https://developer.wordpress.org/reference/classes/wp_list_table/__set/) `wp-admin/includes/class-wp-list-table.php` | Makes private properties settable for backward compatibility. |
| [WP\_List\_Table::\_\_isset()](https://developer.wordpress.org/reference/classes/wp_list_table/__isset/) `wp-admin/includes/class-wp-list-table.php` | Makes private properties checkable for backward compatibility. |
| [WP\_List\_Table::\_\_unset()](https://developer.wordpress.org/reference/classes/wp_list_table/__unset/) `wp-admin/includes/class-wp-list-table.php` | Makes private properties un-settable for backward compatibility. |
| [translations\_api()](https://developer.wordpress.org/reference/functions/translations_api/) `wp-admin/includes/translation-install.php` | Retrieve translations from WordPress Translation API. |
| [WP\_Upgrader::maintenance\_mode()](https://developer.wordpress.org/reference/classes/wp_upgrader/maintenance_mode/) `wp-admin/includes/class-wp-upgrader.php` | Toggles maintenance mode for the site. |
| [themes\_api()](https://developer.wordpress.org/reference/functions/themes_api/) `wp-admin/includes/theme.php` | Retrieves theme installer pages from the WordPress.org Themes API. |
| [get\_core\_checksums()](https://developer.wordpress.org/reference/functions/get_core_checksums/) `wp-admin/includes/update.php` | Gets and caches the checksums for the given version of WordPress. |
| [plugins\_api()](https://developer.wordpress.org/reference/functions/plugins_api/) `wp-admin/includes/plugin-install.php` | Retrieves plugin installer pages from the WordPress.org Plugins API. |
| [search\_theme\_directories()](https://developer.wordpress.org/reference/functions/search_theme_directories/) `wp-includes/theme.php` | Searches all registered theme directories for complete and valid themes. |
| [wp\_strip\_all\_tags()](https://developer.wordpress.org/reference/functions/wp_strip_all_tags/) `wp-includes/formatting.php` | Properly strips all HTML tags including ‘script’ and ‘style’. |
| [\_deprecated\_function()](https://developer.wordpress.org/reference/functions/_deprecated_function/) `wp-includes/functions.php` | Marks a function as deprecated and inform when it has been used. |
| [\_deprecated\_file()](https://developer.wordpress.org/reference/functions/_deprecated_file/) `wp-includes/functions.php` | Marks a file as deprecated and inform when it has been used. |
| [\_doing\_it\_wrong()](https://developer.wordpress.org/reference/functions/_doing_it_wrong/) `wp-includes/functions.php` | Marks something as being incorrectly called. |
| [\_deprecated\_argument()](https://developer.wordpress.org/reference/functions/_deprecated_argument/) `wp-includes/functions.php` | Marks a function argument as deprecated and inform when it has been used. |
| [wp\_version\_check()](https://developer.wordpress.org/reference/functions/wp_version_check/) `wp-includes/update.php` | Checks WordPress version against the newest version. |
| [wp\_update\_plugins()](https://developer.wordpress.org/reference/functions/wp_update_plugins/) `wp-includes/update.php` | Checks for available updates to plugins based on the latest versions hosted on WordPress.org. |
| [wp\_update\_themes()](https://developer.wordpress.org/reference/functions/wp_update_themes/) `wp-includes/update.php` | Checks for available updates to themes based on the latest versions hosted on WordPress.org. |
| [prep\_atom\_text\_construct()](https://developer.wordpress.org/reference/functions/prep_atom_text_construct/) `wp-includes/feed.php` | Determines the type of a string of data with the data formatted. |
| [RSSCache::error()](https://developer.wordpress.org/reference/classes/rsscache/error/) `wp-includes/rss.php` |  |
| [MagpieRSS::error()](https://developer.wordpress.org/reference/classes/magpierss/error/) `wp-includes/rss.php` |  |
| [ms\_subdomain\_constants()](https://developer.wordpress.org/reference/functions/ms_subdomain_constants/) `wp-includes/ms-default-constants.php` | Defines Multisite subdomain constants and handles warnings and notices. |

[Show 36 more](https://developer.wordpress.org/reference/functions/wp_trigger_error/#) [Show less](https://developer.wordpress.org/reference/functions/wp_trigger_error/#)

## [Changelog](https://developer.wordpress.org/reference/functions/wp_trigger_error/\#changelog)

| Version | Description |
| --- | --- |
| [6.4.0](https://developer.wordpress.org/reference/since/6.4.0/) | Introduced. |

## User Contributed Notes

You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_trigger_error%2F) before being able to contribute a note or feedback.

Notifications