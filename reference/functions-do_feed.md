---
url: https://developer.wordpress.org/reference/functions/do_feed
scraped_at: 2025-10-20T03:13:24.645Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/do_feed/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

do\_feed()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)do\_feed()

Search

# do\_feed()

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/do_feed/#description)
- [Source](https://developer.wordpress.org/reference/functions/do_feed/#source)
- [Hooks](https://developer.wordpress.org/reference/functions/do_feed/#hooks)
- [Related](https://developer.wordpress.org/reference/functions/do_feed/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/do_feed/#changelog)

[↑ Back to top](https://developer.wordpress.org/reference/functions/do_feed/#wp--skip-link--target)

Loads the feed template from the use of an action hook.

## [Description](https://developer.wordpress.org/reference/functions/do_feed/\#description)

If the feed action does not have a hook, then the function will die with a message telling the visitor that the feed is not valid.

It is better to only have one hook for each feed.

## [Source](https://developer.wordpress.org/reference/functions/do_feed/\#source)

`wp-includes/functions.php`
[Expand code](https://developer.wordpress.org/reference/functions/do_feed/#)

[Copy](https://developer.wordpress.org/reference/functions/do_feed/#)

```php
function do_feed() {
	global $wp_query;

	$feed = get_query_var( 'feed' );

	// Remove the pad, if present.
	$feed = preg_replace( '/^_+/', '', $feed );

	if ( '' === $feed || 'feed' === $feed ) {
		$feed = get_default_feed();
	}

	if ( ! has_action( "do_feed_{$feed}" ) ) {
		wp_die( __( '<strong>Error:</strong> This is not a valid feed template.' ), '', array( 'response' => 404 ) );
	}

	/**
	 * Fires once the given feed is loaded.
	 *
	 * The dynamic portion of the hook name, `$feed`, refers to the feed template name.
	 *
	 * Possible hook names include:
	 *
	 *  - `do_feed_atom`
	 *  - `do_feed_rdf`
	 *  - `do_feed_rss`
	 *  - `do_feed_rss2`
	 *
	 * @since 2.1.0
	 * @since 4.4.0 The `$feed` parameter was added.
	 *
	 * @param bool   $is_comment_feed Whether the feed is a comment feed.
	 * @param string $feed            The feed name.
	 */
	do_action( "do_feed_{$feed}", $wp_query->is_comment_feed, $feed );
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/functions.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/functions.php#L1606) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/functions.php#L1606-L1641)

## [Hooks](https://developer.wordpress.org/reference/functions/do_feed/\#hooks)

[do\_action( “do\_feed\_{$feed}”, bool$is\_comment\_feed, string$feed )](https://developer.wordpress.org/reference/hooks/do_feed_feed/)

Fires once the given feed is loaded.

## [Related](https://developer.wordpress.org/reference/functions/do_feed/\#related)

| Uses | Description |
| --- | --- |
| [get\_query\_var()](https://developer.wordpress.org/reference/functions/get_query_var/) `wp-includes/query.php` | Retrieves the value of a query variable in the [WP\_Query](https://developer.wordpress.org/reference/classes/wp_query/) class. |
| [has\_action()](https://developer.wordpress.org/reference/functions/has_action/) `wp-includes/plugin.php` | Checks if any action has been registered for a hook. |
| [get\_default\_feed()](https://developer.wordpress.org/reference/functions/get_default_feed/) `wp-includes/feed.php` | Retrieves the default feed. |
| [wp\_die()](https://developer.wordpress.org/reference/functions/wp_die/) `wp-includes/functions.php` | Kills WordPress execution and displays HTML page with an error message. |
| [do\_action()](https://developer.wordpress.org/reference/functions/do_action/) `wp-includes/plugin.php` | Calls the callback functions that have been added to an action hook. |

[Show 2 more](https://developer.wordpress.org/reference/functions/do_feed/#) [Show less](https://developer.wordpress.org/reference/functions/do_feed/#)

## [Changelog](https://developer.wordpress.org/reference/functions/do_feed/\#changelog)

| Version | Description |
| --- | --- |
| [2.1.0](https://developer.wordpress.org/reference/since/2.1.0/) | Introduced. |

## User Contributed Notes

You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fdo_feed%2F) before being able to contribute a note or feedback.

Notifications