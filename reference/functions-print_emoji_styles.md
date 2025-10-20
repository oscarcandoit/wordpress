---
url: https://developer.wordpress.org/reference/functions/print_emoji_styles
scraped_at: 2025-10-20T03:18:29.504Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/print_emoji_styles/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

print\_emoji\_styles()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)print\_emoji\_styles()

Search

# print\_emoji\_styles()

## In this article

Table of Contents

- [Source](https://developer.wordpress.org/reference/functions/print_emoji_styles/#source)
- [Related](https://developer.wordpress.org/reference/functions/print_emoji_styles/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/print_emoji_styles/#changelog)

[↑ Back to top](https://developer.wordpress.org/reference/functions/print_emoji_styles/#wp--skip-link--target)

This function has been deprecated. Use wp\_enqueue\_emoji\_styles() instead.

Prints the important emoji-related styles.

## [Source](https://developer.wordpress.org/reference/functions/print_emoji_styles/\#source)

`wp-includes/deprecated.php`
[Expand code](https://developer.wordpress.org/reference/functions/print_emoji_styles/#)

[Copy](https://developer.wordpress.org/reference/functions/print_emoji_styles/#)

```php
function print_emoji_styles() {
	_deprecated_function( __FUNCTION__, '6.4.0', 'wp_enqueue_emoji_styles' );
	static $printed = false;

	if ( $printed ) {
		return;
	}

	$printed = true;

	$type_attr = current_theme_supports( 'html5', 'style' ) ? '' : ' type="text/css"';
	?>
	<style<?php echo $type_attr; ?>>
	img.wp-smiley,
	img.emoji {
		display: inline !important;
		border: none !important;
		box-shadow: none !important;
		height: 1em !important;
		width: 1em !important;
		margin: 0 0.07em !important;
		vertical-align: -0.1em !important;
		background: none !important;
		padding: 0 !important;
	}
	</style>
	<?php
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/deprecated.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/deprecated.php#L5915) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/deprecated.php#L5915-L5942)

## [Related](https://developer.wordpress.org/reference/functions/print_emoji_styles/\#related)

| Uses | Description |
| --- | --- |
| [current\_theme\_supports()](https://developer.wordpress.org/reference/functions/current_theme_supports/) `wp-includes/theme.php` | Checks a theme’s support for a given feature. |
| [\_deprecated\_function()](https://developer.wordpress.org/reference/functions/_deprecated_function/) `wp-includes/functions.php` | Marks a function as deprecated and inform when it has been used. |

## [Changelog](https://developer.wordpress.org/reference/functions/print_emoji_styles/\#changelog)

| Version | Description |
| --- | --- |
| [6.4.0](https://developer.wordpress.org/reference/since/6.4.0/) | Use [wp\_enqueue\_emoji\_styles()](https://developer.wordpress.org/reference/functions/wp_enqueue_emoji_styles/) instead. |
| [4.2.0](https://developer.wordpress.org/reference/since/4.2.0/) | Introduced. |

## User Contributed Notes

You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fprint_emoji_styles%2F) before being able to contribute a note or feedback.

Notifications