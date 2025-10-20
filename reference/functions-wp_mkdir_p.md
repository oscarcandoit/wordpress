---
url: https://developer.wordpress.org/reference/functions/wp_mkdir_p
scraped_at: 2025-10-20T03:26:37.428Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/wp_mkdir_p/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp\_mkdir\_p()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)wp\_mkdir\_p()

Search

# wp\_mkdir\_p( string$target ): bool

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/wp_mkdir_p/#description)
- [Parameters](https://developer.wordpress.org/reference/functions/wp_mkdir_p/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/wp_mkdir_p/#return)
- [Source](https://developer.wordpress.org/reference/functions/wp_mkdir_p/#source)
- [Related](https://developer.wordpress.org/reference/functions/wp_mkdir_p/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/wp_mkdir_p/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/functions/wp_mkdir_p/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/functions/wp_mkdir_p/#wp--skip-link--target)

Recursive directory creation based on full path.

## [Description](https://developer.wordpress.org/reference/functions/wp_mkdir_p/\#description)

Will attempt to set permissions on folders.

## [Parameters](https://developer.wordpress.org/reference/functions/wp_mkdir_p/\#parameters)

`$target` stringrequired

Full path to attempt to create.

## [Return](https://developer.wordpress.org/reference/functions/wp_mkdir_p/\#return)

bool Whether the path was created. True if path already exists.

## [Source](https://developer.wordpress.org/reference/functions/wp_mkdir_p/\#source)

`wp-includes/functions.php`
[Expand code](https://developer.wordpress.org/reference/functions/wp_mkdir_p/#)

[Copy](https://developer.wordpress.org/reference/functions/wp_mkdir_p/#)

```php
function wp_mkdir_p( $target ) {
	$wrapper = null;

	// Strip the protocol.
	if ( wp_is_stream( $target ) ) {
		list( $wrapper, $target ) = explode( '://', $target, 2 );
	}

	// From php.net/mkdir user contributed notes.
	$target = str_replace( '//', '/', $target );

	// Put the wrapper back on the target.
	if ( null !== $wrapper ) {
		$target = $wrapper . '://' . $target;
	}

	/*
	 * Safe mode fails with a trailing slash under certain PHP versions.
	 * Use rtrim() instead of untrailingslashit to avoid formatting.php dependency.
	 */
	$target = rtrim( $target, '/' );
	if ( empty( $target ) ) {
		$target = '/';
	}

	if ( file_exists( $target ) ) {
		return @is_dir( $target );
	}

	// Do not allow path traversals.
	if ( str_contains( $target, '../' ) || str_contains( $target, '..' . DIRECTORY_SEPARATOR ) ) {
		return false;
	}

	// We need to find the permissions of the parent folder that exists and inherit that.
	$target_parent = dirname( $target );
	while ( '.' !== $target_parent && ! is_dir( $target_parent ) && dirname( $target_parent ) !== $target_parent ) {
		$target_parent = dirname( $target_parent );
	}

	// Get the permission bits.
	$stat = @stat( $target_parent );
	if ( $stat ) {
		$dir_perms = $stat['mode'] & 0007777;
	} else {
		$dir_perms = 0777;
	}

	if ( @mkdir( $target, $dir_perms, true ) ) {

		/*
		 * If a umask is set that modifies $dir_perms, we'll have to re-set
		 * the $dir_perms correctly with chmod()
		 */
		if ( ( $dir_perms & ~umask() ) !== $dir_perms ) {
			$folder_parts = explode( '/', substr( $target, strlen( $target_parent ) + 1 ) );
			for ( $i = 1, $c = count( $folder_parts ); $i <= $c; $i++ ) {
				chmod( $target_parent . '/' . implode( '/', array_slice( $folder_parts, 0, $i ) ), $dir_perms );
			}
		}

		return true;
	}

	return false;
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/functions.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/functions.php#L2042) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/functions.php#L2042-L2107)

## [Related](https://developer.wordpress.org/reference/functions/wp_mkdir_p/\#related)

| Uses | Description |
| --- | --- |
| [wp\_is\_stream()](https://developer.wordpress.org/reference/functions/wp_is_stream/) `wp-includes/functions.php` | Tests if a given path is a stream URL |

| Used by | Description |
| --- | --- |
| [WP\_Image\_Editor\_Imagick::write\_image()](https://developer.wordpress.org/reference/classes/wp_image_editor_imagick/write_image/) `wp-includes/class-wp-image-editor-imagick.php` | Writes an image to a file or stream. |
| [wp\_privacy\_generate\_personal\_data\_export\_file()](https://developer.wordpress.org/reference/functions/wp_privacy_generate_personal_data_export_file/) `wp-admin/includes/privacy-tools.php` | Generate the personal data export file. |
| [\_copy\_image\_file()](https://developer.wordpress.org/reference/functions/_copy_image_file/) `wp-admin/includes/image.php` | Copies an existing image file. |
| [wp\_crop\_image()](https://developer.wordpress.org/reference/functions/wp_crop_image/) `wp-admin/includes/image.php` | Crops an image to a given size. |
| [wp\_upload\_bits()](https://developer.wordpress.org/reference/functions/wp_upload_bits/) `wp-includes/functions.php` | Creates a file in the upload folder with given content. |
| [wp\_upload\_dir()](https://developer.wordpress.org/reference/functions/wp_upload_dir/) `wp-includes/functions.php` | Returns an array containing the current upload directory’s path and URL. |
| [WP\_Image\_Editor::make\_image()](https://developer.wordpress.org/reference/classes/wp_image_editor/make_image/) `wp-includes/class-wp-image-editor.php` | Either calls editor’s save function or handles file as a stream. |

[Show 2 more](https://developer.wordpress.org/reference/functions/wp_mkdir_p/#) [Show less](https://developer.wordpress.org/reference/functions/wp_mkdir_p/#)

## [Changelog](https://developer.wordpress.org/reference/functions/wp_mkdir_p/\#changelog)

| Version | Description |
| --- | --- |
| [2.0.1](https://developer.wordpress.org/reference/since/2.0.1/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/functions/wp_mkdir_p/\#user-contributed-notes)

1. [Skip to note 4 content](https://developer.wordpress.org/reference/functions/wp_mkdir_p/#comment-content-1355)



**Basic Example**





`wp-includes/functions.php`
[Copy](https://developer.wordpress.org/reference/functions/wp_mkdir_p/#)




```php
if ( wp_mkdir_p( '/a/really/deep/sub/directory' ) ) {
     echo __( 'It worked! Now look for a directory named "a".', 'textdomain' );
}
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_mkdir_p%2F%3Freplytocom%3D1355%23feedback-editor-1355)

2. [Skip to note 5 content](https://developer.wordpress.org/reference/functions/wp_mkdir_p/#comment-content-5059)



Should you need to create a folder with 777 permission (i.e. usefull for a cache folder), just do:





`wp-includes/functions.php`
[Copy](https://developer.wordpress.org/reference/functions/wp_mkdir_p/#)




```php
$cache_folder = ABSPATH . 'cache';
if ( ! is_dir( $cache_folder ) ) {
   		wp_mkdir_p( $cache_folder );
   		chmod( $cache_folder, 0777 );
}
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_mkdir_p%2F%3Freplytocom%3D5059%23feedback-editor-5059)

3. [Skip to note 6 content](https://developer.wordpress.org/reference/functions/wp_mkdir_p/#comment-content-4862)



Creating a directory if doesn’t already exist.





`wp-includes/functions.php`
[Copy](https://developer.wordpress.org/reference/functions/wp_mkdir_p/#)




```php
if ( ! is_dir( ABSPATH . 'my-folder' ) ) {
       wp_mkdir_p( ABSPATH . 'my-folder' );
}
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_mkdir_p%2F%3Freplytocom%3D4862%23feedback-editor-4862)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_mkdir_p%2F) before being able to contribute a note or feedback.

Notifications