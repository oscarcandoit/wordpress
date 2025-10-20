---
url: https://developer.wordpress.org/reference/functions/get_transient
scraped_at: 2025-10-20T03:22:48.535Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/get_transient/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

get\_transient()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)get\_transient()

Search

# get\_transient( string$transient ): mixed

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/get_transient/#description)
- [Parameters](https://developer.wordpress.org/reference/functions/get_transient/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/get_transient/#return)
- [More Information](https://developer.wordpress.org/reference/functions/get_transient/#more-information)
- [Source](https://developer.wordpress.org/reference/functions/get_transient/#source)
- [Hooks](https://developer.wordpress.org/reference/functions/get_transient/#hooks)
- [Related](https://developer.wordpress.org/reference/functions/get_transient/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/get_transient/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/functions/get_transient/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/functions/get_transient/#wp--skip-link--target)

Retrieves the value of a transient.

## [Description](https://developer.wordpress.org/reference/functions/get_transient/\#description)

If the transient does not exist, does not have a value, or has expired, then the return value will be false.

## [Parameters](https://developer.wordpress.org/reference/functions/get_transient/\#parameters)

`$transient` stringrequired

Transient name. Expected to not be SQL-escaped.

## [Return](https://developer.wordpress.org/reference/functions/get_transient/\#return)

mixed Value of transient.

## [More Information](https://developer.wordpress.org/reference/functions/get_transient/\#more-information)

$transient parameter should be 172 characters or less in length as WordPress will prefix your name with “\_transient\_” or “\_transient\_timeout\_” in the options table (depending on whether it expires or not). Longer key names will silently fail. See [Trac #15058](https://core.trac.wordpress.org/ticket/15058).

Returned value is the value of transient. If the transient does not exist, does not have a value, or has expired, then get\_transient will return `false`. This should be checked using the identity operator ( === ) instead of the normal equality operator, because an integer value of zero (or other “empty” data) could be the data you’re wanting to store. Because of this “false” value, transients should not be used to hold plain boolean values. Put them into an array or convert them to integers instead.

## [Source](https://developer.wordpress.org/reference/functions/get_transient/\#source)

`wp-includes/option.php`
[Expand code](https://developer.wordpress.org/reference/functions/get_transient/#)

[Copy](https://developer.wordpress.org/reference/functions/get_transient/#)

```php
function get_transient( $transient ) {

	/**
	 * Filters the value of an existing transient before it is retrieved.
	 *
	 * The dynamic portion of the hook name, `$transient`, refers to the transient name.
	 *
	 * Returning a value other than false from the filter will short-circuit retrieval
	 * and return that value instead.
	 *
	 * @since 2.8.0
	 * @since 4.4.0 The `$transient` parameter was added
	 *
	 * @param mixed  $pre_transient The default value to return if the transient does not exist.
	 *                              Any value other than false will short-circuit the retrieval
	 *                              of the transient, and return that value.
	 * @param string $transient     Transient name.
	 */
	$pre = apply_filters( "pre_transient_{$transient}", false, $transient );

	if ( false !== $pre ) {
		return $pre;
	}

	if ( wp_using_ext_object_cache() || wp_installing() ) {
		$value = wp_cache_get( $transient, 'transient' );
	} else {
		$transient_option = '_transient_' . $transient;
		if ( ! wp_installing() ) {
			// If option is not in alloptions, it is not autoloaded and thus has a timeout.
			$alloptions = wp_load_alloptions();

			if ( ! isset( $alloptions[ $transient_option ] ) ) {
				$transient_timeout = '_transient_timeout_' . $transient;
				wp_prime_option_caches( array( $transient_option, $transient_timeout ) );
				$timeout = get_option( $transient_timeout );
				if ( false !== $timeout && $timeout < time() ) {
					delete_option( $transient_option );
					delete_option( $transient_timeout );
					$value = false;
				}
			}
		}

		if ( ! isset( $value ) ) {
			$value = get_option( $transient_option );
		}
	}

	/**
	 * Filters an existing transient's value.
	 *
	 * The dynamic portion of the hook name, `$transient`, refers to the transient name.
	 *
	 * @since 2.8.0
	 * @since 4.4.0 The `$transient` parameter was added
	 *
	 * @param mixed  $value     Value of transient.
	 * @param string $transient Transient name.
	 */
	return apply_filters( "transient_{$transient}", $value, $transient );
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/option.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/option.php#L1431) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/option.php#L1431-L1492)

## [Hooks](https://developer.wordpress.org/reference/functions/get_transient/\#hooks)

[apply\_filters( “pre\_transient\_{$transient}”, mixed$pre\_transient, string$transient )](https://developer.wordpress.org/reference/hooks/pre_transient_transient/)

Filters the value of an existing transient before it is retrieved.

[apply\_filters( “transient\_{$transient}”, mixed$value, string$transient )](https://developer.wordpress.org/reference/hooks/transient_transient/)

Filters an existing transient’s value.

## [Related](https://developer.wordpress.org/reference/functions/get_transient/\#related)

| Uses | Description |
| --- | --- |
| [wp\_prime\_option\_caches()](https://developer.wordpress.org/reference/functions/wp_prime_option_caches/) `wp-includes/option.php` | Primes specific options into the cache with a single database query. |
| [wp\_installing()](https://developer.wordpress.org/reference/functions/wp_installing/) `wp-includes/load.php` | Checks or sets whether WordPress is in “installation” mode. |
| [wp\_using\_ext\_object\_cache()](https://developer.wordpress.org/reference/functions/wp_using_ext_object_cache/) `wp-includes/load.php` | Toggles `$_wp_using_ext_object_cache` on and off without directly touching global. |
| [wp\_load\_alloptions()](https://developer.wordpress.org/reference/functions/wp_load_alloptions/) `wp-includes/option.php` | Loads and caches all autoloaded options, if available or all options. |
| [delete\_option()](https://developer.wordpress.org/reference/functions/delete_option/) `wp-includes/option.php` | Removes an option by name. Prevents removal of protected WordPress options. |
| [wp\_cache\_get()](https://developer.wordpress.org/reference/functions/wp_cache_get/) `wp-includes/cache.php` | Retrieves the cache contents from the cache by key and group. |
| [apply\_filters()](https://developer.wordpress.org/reference/functions/apply_filters/) `wp-includes/plugin.php` | Calls the callback functions that have been added to a filter hook. |
| [get\_option()](https://developer.wordpress.org/reference/functions/get_option/) `wp-includes/option.php` | Retrieves an option value based on an option name. |

[Show 3 more](https://developer.wordpress.org/reference/functions/get_transient/#) [Show less](https://developer.wordpress.org/reference/functions/get_transient/#)

| Used by | Description |
| --- | --- |
| [wp\_add\_global\_styles\_for\_blocks()](https://developer.wordpress.org/reference/functions/wp_add_global_styles_for_blocks/) `wp-includes/global-styles-and-settings.php` | Adds global style rules to the inline style for each block. |
| [clean\_dirsize\_cache()](https://developer.wordpress.org/reference/functions/clean_dirsize_cache/) `wp-includes/functions.php` | Cleans directory size cache used by [recurse\_dirsize()](https://developer.wordpress.org/reference/functions/recurse_dirsize/) . |
| [wp\_dashboard\_site\_health()](https://developer.wordpress.org/reference/functions/wp_dashboard_site_health/) `wp-admin/includes/dashboard.php` | Displays the Site Health Status widget. |
| [WP\_Site\_Health::enqueue\_scripts()](https://developer.wordpress.org/reference/classes/wp_site_health/enqueue_scripts/) `wp-admin/includes/class-wp-site-health.php` | Enqueues the site health scripts. |
| [wp\_start\_scraping\_edited\_file\_errors()](https://developer.wordpress.org/reference/functions/wp_start_scraping_edited_file_errors/) `wp-includes/load.php` | Starts scraping edited file errors. |
| [WP\_oEmbed\_Controller::get\_proxy\_item()](https://developer.wordpress.org/reference/classes/wp_oembed_controller/get_proxy_item/) `wp-includes/class-wp-oembed-controller.php` | Callback for the proxy API endpoint. |
| [install\_themes\_feature\_list()](https://developer.wordpress.org/reference/functions/install_themes_feature_list/) `wp-admin/includes/theme-install.php` | Retrieves the list of WordPress theme features (aka theme tags). |
| [wp\_dashboard\_cached\_rss\_widget()](https://developer.wordpress.org/reference/functions/wp_dashboard_cached_rss_widget/) `wp-admin/includes/dashboard.php` | Checks to see if all of the feed url in $check\_urls are cached. |
| [wp\_dashboard\_plugins\_output()](https://developer.wordpress.org/reference/functions/wp_dashboard_plugins_output/) `wp-admin/includes/deprecated.php` | Display plugins text for the WordPress news widget. |
| [get\_settings\_errors()](https://developer.wordpress.org/reference/functions/get_settings_errors/) `wp-admin/includes/template.php` | Fetches settings errors registered by [add\_settings\_error()](https://developer.wordpress.org/reference/functions/add_settings_error/) . |
| [spawn\_cron()](https://developer.wordpress.org/reference/functions/spawn_cron/) `wp-includes/cron.php` | Sends a request to run cron through HTTP request that doesn’t halt page loading. |
| [wp\_rand()](https://developer.wordpress.org/reference/functions/wp_rand/) `wp-includes/pluggable.php` | Generates a random non-negative number. |
| [WP\_Feed\_Cache\_Transient::load()](https://developer.wordpress.org/reference/classes/wp_feed_cache_transient/load/) `wp-includes/class-wp-feed-cache-transient.php` | Retrieves the data saved in the transient. |
| [WP\_Feed\_Cache\_Transient::mtime()](https://developer.wordpress.org/reference/classes/wp_feed_cache_transient/mtime/) `wp-includes/class-wp-feed-cache-transient.php` | Gets mod transient. |
| [recurse\_dirsize()](https://developer.wordpress.org/reference/functions/recurse_dirsize/) `wp-includes/functions.php` | Gets the size of a directory recursively. |
| [is\_multi\_author()](https://developer.wordpress.org/reference/functions/is_multi_author/) `wp-includes/author-template.php` | Determines whether this site has more than one author. |
| [RSSCache::get()](https://developer.wordpress.org/reference/classes/rsscache/get/) `wp-includes/rss.php` |  |
| [RSSCache::check\_cache()](https://developer.wordpress.org/reference/classes/rsscache/check_cache/) `wp-includes/rss.php` |  |

[Show 13 more](https://developer.wordpress.org/reference/functions/get_transient/#) [Show less](https://developer.wordpress.org/reference/functions/get_transient/#)

## [Changelog](https://developer.wordpress.org/reference/functions/get_transient/\#changelog)

| Version | Description |
| --- | --- |
| [2.8.0](https://developer.wordpress.org/reference/since/2.8.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/functions/get_transient/\#user-contributed-notes)

1. [Skip to note 5 content](https://developer.wordpress.org/reference/functions/get_transient/#comment-content-728)



Example of using `get_transient`, `set_transient` and `WP_Query`





`wp-includes/option.php`
[Copy](https://developer.wordpress.org/reference/functions/get_transient/#)




```php
// Get any existing copy of our transient data
if ( false === ( $special_query_results = get_transient( 'special_query_results' ) ) ) {
   	// It wasn't there, so regenerate the data and save the transient
   	$special_query_results = new WP_Query( 'cat=5&order=random&tag=tech&post_meta_key=thumbnail' );
   	set_transient( 'special_query_results', $special_query_results );
}

// Use the data like you would have normally...
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_transient%2F%3Freplytocom%3D728%23feedback-editor-728)

2. [Skip to note 6 content](https://developer.wordpress.org/reference/functions/get_transient/#comment-content-2822)



**Useful to know:** If the transient exists but has expired, the return value will not _just_ be false. The expired transient will be deleted at the same time.



WordPress does not delete expired transients on its own, but using **[get\_transient()](https://developer.wordpress.org/reference/functions/get_transient/)** on an expired one will do so. Non-expired transients, or transients without expiration will only be deleted with **[delete\_transient()](https://developer.wordpress.org/reference/functions/delete_transient/)**.





[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_transient%2F%3Freplytocom%3D2822%23feedback-editor-2822)

3. [Skip to note 7 content](https://developer.wordpress.org/reference/functions/get_transient/#comment-content-729)



Add `WP_DEBUG` in the conditional statement if you always want live data during development stage





`wp-includes/option.php`
[Copy](https://developer.wordpress.org/reference/functions/get_transient/#)




```php
<?php

if ( WP_DEBUG or false === ( $special_query_results = get_transient( 'special_query_results' ) ) ) ) {
   	// It wasn't there, so regenerate the data and save the transient
   	$special_query_results = new WP_Query( 'cat=5&order=random&tag=tech&post_meta_key=thumbnail' );
   	set_transient( 'special_query_results', $special_query_results );
}

?>
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_transient%2F%3Freplytocom%3D729%23feedback-editor-729)

4. [Skip to note 8 content](https://developer.wordpress.org/reference/functions/get_transient/#comment-content-7086)



Be careful: `get_transient()` might not return the same result whether an object cache is enabled or not.





`wp-includes/option.php`
[Copy](https://developer.wordpress.org/reference/functions/get_transient/#)




```php
$obj = new stdClass();
$obj->test = 'value';
$obj->obj = new stdClass();
$obj->obj->test = 'sub value';
set_transient( 'test_sub_object', $obj );
$obj->test = 'value modified';
$obj->obj->test = 'sub value modified';
$obj_from_transient = get_transient( 'test_sub_object' );
```





Here `$obj_from_transient->obj->test = 'sub value modified'` not `'sub value'` if an object cache is enabled ( `wp_get_cache` is used in that case).





[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_transient%2F%3Freplytocom%3D7086%23feedback-editor-7086)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_transient%2F) before being able to contribute a note or feedback.

Notifications