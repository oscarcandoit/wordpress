---
url: https://developer.wordpress.org/reference/functions/wp_get_nocache_headers
scraped_at: 2025-10-20T03:16:37.150Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/wp_get_nocache_headers/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp\_get\_nocache\_headers()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)wp\_get\_nocache\_headers()

Search

# wp\_get\_nocache\_headers(): array

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/wp_get_nocache_headers/#description)
- [Return](https://developer.wordpress.org/reference/functions/wp_get_nocache_headers/#return)
- [Source](https://developer.wordpress.org/reference/functions/wp_get_nocache_headers/#source)
- [Hooks](https://developer.wordpress.org/reference/functions/wp_get_nocache_headers/#hooks)
- [Related](https://developer.wordpress.org/reference/functions/wp_get_nocache_headers/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/wp_get_nocache_headers/#changelog)

[↑ Back to top](https://developer.wordpress.org/reference/functions/wp_get_nocache_headers/#wp--skip-link--target)

Gets the HTTP header information to prevent caching.

## [Description](https://developer.wordpress.org/reference/functions/wp_get_nocache_headers/\#description)

The several different headers cover the different ways cache prevention is handled by different browsers or intermediate caches such as proxy servers.

## [Return](https://developer.wordpress.org/reference/functions/wp_get_nocache_headers/\#return)

array The associative array of header names and field values.

## [Source](https://developer.wordpress.org/reference/functions/wp_get_nocache_headers/\#source)

`wp-includes/functions.php`
[Expand code](https://developer.wordpress.org/reference/functions/wp_get_nocache_headers/#)

[Copy](https://developer.wordpress.org/reference/functions/wp_get_nocache_headers/#)

```php
function wp_get_nocache_headers() {
	$cache_control = 'no-cache, must-revalidate, max-age=0, no-store, private';

	$headers = array(
		'Expires'       => 'Wed, 11 Jan 1984 05:00:00 GMT',
		'Cache-Control' => $cache_control,
	);

	if ( function_exists( 'apply_filters' ) ) {
		/**
		 * Filters the cache-controlling HTTP headers that are used to prevent caching.
		 *
		 * @since 2.8.0
		 *
		 * @see wp_get_nocache_headers()
		 *
		 * @param array $headers Header names and field values.
		 */
		$headers = (array) apply_filters( 'nocache_headers', $headers );
	}
	$headers['Last-Modified'] = false;
	return $headers;
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/functions.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/functions.php#L1502) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/functions.php#L1502-L1524)

## [Hooks](https://developer.wordpress.org/reference/functions/wp_get_nocache_headers/\#hooks)

[apply\_filters( ‘nocache\_headers’, array$headers )](https://developer.wordpress.org/reference/hooks/nocache_headers/)

Filters the cache-controlling HTTP headers that are used to prevent caching.

## [Related](https://developer.wordpress.org/reference/functions/wp_get_nocache_headers/\#related)

| Uses | Description |
| --- | --- |
| [apply\_filters()](https://developer.wordpress.org/reference/functions/apply_filters/) `wp-includes/plugin.php` | Calls the callback functions that have been added to a filter hook. |

| Used by | Description |
| --- | --- |
| [WP\_REST\_Server::serve\_request()](https://developer.wordpress.org/reference/classes/wp_rest_server/serve_request/) `wp-includes/rest-api/class-wp-rest-server.php` | Handles serving a REST API request. |
| [WP::send\_headers()](https://developer.wordpress.org/reference/classes/wp/send_headers/) `wp-includes/class-wp.php` | Sends additional HTTP headers for caching, content type, etc. |
| [nocache\_headers()](https://developer.wordpress.org/reference/functions/nocache_headers/) `wp-includes/functions.php` | Sets the HTTP headers to prevent caching for the different browsers. |

## [Changelog](https://developer.wordpress.org/reference/functions/wp_get_nocache_headers/\#changelog)

| Version | Description |
| --- | --- |
| [6.8.0](https://developer.wordpress.org/reference/since/6.8.0/) | The `Cache-Control` header now includes the `no-store` and `private` directives regardless of whether a user is logged in. |
| [6.3.0](https://developer.wordpress.org/reference/since/6.3.0/) | The `Cache-Control` header for logged in users now includes the `no-store` and `private` directives. |
| [2.8.0](https://developer.wordpress.org/reference/since/2.8.0/) | Introduced. |

## User Contributed Notes

You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_get_nocache_headers%2F) before being able to contribute a note or feedback.

Notifications