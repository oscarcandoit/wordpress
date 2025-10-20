---
url: https://developer.wordpress.org/reference/functions/wp_get_loading_optimization_attributes
scraped_at: 2025-10-20T03:19:35.340Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/wp_get_loading_optimization_attributes/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp\_get\_loading\_optimization\_attributes()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)wp\_get\_loading\_optimization\_attributes()

Search

# wp\_get\_loading\_optimization\_attributes( string$tag\_name, array$attr, string$context ): array

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/wp_get_loading_optimization_attributes/#description)
- [Parameters](https://developer.wordpress.org/reference/functions/wp_get_loading_optimization_attributes/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/wp_get_loading_optimization_attributes/#return)
- [Source](https://developer.wordpress.org/reference/functions/wp_get_loading_optimization_attributes/#source)
- [Changelog](https://developer.wordpress.org/reference/functions/wp_get_loading_optimization_attributes/#changelog)

[↑ Back to top](https://developer.wordpress.org/reference/functions/wp_get_loading_optimization_attributes/#wp--skip-link--target)

Gets loading optimization attributes.

## [Description](https://developer.wordpress.org/reference/functions/wp_get_loading_optimization_attributes/\#description)

This function returns an array of attributes that should be merged into the given attributes array to optimize loading performance. Potential attributes returned by this function are:

- `loading` attribute with a value of "lazy"
- `fetchpriority` attribute with a value of "high"
- `decoding` attribute with a value of "async"

If any of these attributes are already present in the given attributes, they will not be modified. Note that no element should have both `loading="lazy"` and `fetchpriority="high"`, so the function will trigger a warning in case both attributes are present with those values.

## [Parameters](https://developer.wordpress.org/reference/functions/wp_get_loading_optimization_attributes/\#parameters)

`$tag_name` stringrequired

The tag name.

`$attr` arrayrequired

Array of the attributes for the tag.

`$context` stringrequired

Context for the element for which the loading optimization attribute is requested.

## [Return](https://developer.wordpress.org/reference/functions/wp_get_loading_optimization_attributes/\#return)

array Loading optimization attributes.

## [Source](https://developer.wordpress.org/reference/functions/wp_get_loading_optimization_attributes/\#source)

`wp-includes/media.php`
[Expand code](https://developer.wordpress.org/reference/functions/wp_get_loading_optimization_attributes/#)

[Copy](https://developer.wordpress.org/reference/functions/wp_get_loading_optimization_attributes/#)

```php
		 * getimagesize() has a tendency to generate errors, such as
		 * "corrupt JPEG data: 7191 extraneous bytes before marker",
		 * even when it's able to provide image size information.
		 *
		 * See https://core.trac.wordpress.org/ticket/42480
		 */
		if ( 2 === func_num_args() ) {
			$info = @getimagesize( $filename, $image_info );
		} else {
			$info = @getimagesize( $filename );
		}
	}

	if (
		! empty( $info ) &&
		// Some PHP versions return 0x0 sizes from `getimagesize` for unrecognized image formats, including AVIFs.
		! ( empty( $info[0] ) && empty( $info[1] ) )
	) {
		return $info;
	}

	$image_mime_type = wp_get_image_mime( $filename );

	// Not an image?
	if ( false === $image_mime_type ) {
		return false;
	}

	/*
	 * For PHP versions that don't support WebP images,
	 * extract the image size info from the file headers.
	 */
	if ( 'image/webp' === $image_mime_type ) {
		$webp_info = wp_get_webp_info( $filename );
		$width     = $webp_info['width'];
		$height    = $webp_info['height'];

		// Mimic the native return format.
		if ( $width && $height ) {
			return array(
				$width,
				$height,
				IMAGETYPE_WEBP,
				sprintf(
					'width="%d" height="%d"',
					$width,
					$height
				),
				'mime' => 'image/webp',
			);
		}
	}

	// For PHP versions that don't support AVIF images, extract the image size info from the file headers.
	if ( 'image/avif' === $image_mime_type ) {
		$avif_info = wp_get_avif_info( $filename );

		$width  = $avif_info['width'];
		$height = $avif_info['height'];

		// Mimic the native return format.
		if ( $width && $height ) {
			return array(
				$width,
				$height,
				IMAGETYPE_AVIF,
				sprintf(
					'width="%d" height="%d"',
					$width,
					$height
				),
				'mime' => 'image/avif',
			);
		}
	}

	// For PHP versions that don't support HEIC images, extract the size info using Imagick when available.
	if ( wp_is_heic_image_mime_type( $image_mime_type ) ) {
		$editor = wp_get_image_editor( $filename );

		if ( is_wp_error( $editor ) ) {
			return false;
		}

		// If the editor for HEICs is Imagick, use it to get the image size.
		if ( $editor instanceof WP_Image_Editor_Imagick ) {
			$size = $editor->get_size();
			return array(
				$size['width'],
				$size['height'],
				IMAGETYPE_HEIC,
				sprintf(
					'width="%d" height="%d"',
					$size['width'],
					$size['height']
				),
				'mime' => 'image/heic',
			);
		}
	}

	// The image could not be parsed.
	return false;
}

/**
 * Extracts meta information about an AVIF file: width, height, bit depth, and number of channels.
 *
 * @since 6.5.0
 *
 * @param string $filename Path to an AVIF file.
 * @return array {
 *     An array of AVIF image information.
 *
 *     @type int|false $width        Image width on success, false on failure.
 *     @type int|false $height       Image height on success, false on failure.
 *     @type int|false $bit_depth    Image bit depth on success, false on failure.
 *     @type int|false $num_channels Image number of channels on success, false on failure.
 * }
 */
function wp_get_avif_info( $filename ) {
	$results = array(
		'width'        => false,
		'height'       => false,
		'bit_depth'    => false,
		'num_channels' => false,
	);

	if ( 'image/avif' !== wp_get_image_mime( $filename ) ) {
		return $results;
	}

	// Parse the file using libavifinfo's PHP implementation.
	require_once ABSPATH . WPINC . '/class-avif-info.php';

	$handle = fopen( $filename, 'rb' );
	if ( $handle ) {
		$parser  = new Avifinfo\Parser( $handle );
		$success = $parser->parse_ftyp() && $parser->parse_file();
		fclose( $handle );
		if ( $success ) {
			$results = $parser->features->primary_item_features;
		}
	}
	return $results;
}

/**
 * Extracts meta information about a WebP file: width, height, and type.
 *
 * @since 5.8.0
 *
 * @param string $filename Path to a WebP file.
 * @return array {
 *     An array of WebP image information.
 *
 *     @type int|false    $width  Image width on success, false on failure.
 *     @type int|false    $height Image height on success, false on failure.
 *     @type string|false $type   The WebP type: one of 'lossy', 'lossless' or 'animated-alpha'.
 *                                False on failure.
 * }
 */
function wp_get_webp_info( $filename ) {
	$width  = false;
	$height = false;
	$type   = false;

	if ( 'image/webp' !== wp_get_image_mime( $filename ) ) {
		return compact( 'width', 'height', 'type' );
	}

	$magic = file_get_contents( $filename, false, null, 0, 40 );

	if ( false === $magic ) {
		return compact( 'width', 'height', 'type' );
	}

	// Make sure we got enough bytes.
	if ( strlen( $magic ) < 40 ) {
		return compact( 'width', 'height', 'type' );
	}

	/*
	 * The headers are a little different for each of the three formats.
	 * Header values based on WebP docs, see https://developers.google.com/speed/webp/docs/riff_container.
	 */
	switch ( substr( $magic, 12, 4 ) ) {
		// Lossy WebP.
		case 'VP8 ':
			$parts  = unpack( 'v2', substr( $magic, 26, 4 ) );
			$width  = (int) ( $parts[1] & 0x3FFF );
			$height = (int) ( $parts[2] & 0x3FFF );
			$type   = 'lossy';
			break;
		// Lossless WebP.
		case 'VP8L':
			$parts  = unpack( 'C4', substr( $magic, 21, 4 ) );
			$width  = (int) ( $parts[1] | ( ( $parts[2] & 0x3F ) << 8 ) ) + 1;
			$height = (int) ( ( ( $parts[2] & 0xC0 ) >> 6 ) | ( $parts[3] << 2 ) | ( ( $parts[4] & 0x03 ) << 10 ) ) + 1;
			$type   = 'lossless';
			break;
		// Animated/alpha WebP.
		case 'VP8X':
			// Pad 24-bit int.
			$width = unpack( 'V', substr( $magic, 24, 3 ) . "\x00" );
			$width = (int) ( $width[1] & 0xFFFFFF ) + 1;
			// Pad 24-bit int.
			$height = unpack( 'V', substr( $magic, 27, 3 ) . "\x00" );
			$height = (int) ( $height[1] & 0xFFFFFF ) + 1;
			$type   = 'animated-alpha';
			break;
	}

	return compact( 'width', 'height', 'type' );
}

/**
 * Gets loading optimization attributes.

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/media.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/media.php#L5722) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/media.php#L5722-L5939)

## [Changelog](https://developer.wordpress.org/reference/functions/wp_get_loading_optimization_attributes/\#changelog)

| Version | Description |
| --- | --- |
| [6.3.0](https://developer.wordpress.org/reference/since/6.3.0/) | Introduced. |

## User Contributed Notes

You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_get_loading_optimization_attributes%2F) before being able to contribute a note or feedback.

Notifications