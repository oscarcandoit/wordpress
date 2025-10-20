---
url: https://developer.wordpress.org/reference/functions/wp_crop_image
scraped_at: 2025-10-20T03:19:31.844Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/wp_crop_image/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp\_crop\_image()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)wp\_crop\_image()

Search

# wp\_crop\_image( string\|int$src, int$src\_x, int$src\_y, int$src\_w, int$src\_h, int$dst\_w, int$dst\_h, bool\|false$src\_abs = false, string\|false$dst\_file = false ): string\| [WP\_Error](https://developer.wordpress.org/reference/classes/wp_error/)

## In this article

Table of Contents

- [Parameters](https://developer.wordpress.org/reference/functions/wp_crop_image/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/wp_crop_image/#return)
- [Source](https://developer.wordpress.org/reference/functions/wp_crop_image/#source)
- [Related](https://developer.wordpress.org/reference/functions/wp_crop_image/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/wp_crop_image/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/functions/wp_crop_image/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/functions/wp_crop_image/#wp--skip-link--target)

Crops an image to a given size.

## [Parameters](https://developer.wordpress.org/reference/functions/wp_crop_image/\#parameters)

`$src` string\|intrequired

The source file or Attachment ID.

`$src_x` intrequired

The start x position to crop from.

`$src_y` intrequired

The start y position to crop from.

`$src_w` intrequired

The width to crop.

`$src_h` intrequired

The height to crop.

`$dst_w` intrequired

The destination width.

`$dst_h` intrequired

The destination height.

`$src_abs` bool\|falseoptional

If the source crop points are absolute.

Default: `false`

`$dst_file` string\|falseoptional

The destination file to write to.

Default: `false`

## [Return](https://developer.wordpress.org/reference/functions/wp_crop_image/\#return)

string\| [WP\_Error](https://developer.wordpress.org/reference/classes/wp_error/) New filepath on success, [WP\_Error](https://developer.wordpress.org/reference/classes/wp_error/) on failure.

## [Source](https://developer.wordpress.org/reference/functions/wp_crop_image/\#source)

`wp-admin/includes/image.php`
[Expand code](https://developer.wordpress.org/reference/functions/wp_crop_image/#)

[Copy](https://developer.wordpress.org/reference/functions/wp_crop_image/#)

```php
function wp_crop_image( $src, $src_x, $src_y, $src_w, $src_h, $dst_w, $dst_h, $src_abs = false, $dst_file = false ) {
	$src_file = $src;
	if ( is_numeric( $src ) ) { // Handle int as attachment ID.
		$src_file = get_attached_file( $src );

		if ( ! file_exists( $src_file ) ) {
			/*
			 * If the file doesn't exist, attempt a URL fopen on the src link.
			 * This can occur with certain file replication plugins.
			 */
			$src = _load_image_to_edit_path( $src, 'full' );
		} else {
			$src = $src_file;
		}
	}

	$editor = wp_get_image_editor( $src );
	if ( is_wp_error( $editor ) ) {
		return $editor;
	}

	$src = $editor->crop( $src_x, $src_y, $src_w, $src_h, $dst_w, $dst_h, $src_abs );
	if ( is_wp_error( $src ) ) {
		return $src;
	}

	if ( ! $dst_file ) {
		$dst_file = str_replace( wp_basename( $src_file ), 'cropped-' . wp_basename( $src_file ), $src_file );
	}

	/*
	 * The directory containing the original file may no longer exist when
	 * using a replication plugin.
	 */
	wp_mkdir_p( dirname( $dst_file ) );

	$dst_file = dirname( $dst_file ) . '/' . wp_unique_filename( dirname( $dst_file ), wp_basename( $dst_file ) );

	$result = $editor->save( $dst_file );
	if ( is_wp_error( $result ) ) {
		return $result;
	}

	if ( ! empty( $result['path'] ) ) {
		return $result['path'];
	}

	return $dst_file;
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-admin/includes/image.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-admin/includes/image.php#L25) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-admin/includes/image.php#L25-L73)

## [Related](https://developer.wordpress.org/reference/functions/wp_crop_image/\#related)

| Uses | Description |
| --- | --- |
| [\_load\_image\_to\_edit\_path()](https://developer.wordpress.org/reference/functions/_load_image_to_edit_path/) `wp-admin/includes/image.php` | Retrieves the path or URL of an attachment’s attached file. |
| [wp\_basename()](https://developer.wordpress.org/reference/functions/wp_basename/) `wp-includes/formatting.php` | i18n-friendly version of basename(). |
| [wp\_mkdir\_p()](https://developer.wordpress.org/reference/functions/wp_mkdir_p/) `wp-includes/functions.php` | Recursive directory creation based on full path. |
| [wp\_unique\_filename()](https://developer.wordpress.org/reference/functions/wp_unique_filename/) `wp-includes/functions.php` | Gets a filename that is sanitized and unique for the given directory. |
| [get\_attached\_file()](https://developer.wordpress.org/reference/functions/get_attached_file/) `wp-includes/post.php` | Retrieves attached file path based on attachment ID. |
| [is\_wp\_error()](https://developer.wordpress.org/reference/functions/is_wp_error/) `wp-includes/load.php` | Checks whether the given variable is a WordPress Error. |

[Show 1 more](https://developer.wordpress.org/reference/functions/wp_crop_image/#) [Show less](https://developer.wordpress.org/reference/functions/wp_crop_image/#)

| Used by | Description |
| --- | --- |
| [wp\_ajax\_crop\_image()](https://developer.wordpress.org/reference/functions/wp_ajax_crop_image/) `wp-admin/includes/ajax-actions.php` | Handles cropping an image via AJAX. |
| [Custom\_Image\_Header::ajax\_header\_crop()](https://developer.wordpress.org/reference/classes/custom_image_header/ajax_header_crop/) `wp-admin/includes/class-custom-image-header.php` | Gets attachment uploaded by Media Manager, crops it, then saves it as a new object. Returns JSON-encoded object details. |
| [Custom\_Image\_Header::step\_2()](https://developer.wordpress.org/reference/classes/custom_image_header/step_2/) `wp-admin/includes/class-custom-image-header.php` | Displays second step of custom header image page. |
| [Custom\_Image\_Header::step\_3()](https://developer.wordpress.org/reference/classes/custom_image_header/step_3/) `wp-admin/includes/class-custom-image-header.php` | Displays third step of custom header image page. |

## [Changelog](https://developer.wordpress.org/reference/functions/wp_crop_image/\#changelog)

| Version | Description |
| --- | --- |
| [2.1.0](https://developer.wordpress.org/reference/since/2.1.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/functions/wp_crop_image/\#user-contributed-notes)

1. [Skip to note 2 content](https://developer.wordpress.org/reference/functions/wp_crop_image/#comment-content-6310)





`wp-admin/includes/image.php`
[Expand code](https://developer.wordpress.org/reference/functions/wp_crop_image/#)

[Copy](https://developer.wordpress.org/reference/functions/wp_crop_image/#)




```php
$attachment_id = 100; // Image attachment ID.
$cropped_file = wp_crop_image(
   	$attachment_id, // Attachment ID.
   	1,              // Position x on the image.
   	70,             // Position y on the image.
   	100,            // Selected for cropping width.
   	100,            // Selected for cropping height.
   	100,            // Desired Cropped image width.
   	100             // Desired cropped image height.
);

// This will return 100x100 cropped image.
if ( ! is_wp_error( $cropped_file ) ) {
   	echo $cropped_file; // Will return absolute path of cropped file.
}
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_crop_image%2F%3Freplytocom%3D6310%23feedback-editor-6310)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_crop_image%2F) before being able to contribute a note or feedback.

Notifications