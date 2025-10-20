---
url: https://developer.wordpress.org/reference/functions/_get_last_post_time
scraped_at: 2025-10-20T03:17:39.499Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/_get_last_post_time/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

\_get\_last\_post\_time()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)\_get\_last\_post\_time()

Search

# \_get\_last\_post\_time( string$timezone, string$field, string$post\_type = 'any' ): string\|false

## In this article

Table of Contents

- [Parameters](https://developer.wordpress.org/reference/functions/_get_last_post_time/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/_get_last_post_time/#return)
- [Source](https://developer.wordpress.org/reference/functions/_get_last_post_time/#source)
- [Related](https://developer.wordpress.org/reference/functions/_get_last_post_time/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/_get_last_post_time/#changelog)

[↑ Back to top](https://developer.wordpress.org/reference/functions/_get_last_post_time/#wp--skip-link--target)

This function’s access is marked private. This means it is not intended for use by plugin or theme developers, only in other core functions. It is listed here for completeness.

Gets the timestamp of the last time any post was modified or published.

## [Parameters](https://developer.wordpress.org/reference/functions/_get_last_post_time/\#parameters)

`$timezone` stringrequired

The timezone for the timestamp. See [get\_lastpostdate()](https://developer.wordpress.org/reference/functions/get_lastpostdate/) .

for information on accepted values.More Arguments from get\_lastpostdate( … $timezone )The timezone for the timestamp. Accepts `'server'`, `'blog'`, or `'gmt'`.

`'server'` uses the server’s internal timezone.

`'blog'` uses the `post_date` field, which proxies to the timezone set for the site.

`'gmt'` uses the `post_date_gmt` field.

Default `'server'`.

`$field` stringrequired

Post field to check. Accepts `'date'` or `'modified'`.

`$post_type` stringoptional

The post type to check. Default `'any'`.

Default: `'any'`

## [Return](https://developer.wordpress.org/reference/functions/_get_last_post_time/\#return)

string\|false The timestamp in ‘Y-m-d H:i:s’ format, or false on failure.

## [Source](https://developer.wordpress.org/reference/functions/_get_last_post_time/\#source)

`wp-includes/post.php`
[Expand code](https://developer.wordpress.org/reference/functions/_get_last_post_time/#)

[Copy](https://developer.wordpress.org/reference/functions/_get_last_post_time/#)

```php
function _get_last_post_time( $timezone, $field, $post_type = 'any' ) {
	global $wpdb;

	if ( ! in_array( $field, array( 'date', 'modified' ), true ) ) {
		return false;
	}

	$timezone = strtolower( $timezone );

	$key = "lastpost{$field}:$timezone";
	if ( 'any' !== $post_type ) {
		$key .= ':' . sanitize_key( $post_type );
	}

	$date = wp_cache_get( $key, 'timeinfo' );
	if ( false !== $date ) {
		return $date;
	}

	if ( 'any' === $post_type ) {
		$post_types = get_post_types( array( 'public' => true ) );
		array_walk( $post_types, array( $wpdb, 'escape_by_ref' ) );
		$post_types = "'" . implode( "', '", $post_types ) . "'";
	} else {
		$post_types = "'" . sanitize_key( $post_type ) . "'";
	}

	switch ( $timezone ) {
		case 'gmt':
			$date = $wpdb->get_var( "SELECT post_{$field}_gmt FROM $wpdb->posts WHERE post_status = 'publish' AND post_type IN ({$post_types}) ORDER BY post_{$field}_gmt DESC LIMIT 1" );
			break;
		case 'blog':
			$date = $wpdb->get_var( "SELECT post_{$field} FROM $wpdb->posts WHERE post_status = 'publish' AND post_type IN ({$post_types}) ORDER BY post_{$field}_gmt DESC LIMIT 1" );
			break;
		case 'server':
			$add_seconds_server = gmdate( 'Z' );
			$date               = $wpdb->get_var( "SELECT DATE_ADD(post_{$field}_gmt, INTERVAL '$add_seconds_server' SECOND) FROM $wpdb->posts WHERE post_status = 'publish' AND post_type IN ({$post_types}) ORDER BY post_{$field}_gmt DESC LIMIT 1" );
			break;
	}

	if ( $date ) {
		wp_cache_set( $key, $date, 'timeinfo' );

		return $date;
	}

	return false;
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/post.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/post.php#L7545) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/post.php#L7545-L7592)

## [Related](https://developer.wordpress.org/reference/functions/_get_last_post_time/\#related)

| Uses | Description |
| --- | --- |
| [wp\_cache\_set()](https://developer.wordpress.org/reference/functions/wp_cache_set/) `wp-includes/cache.php` | Saves the data to the cache. |
| [wp\_cache\_get()](https://developer.wordpress.org/reference/functions/wp_cache_get/) `wp-includes/cache.php` | Retrieves the cache contents from the cache by key and group. |
| [sanitize\_key()](https://developer.wordpress.org/reference/functions/sanitize_key/) `wp-includes/formatting.php` | Sanitizes a string key. |
| [get\_post\_types()](https://developer.wordpress.org/reference/functions/get_post_types/) `wp-includes/post.php` | Gets a list of all registered post type objects. |
| [wpdb::get\_var()](https://developer.wordpress.org/reference/classes/wpdb/get_var/) `wp-includes/class-wpdb.php` | Retrieves one value from the database. |

[Show 3 more](https://developer.wordpress.org/reference/functions/_get_last_post_time/#) [Show less](https://developer.wordpress.org/reference/functions/_get_last_post_time/#)

| Used by | Description |
| --- | --- |
| [get\_lastpostdate()](https://developer.wordpress.org/reference/functions/get_lastpostdate/) `wp-includes/post.php` | Retrieves the most recent time that a post on the site was published. |
| [get\_lastpostmodified()](https://developer.wordpress.org/reference/functions/get_lastpostmodified/) `wp-includes/post.php` | Gets the most recent time that a post on the site was modified. |

## [Changelog](https://developer.wordpress.org/reference/functions/_get_last_post_time/\#changelog)

| Version | Description |
| --- | --- |
| [4.4.0](https://developer.wordpress.org/reference/since/4.4.0/) | The `$post_type` argument was added. |
| [3.1.0](https://developer.wordpress.org/reference/since/3.1.0/) | Introduced. |

## User Contributed Notes

You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2F_get_last_post_time%2F) before being able to contribute a note or feedback.

Notifications