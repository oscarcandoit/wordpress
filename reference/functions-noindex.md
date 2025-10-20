---
url: https://developer.wordpress.org/reference/functions/noindex
scraped_at: 2025-10-20T03:21:28.380Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/noindex/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

noindex()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)noindex()

Search

# noindex()

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/noindex/#description)
  - [See also](https://developer.wordpress.org/reference/functions/noindex/#see-also)
- [Source](https://developer.wordpress.org/reference/functions/noindex/#source)
- [Related](https://developer.wordpress.org/reference/functions/noindex/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/noindex/#changelog)

[↑ Back to top](https://developer.wordpress.org/reference/functions/noindex/#wp--skip-link--target)

This function has been deprecated. Use [wp\_no\_robots()](https://developer.wordpress.org/reference/functions/wp_no_robots) instead.

Displays a `noindex` meta tag if required by the blog configuration.

## [Description](https://developer.wordpress.org/reference/functions/noindex/\#description)

If a blog is marked as not being public then the `noindex` meta tag will be output to tell web robots not to index the page content.

Typical usage is as a [‘wp\_head’](https://developer.wordpress.org/reference/hooks/wp_head/) callback:

`wp-includes/deprecated.php`
[Copy](https://developer.wordpress.org/reference/functions/noindex/#)

```php
add_action( 'wp_head', 'noindex' );
```

### [See also](https://developer.wordpress.org/reference/functions/noindex/\#see-also)

- [wp\_no\_robots()](https://developer.wordpress.org/reference/functions/wp_no_robots)

## [Source](https://developer.wordpress.org/reference/functions/noindex/\#source)

`wp-includes/deprecated.php`
[Copy](https://developer.wordpress.org/reference/functions/noindex/#)

```php
function noindex() {
	_deprecated_function( __FUNCTION__, '5.7.0', 'wp_robots_noindex()' );

	// If the blog is not public, tell robots to go away.
	if ( '0' == get_option( 'blog_public' ) ) {
		wp_no_robots();
	}
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/deprecated.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/deprecated.php#L4155) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/deprecated.php#L4155-L4162)

## [Related](https://developer.wordpress.org/reference/functions/noindex/\#related)

| Uses | Description |
| --- | --- |
| [wp\_no\_robots()](https://developer.wordpress.org/reference/functions/wp_no_robots/) `wp-includes/deprecated.php` | Display a `noindex` meta tag. |
| [\_deprecated\_function()](https://developer.wordpress.org/reference/functions/_deprecated_function/) `wp-includes/functions.php` | Marks a function as deprecated and inform when it has been used. |
| [get\_option()](https://developer.wordpress.org/reference/functions/get_option/) `wp-includes/option.php` | Retrieves an option value based on an option name. |

[Show 1 more](https://developer.wordpress.org/reference/functions/noindex/#) [Show less](https://developer.wordpress.org/reference/functions/noindex/#)

## [Changelog](https://developer.wordpress.org/reference/functions/noindex/\#changelog)

| Version | Description |
| --- | --- |
| [5.7.0](https://developer.wordpress.org/reference/since/5.7.0/) | Use [wp\_robots\_noindex()](https://developer.wordpress.org/reference/functions/wp_robots_noindex/) instead on `'wp_robots'` filter. |
| [2.1.0](https://developer.wordpress.org/reference/since/2.1.0/) | Introduced. |

## User Contributed Notes

You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fnoindex%2F) before being able to contribute a note or feedback.

Notifications