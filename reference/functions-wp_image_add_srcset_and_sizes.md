---
url: https://developer.wordpress.org/reference/functions/wp_image_add_srcset_and_sizes
scraped_at: 2025-10-20T03:18:34.944Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/wp_image_add_srcset_and_sizes/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp\_image\_add\_srcset\_and\_sizes()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)wp\_image\_add\_srcset\_and\_sizes()

Search

# wp\_image\_add\_srcset\_and\_sizes( string$image, array$image\_meta, int$attachment\_id ): string

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/wp_image_add_srcset_and_sizes/#description)
  - [See also](https://developer.wordpress.org/reference/functions/wp_image_add_srcset_and_sizes/#see-also)
- [Parameters](https://developer.wordpress.org/reference/functions/wp_image_add_srcset_and_sizes/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/wp_image_add_srcset_and_sizes/#return)
- [Source](https://developer.wordpress.org/reference/functions/wp_image_add_srcset_and_sizes/#source)
- [Changelog](https://developer.wordpress.org/reference/functions/wp_image_add_srcset_and_sizes/#changelog)

[↑ Back to top](https://developer.wordpress.org/reference/functions/wp_image_add_srcset_and_sizes/#wp--skip-link--target)

Adds ‘srcset’ and ‘sizes’ attributes to an existing ‘img’ element.

## [Description](https://developer.wordpress.org/reference/functions/wp_image_add_srcset_and_sizes/\#description)

### [See also](https://developer.wordpress.org/reference/functions/wp_image_add_srcset_and_sizes/\#see-also)

- [wp\_calculate\_image\_srcset()](https://developer.wordpress.org/reference/functions/wp_calculate_image_srcset)
- [wp\_calculate\_image\_sizes()](https://developer.wordpress.org/reference/functions/wp_calculate_image_sizes)

## [Parameters](https://developer.wordpress.org/reference/functions/wp_image_add_srcset_and_sizes/\#parameters)

`$image` stringrequired

An HTML `'img'` element to be filtered.

`$image_meta` arrayrequired

The image meta data as returned by ‘ [wp\_get\_attachment\_metadata()](https://developer.wordpress.org/reference/functions/wp_get_attachment_metadata/) ‘.

`$attachment_id` intrequired

Image attachment ID.

## [Return](https://developer.wordpress.org/reference/functions/wp_image_add_srcset_and_sizes/\#return)

string Converted `'img'` element with `'srcset'` and `'sizes'` attributes added.

## [Source](https://developer.wordpress.org/reference/functions/wp_image_add_srcset_and_sizes/\#source)

`wp-includes/media.php`
[Expand code](https://developer.wordpress.org/reference/functions/wp_image_add_srcset_and_sizes/#)

[Copy](https://developer.wordpress.org/reference/functions/wp_image_add_srcset_and_sizes/#)

```php
				break;
			}
		}
	}

	/**
	 * Filters the 'wp_image_src_get_dimensions' value.
	 *
	 * @since 5.7.0
	 *
	 * @param array|false $dimensions    Array with first element being the width
	 *                                   and second element being the height, or
	 *                                   false if dimensions could not be determined.
	 * @param string      $image_src     The image source file.
	 * @param array       $image_meta    The image meta data as returned by
	 *                                   'wp_get_attachment_metadata()'.
	 * @param int         $attachment_id The image attachment ID. Default 0.
	 */
	return apply_filters( 'wp_image_src_get_dimensions', $dimensions, $image_src, $image_meta, $attachment_id );
}

/**
 * Adds 'srcset' and 'sizes' attributes to an existing 'img' element.
 *
 * @since 4.4.0
 *
 * @see wp_calculate_image_srcset()
 * @see wp_calculate_image_sizes()
 *
 * @param string $image         An HTML 'img' element to be filtered.
 * @param array  $image_meta    The image meta data as returned by 'wp_get_attachment_metadata()'.
 * @param int    $attachment_id Image attachment ID.
 * @return string Converted 'img' element with 'srcset' and 'sizes' attributes added.
 */
function wp_image_add_srcset_and_sizes( $image, $image_meta, $attachment_id ) {
	// Ensure the image meta exists.
	if ( empty( $image_meta['sizes'] ) ) {
		return $image;
	}

	$image_src         = preg_match( '/src="([^"]+)"/', $image, $match_src ) ? $match_src[1] : '';
	list( $image_src ) = explode( '?', $image_src );

	// Return early if we couldn't get the image source.
	if ( ! $image_src ) {
		return $image;
	}

	// Bail early if an image has been inserted and later edited.
	if ( preg_match( '/-e[0-9]{13}/', $image_meta['file'], $img_edit_hash )
		&& ! str_contains( wp_basename( $image_src ), $img_edit_hash[0] )
	) {
		return $image;
	}

	$width  = preg_match( '/ width="([0-9]+)"/', $image, $match_width ) ? (int) $match_width[1] : 0;
	$height = preg_match( '/ height="([0-9]+)"/', $image, $match_height ) ? (int) $match_height[1] : 0;

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/media.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/media.php#L1719) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/media.php#L1719-L1776)

## [Changelog](https://developer.wordpress.org/reference/functions/wp_image_add_srcset_and_sizes/\#changelog)

| Version | Description |
| --- | --- |
| [4.4.0](https://developer.wordpress.org/reference/since/4.4.0/) | Introduced. |

## User Contributed Notes

You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_image_add_srcset_and_sizes%2F) before being able to contribute a note or feedback.

Notifications