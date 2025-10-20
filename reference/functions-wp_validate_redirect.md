---
url: https://developer.wordpress.org/reference/functions/wp_validate_redirect
scraped_at: 2025-10-20T03:14:50.759Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/wp_validate_redirect/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp\_validate\_redirect()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)wp\_validate\_redirect()

Search

# wp\_validate\_redirect( string$location, string$fallback\_url = '' ): string

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/wp_validate_redirect/#description)
- [Parameters](https://developer.wordpress.org/reference/functions/wp_validate_redirect/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/wp_validate_redirect/#return)
- [Source](https://developer.wordpress.org/reference/functions/wp_validate_redirect/#source)
- [Hooks](https://developer.wordpress.org/reference/functions/wp_validate_redirect/#hooks)
- [Related](https://developer.wordpress.org/reference/functions/wp_validate_redirect/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/wp_validate_redirect/#changelog)

[↑ Back to top](https://developer.wordpress.org/reference/functions/wp_validate_redirect/#wp--skip-link--target)

Validates a URL for use in a redirect.

## [Description](https://developer.wordpress.org/reference/functions/wp_validate_redirect/\#description)

Checks whether the $location is using an allowed host, if it has an absolute path. A plugin can therefore set or remove allowed host(s) to or from the list.

If the host is not allowed, then the redirect is to $fallback\_url supplied.

## [Parameters](https://developer.wordpress.org/reference/functions/wp_validate_redirect/\#parameters)

`$location` stringrequired

The redirect to validate.

`$fallback_url` stringoptional

The value to return if $location is not allowed.

Default: `''`

## [Return](https://developer.wordpress.org/reference/functions/wp_validate_redirect/\#return)

string Redirect-sanitized URL.

## [Source](https://developer.wordpress.org/reference/functions/wp_validate_redirect/\#source)

`wp-includes/pluggable.php`
[Expand code](https://developer.wordpress.org/reference/functions/wp_validate_redirect/#)

[Copy](https://developer.wordpress.org/reference/functions/wp_validate_redirect/#)

```php
function wp_validate_redirect( $location, $fallback_url = '' ) {
	$location = wp_sanitize_redirect( trim( $location, " \t\n\r\0\x08\x0B" ) );
	// Browsers will assume 'http' is your protocol, and will obey a redirect to a URL starting with '//'.
	if ( str_starts_with( $location, '//' ) ) {
		$location = 'http:' . $location;
	}

	/*
	 * In PHP 5 parse_url() may fail if the URL query part contains 'http://'.
	 * See https://bugs.php.net/bug.php?id=38143
	 */
	$cut  = strpos( $location, '?' );
	$test = $cut ? substr( $location, 0, $cut ) : $location;

	$lp = parse_url( $test );

	// Give up if malformed URL.
	if ( false === $lp ) {
		return $fallback_url;
	}

	// Allow only 'http' and 'https' schemes. No 'data:', etc.
	if ( isset( $lp['scheme'] ) && ! ( 'http' === $lp['scheme'] || 'https' === $lp['scheme'] ) ) {
		return $fallback_url;
	}

	if ( ! isset( $lp['host'] ) && ! empty( $lp['path'] ) && '/' !== $lp['path'][0] ) {
		$path = '';
		if ( ! empty( $_SERVER['REQUEST_URI'] ) ) {
			$path = dirname( parse_url( 'http://placeholder' . $_SERVER['REQUEST_URI'], PHP_URL_PATH ) . '?' );
			$path = wp_normalize_path( $path );
		}
		$location = '/' . ltrim( $path . '/', '/' ) . $location;
	}

	/*
	 * Reject if certain components are set but host is not.
	 * This catches URLs like https:host.com for which parse_url() does not set the host field.
	 */
	if ( ! isset( $lp['host'] ) && ( isset( $lp['scheme'] ) || isset( $lp['user'] ) || isset( $lp['pass'] ) || isset( $lp['port'] ) ) ) {
		return $fallback_url;
	}

	// Reject malformed components parse_url() can return on odd inputs.
	foreach ( array( 'user', 'pass', 'host' ) as $component ) {
		if ( isset( $lp[ $component ] ) && strpbrk( $lp[ $component ], ':/?#@' ) ) {
			return $fallback_url;
		}
	}

	$wpp = parse_url( home_url() );

	/**
	 * Filters the list of allowed hosts to redirect to.
	 *
	 * @since 2.3.0
	 *
	 * @param string[] $hosts An array of allowed host names.
	 * @param string   $host  The host name of the redirect destination; empty string if not set.
	 */
	$allowed_hosts = (array) apply_filters( 'allowed_redirect_hosts', array( $wpp['host'] ), isset( $lp['host'] ) ? $lp['host'] : '' );

	if ( isset( $lp['host'] ) && ( ! in_array( $lp['host'], $allowed_hosts, true ) && strtolower( $wpp['host'] ) !== $lp['host'] ) ) {
		$location = $fallback_url;
	}

	return $location;
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/pluggable.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/pluggable.php#L1580) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/pluggable.php#L1580-L1647)

## [Hooks](https://developer.wordpress.org/reference/functions/wp_validate_redirect/\#hooks)

[apply\_filters( ‘allowed\_redirect\_hosts’, string\[\]$hosts, string$host )](https://developer.wordpress.org/reference/hooks/allowed_redirect_hosts/)

Filters the list of allowed hosts to redirect to.

## [Related](https://developer.wordpress.org/reference/functions/wp_validate_redirect/\#related)

| Uses | Description |
| --- | --- |
| [wp\_sanitize\_redirect()](https://developer.wordpress.org/reference/functions/wp_sanitize_redirect/) `wp-includes/pluggable.php` | Sanitizes a URL for use in a redirect. |
| [wp\_normalize\_path()](https://developer.wordpress.org/reference/functions/wp_normalize_path/) `wp-includes/functions.php` | Normalizes a filesystem path. |
| [home\_url()](https://developer.wordpress.org/reference/functions/home_url/) `wp-includes/link-template.php` | Retrieves the URL for the current site where the front end is accessible. |
| [apply\_filters()](https://developer.wordpress.org/reference/functions/apply_filters/) `wp-includes/plugin.php` | Calls the callback functions that have been added to a filter hook. |

[Show 2 more](https://developer.wordpress.org/reference/functions/wp_validate_redirect/#) [Show less](https://developer.wordpress.org/reference/functions/wp_validate_redirect/#)

| Used by | Description |
| --- | --- |
| [WP\_Customize\_Manager::set\_return\_url()](https://developer.wordpress.org/reference/classes/wp_customize_manager/set_return_url/) `wp-includes/class-wp-customize-manager.php` | Sets URL to link the user to when closing the Customizer. |
| [WP\_Customize\_Manager::set\_preview\_url()](https://developer.wordpress.org/reference/classes/wp_customize_manager/set_preview_url/) `wp-includes/class-wp-customize-manager.php` | Sets the initial URL to be previewed. |
| [wp\_safe\_redirect()](https://developer.wordpress.org/reference/functions/wp_safe_redirect/) `wp-includes/pluggable.php` | Performs a safe (local) redirect, using [wp\_redirect()](https://developer.wordpress.org/reference/functions/wp_redirect/) . |
| [wp\_nonce\_ays()](https://developer.wordpress.org/reference/functions/wp_nonce_ays/) `wp-includes/functions.php` | Displays “Are You Sure” message to confirm the action being taken. |
| [wp\_get\_referer()](https://developer.wordpress.org/reference/functions/wp_get_referer/) `wp-includes/functions.php` | Retrieves referer from ‘\_wp\_http\_referer’ or HTTP referer. |
| [wp\_get\_original\_referer()](https://developer.wordpress.org/reference/functions/wp_get_original_referer/) `wp-includes/functions.php` | Retrieves original referer that was posted, if it exists. |
| [allowed\_http\_request\_hosts()](https://developer.wordpress.org/reference/functions/allowed_http_request_hosts/) `wp-includes/http.php` | Marks allowed redirect hosts safe for HTTP requests as well. |

[Show 2 more](https://developer.wordpress.org/reference/functions/wp_validate_redirect/#) [Show less](https://developer.wordpress.org/reference/functions/wp_validate_redirect/#)

## [Changelog](https://developer.wordpress.org/reference/functions/wp_validate_redirect/\#changelog)

| Version | Description |
| --- | --- |
| [2.8.1](https://developer.wordpress.org/reference/since/2.8.1/) | Introduced. |

## User Contributed Notes

You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_validate_redirect%2F) before being able to contribute a note or feedback.

Notifications