---
url: https://developer.wordpress.org/reference/functions/wp_filesize
scraped_at: 2025-10-20T03:16:05.921Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/wp_filesize/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp\_filesize()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)wp\_filesize()

Search

# wp\_filesize( string$path ): int

## In this article

Table of Contents

- [Parameters](https://developer.wordpress.org/reference/functions/wp_filesize/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/wp_filesize/#return)
- [Source](https://developer.wordpress.org/reference/functions/wp_filesize/#source)
- [Hooks](https://developer.wordpress.org/reference/functions/wp_filesize/#hooks)
- [Related](https://developer.wordpress.org/reference/functions/wp_filesize/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/wp_filesize/#changelog)

[↑ Back to top](https://developer.wordpress.org/reference/functions/wp_filesize/#wp--skip-link--target)

Wrapper for PHP filesize with filters and casting the result as an integer.

## [Parameters](https://developer.wordpress.org/reference/functions/wp_filesize/\#parameters)

`$path` stringrequired

Path to the file.

## [Return](https://developer.wordpress.org/reference/functions/wp_filesize/\#return)

int The size of the file in bytes, or 0 in the event of an error.

## [Source](https://developer.wordpress.org/reference/functions/wp_filesize/\#source)

`wp-includes/functions.php`
[Expand code](https://developer.wordpress.org/reference/functions/wp_filesize/#)

[Copy](https://developer.wordpress.org/reference/functions/wp_filesize/#)

```php
function wp_filesize( $path ) {
	/**
	 * Filters the result of wp_filesize before the PHP function is run.
	 *
	 * @since 6.0.0
	 *
	 * @param null|int $size The unfiltered value. Returning an int from the callback bypasses the filesize call.
	 * @param string   $path Path to the file.
	 */
	$size = apply_filters( 'pre_wp_filesize', null, $path );

	if ( is_int( $size ) ) {
		return $size;
	}

	$size = file_exists( $path ) ? (int) filesize( $path ) : 0;

	/**
	 * Filters the size of the file.
	 *
	 * @since 6.0.0
	 *
	 * @param int    $size The result of PHP filesize on the file.
	 * @param string $path Path to the file.
	 */
	return (int) apply_filters( 'wp_filesize', $size, $path );
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/functions.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/functions.php#L3603) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/functions.php#L3603-L3629)

## [Hooks](https://developer.wordpress.org/reference/functions/wp_filesize/\#hooks)

[apply\_filters( ‘pre\_wp\_filesize’, null\|int$size, string$path )](https://developer.wordpress.org/reference/hooks/pre_wp_filesize/)

Filters the result of wp\_filesize before the PHP function is run.

[apply\_filters( ‘wp\_filesize’, int$size, string$path )](https://developer.wordpress.org/reference/hooks/wp_filesize/)

Filters the size of the file.

## [Related](https://developer.wordpress.org/reference/functions/wp_filesize/\#related)

| Uses | Description |
| --- | --- |
| [apply\_filters()](https://developer.wordpress.org/reference/functions/apply_filters/) `wp-includes/plugin.php` | Calls the callback functions that have been added to a filter hook. |

| Used by | Description |
| --- | --- |
| [wp\_maybe\_inline\_styles()](https://developer.wordpress.org/reference/functions/wp_maybe_inline_styles/) `wp-includes/script-loader.php` | Allows small styles to be inlined. |
| [\_wp\_image\_meta\_replace\_original()](https://developer.wordpress.org/reference/functions/_wp_image_meta_replace_original/) `wp-admin/includes/image.php` | Updates the attached file and image meta data when the original image was edited. |
| [wp\_create\_image\_subsizes()](https://developer.wordpress.org/reference/functions/wp_create_image_subsizes/) `wp-admin/includes/image.php` | Creates image sub-sizes, adds the new data to the image meta `sizes` array, and updates the image metadata. |
| [wp\_generate\_attachment\_metadata()](https://developer.wordpress.org/reference/functions/wp_generate_attachment_metadata/) `wp-admin/includes/image.php` | Generates attachment meta data and create image sub-sizes for images. |
| [attachment\_submitbox\_metadata()](https://developer.wordpress.org/reference/functions/attachment_submitbox_metadata/) `wp-admin/includes/media.php` | Displays non-editable attachment metadata in the publish meta box. |
| [WP\_Image\_Editor\_Imagick::\_save()](https://developer.wordpress.org/reference/classes/wp_image_editor_imagick/_save/) `wp-includes/class-wp-image-editor-imagick.php` |  |
| [WP\_Image\_Editor\_GD::\_save()](https://developer.wordpress.org/reference/classes/wp_image_editor_gd/_save/) `wp-includes/class-wp-image-editor-gd.php` |  |

[Show 2 more](https://developer.wordpress.org/reference/functions/wp_filesize/#) [Show less](https://developer.wordpress.org/reference/functions/wp_filesize/#)

## [Changelog](https://developer.wordpress.org/reference/functions/wp_filesize/\#changelog)

| Version | Description |
| --- | --- |
| [6.0.0](https://developer.wordpress.org/reference/since/6.0.0/) | Introduced. |

## User Contributed Notes

You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_filesize%2F) before being able to contribute a note or feedback.

Notifications