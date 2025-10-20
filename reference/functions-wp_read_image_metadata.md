---
url: https://developer.wordpress.org/reference/functions/wp_read_image_metadata
scraped_at: 2025-10-20T03:26:30.552Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/wp_read_image_metadata/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp\_read\_image\_metadata()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)wp\_read\_image\_metadata()

Search

# wp\_read\_image\_metadata( string$file ): array\|false

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/wp_read_image_metadata/#description)
- [Parameters](https://developer.wordpress.org/reference/functions/wp_read_image_metadata/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/wp_read_image_metadata/#return)
- [More Information](https://developer.wordpress.org/reference/functions/wp_read_image_metadata/#more-information)
- [Source](https://developer.wordpress.org/reference/functions/wp_read_image_metadata/#source)
- [Hooks](https://developer.wordpress.org/reference/functions/wp_read_image_metadata/#hooks)
- [Related](https://developer.wordpress.org/reference/functions/wp_read_image_metadata/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/wp_read_image_metadata/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/functions/wp_read_image_metadata/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/functions/wp_read_image_metadata/#wp--skip-link--target)

Gets extended image metadata, exif or iptc as available.

## [Description](https://developer.wordpress.org/reference/functions/wp_read_image_metadata/\#description)

Retrieves the EXIF metadata aperture, credit, camera, caption, copyright, iso created\_timestamp, focal\_length, shutter\_speed, and title.

The IPTC metadata that is retrieved is APP13, credit, byline, created date and time, caption, copyright, and title. Also includes FNumber, Model, DateTimeDigitized, FocalLength, ISOSpeedRatings, and ExposureTime.

## [Parameters](https://developer.wordpress.org/reference/functions/wp_read_image_metadata/\#parameters)

`$file` stringrequired

## [Return](https://developer.wordpress.org/reference/functions/wp_read_image_metadata/\#return)

array\|false Image metadata array on success, false on failure.

## [More Information](https://developer.wordpress.org/reference/functions/wp_read_image_metadata/\#more-information)

**Additional note to Return**

The elements returned in the array are:

**`["aperture"]`**

(string) Set to the EXIF FNumber field.

**`["credit"]`**

(string) Set to the first non-empty value found by looking through the following fields:

1. IPTC Credit field (2#110)
2. IPTC Creator field (2#080)
3. EXIF Artist field
4. EXIF Author field

**`["camera"] `**

(string) Set to the EXIF Model field.

**`["caption"] `**

(string) Set to a non-empty value of one of the following fields (see source code for the precise logic involved):

1. IPTC Description field (2#120)
2. EXIF UserComment field if \[“title”\] is unset AND EXIF:ImageDescription is less than 80 characters
3. EXIF ImageDescription field if \[“title”\] is set OR EXIF:ImageDescription is more than 80 characters
4. EXIF Comments field if \[“title”\] does not equal EXIF:Comments

**`["created_timestamp"] `**

(string) Set to the first non-empty value found by looking through the following fields:

1. EXIF field DateTimeDigitized
2. IPTC Date and Time fields (2#055 and 2#060)

**`["copyright"] `**

(string) Set to the first non-empty value found by looking through the following fields:

1. IPTC Copyright field (2#116)
2. EXIF Copyright field

**`["focal_length"] `**

(string) Set to the EXIF FocalLength field.

**`["iso"] `**

(string) Set to the EXIF ISOSpeedRatings field.

**`["shutter_speed"] `**

(string) Set to the EXIF ExposureTime field.

**`["title"] `**

(string) Set to the first non-empty value found by looking through the following fields:

1. IPTC Headline field (2#105)
2. IPTC Title field (2#005)
3. IPTC Description field (2#120) but only if less than 80 characters
4. EXIF Title field
5. EXIF ImageDescription field but only if less than 80 characters

The (2#nnn) value shown after each IPTC field (above) is the key of the array returned by PHP’s iptcparse function for that particular IPTC field.

## [Source](https://developer.wordpress.org/reference/functions/wp_read_image_metadata/\#source)

`wp-admin/includes/image.php`
[Expand code](https://developer.wordpress.org/reference/functions/wp_read_image_metadata/#)

[Copy](https://developer.wordpress.org/reference/functions/wp_read_image_metadata/#)

```php
function wp_read_image_metadata( $file ) {
	if ( ! file_exists( $file ) ) {
		return false;
	}

	list( , , $image_type ) = wp_getimagesize( $file );

	/*
	 * EXIF contains a bunch of data we'll probably never need formatted in ways
	 * that are difficult to use. We'll normalize it and just extract the fields
	 * that are likely to be useful. Fractions and numbers are converted to
	 * floats, dates to unix timestamps, and everything else to strings.
	 */
	$meta = array(
		'aperture'          => 0,
		'credit'            => '',
		'camera'            => '',
		'caption'           => '',
		'created_timestamp' => 0,
		'copyright'         => '',
		'focal_length'      => 0,
		'iso'               => 0,
		'shutter_speed'     => 0,
		'title'             => '',
		'orientation'       => 0,
		'keywords'          => array(),
	);

	$iptc = array();
	$info = array();
	/*
	 * Read IPTC first, since it might contain data not available in exif such
	 * as caption, description etc.
	 */
	if ( is_callable( 'iptcparse' ) ) {
		wp_getimagesize( $file, $info );

		if ( ! empty( $info['APP13'] ) ) {
			// Don't silence errors when in debug mode, unless running unit tests.
			if ( defined( 'WP_DEBUG' ) && WP_DEBUG
				&& ! defined( 'WP_RUN_CORE_TESTS' )
			) {
				$iptc = iptcparse( $info['APP13'] );
			} else {
				// Silencing notice and warning is intentional. See https://core.trac.wordpress.org/ticket/42480
				$iptc = @iptcparse( $info['APP13'] );
			}

			if ( ! is_array( $iptc ) ) {
				$iptc = array();
			}

			// Headline, "A brief synopsis of the caption".
			if ( ! empty( $iptc['2#105'][0] ) ) {
				$meta['title'] = trim( $iptc['2#105'][0] );
				/*
				* Title, "Many use the Title field to store the filename of the image,
				* though the field may be used in many ways".
				*/
			} elseif ( ! empty( $iptc['2#005'][0] ) ) {
				$meta['title'] = trim( $iptc['2#005'][0] );
			}

			if ( ! empty( $iptc['2#120'][0] ) ) { // Description / legacy caption.
				$caption = trim( $iptc['2#120'][0] );

				mbstring_binary_safe_encoding();
				$caption_length = strlen( $caption );
				reset_mbstring_encoding();

				if ( empty( $meta['title'] ) && $caption_length < 80 ) {
					// Assume the title is stored in 2:120 if it's short.
					$meta['title'] = $caption;
				}

				$meta['caption'] = $caption;
			}

			if ( ! empty( $iptc['2#110'][0] ) ) { // Credit.
				$meta['credit'] = trim( $iptc['2#110'][0] );
			} elseif ( ! empty( $iptc['2#080'][0] ) ) { // Creator / legacy byline.
				$meta['credit'] = trim( $iptc['2#080'][0] );
			}

			if ( ! empty( $iptc['2#055'][0] ) && ! empty( $iptc['2#060'][0] ) ) { // Created date and time.
				$meta['created_timestamp'] = strtotime( $iptc['2#055'][0] . ' ' . $iptc['2#060'][0] );
			}

			if ( ! empty( $iptc['2#116'][0] ) ) { // Copyright.
				$meta['copyright'] = trim( $iptc['2#116'][0] );
			}

			if ( ! empty( $iptc['2#025'][0] ) ) { // Keywords array.
				$meta['keywords'] = array_values( $iptc['2#025'] );
			}
		}
	}

	$exif = array();

	/**
	 * Filters the image types to check for exif data.
	 *
	 * @since 2.5.0
	 *
	 * @param int[] $image_types Array of image types to check for exif data. Each value
	 *                           is usually one of the `IMAGETYPE_*` constants.
	 */
	$exif_image_types = apply_filters( 'wp_read_image_metadata_types', array( IMAGETYPE_JPEG, IMAGETYPE_TIFF_II, IMAGETYPE_TIFF_MM ) );

	if ( is_callable( 'exif_read_data' ) && in_array( $image_type, $exif_image_types, true ) ) {
		// Don't silence errors when in debug mode, unless running unit tests.
		if ( defined( 'WP_DEBUG' ) && WP_DEBUG
			&& ! defined( 'WP_RUN_CORE_TESTS' )
		) {
			$exif = exif_read_data( $file );
		} else {
			// Silencing notice and warning is intentional. See https://core.trac.wordpress.org/ticket/42480
			$exif = @exif_read_data( $file );
		}

		if ( ! is_array( $exif ) ) {
			$exif = array();
		}

		$exif_description = '';
		$exif_usercomment = '';
		if ( ! empty( $exif['ImageDescription'] ) ) {
			$exif_description = trim( $exif['ImageDescription'] );
		}

		if ( ! empty( $exif['COMPUTED']['UserComment'] ) ) {
			$exif_usercomment = trim( $exif['COMPUTED']['UserComment'] );
		}

		if ( $exif_description ) {
			mbstring_binary_safe_encoding();
			$description_length = strlen( $exif_description );
			reset_mbstring_encoding();
			if ( empty( $meta['title'] ) && $description_length < 80 ) {
				// Assume the title is stored in ImageDescription.
				$meta['title'] = $exif_description;
			}

			// If both user comments and description are present.
			if ( empty( $meta['caption'] ) && $exif_description && $exif_usercomment ) {
				if ( ! empty( $meta['title'] ) && $exif_description === $meta['title'] ) {
					$caption = $exif_usercomment;
				} else {
					if ( $exif_description === $exif_usercomment ) {
						$caption = $exif_description;
					} else {
						$caption = trim( $exif_description . ' ' . $exif_usercomment );
					}
				}
				$meta['caption'] = $caption;
			}

			if ( empty( $meta['caption'] ) && $exif_usercomment ) {
				$meta['caption'] = $exif_usercomment;
			}

			if ( empty( $meta['caption'] ) ) {
				$meta['caption'] = $exif_description;
			}
		} elseif ( empty( $meta['caption'] ) && $exif_usercomment ) {
			$meta['caption']    = $exif_usercomment;
			$description_length = strlen( $exif_usercomment );
			if ( empty( $meta['title'] ) && $description_length < 80 ) {
				$meta['title'] = trim( $exif_usercomment );
			}
		} elseif ( empty( $meta['caption'] ) && ! empty( $exif['Comments'] ) ) {
			$meta['caption'] = trim( $exif['Comments'] );
		}

		if ( empty( $meta['credit'] ) ) {
			if ( ! empty( $exif['Artist'] ) ) {
				$meta['credit'] = trim( $exif['Artist'] );
			} elseif ( ! empty( $exif['Author'] ) ) {
				$meta['credit'] = trim( $exif['Author'] );
			}
		}

		if ( empty( $meta['copyright'] ) && ! empty( $exif['Copyright'] ) ) {
			$meta['copyright'] = trim( $exif['Copyright'] );
		}
		if ( ! empty( $exif['FNumber'] ) && is_scalar( $exif['FNumber'] ) ) {
			$meta['aperture'] = round( wp_exif_frac2dec( $exif['FNumber'] ), 2 );
		}
		if ( ! empty( $exif['Model'] ) ) {
			$meta['camera'] = trim( $exif['Model'] );
		}
		if ( empty( $meta['created_timestamp'] ) && ! empty( $exif['DateTimeDigitized'] ) ) {
			$meta['created_timestamp'] = wp_exif_date2ts( $exif['DateTimeDigitized'] );
		}
		if ( ! empty( $exif['FocalLength'] ) ) {
			$meta['focal_length'] = (string) $exif['FocalLength'];
			if ( is_scalar( $exif['FocalLength'] ) ) {
				$meta['focal_length'] = (string) wp_exif_frac2dec( $exif['FocalLength'] );
			}
		}
		if ( ! empty( $exif['ISOSpeedRatings'] ) ) {
			$meta['iso'] = is_array( $exif['ISOSpeedRatings'] ) ? reset( $exif['ISOSpeedRatings'] ) : $exif['ISOSpeedRatings'];
			$meta['iso'] = trim( $meta['iso'] );
		}
		if ( ! empty( $exif['ExposureTime'] ) ) {
			$meta['shutter_speed'] = (string) $exif['ExposureTime'];
			if ( is_scalar( $exif['ExposureTime'] ) ) {
				$meta['shutter_speed'] = (string) wp_exif_frac2dec( $exif['ExposureTime'] );
			}
		}
		if ( ! empty( $exif['Orientation'] ) ) {
			$meta['orientation'] = $exif['Orientation'];
		}
	}

	foreach ( array( 'title', 'caption', 'credit', 'copyright', 'camera', 'iso' ) as $key ) {
		if ( $meta[ $key ] && ! seems_utf8( $meta[ $key ] ) ) {
			$meta[ $key ] = utf8_encode( $meta[ $key ] );
		}
	}

	foreach ( $meta['keywords'] as $key => $keyword ) {
		if ( ! seems_utf8( $keyword ) ) {
			$meta['keywords'][ $key ] = utf8_encode( $keyword );
		}
	}

	$meta = wp_kses_post_deep( $meta );

	/**
	 * Filters the array of meta data read from an image's exif data.
	 *
	 * @since 2.5.0
	 * @since 4.4.0 The `$iptc` parameter was added.
	 * @since 5.0.0 The `$exif` parameter was added.
	 *
	 * @param array  $meta       Image meta data.
	 * @param string $file       Path to image file.
	 * @param int    $image_type Type of image, one of the `IMAGETYPE_XXX` constants.
	 * @param array  $iptc       IPTC data.
	 * @param array  $exif       EXIF data.
	 */
	return apply_filters( 'wp_read_image_metadata', $meta, $file, $image_type, $iptc, $exif );
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-admin/includes/image.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-admin/includes/image.php#L825) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-admin/includes/image.php#L825-L1069)

## [Hooks](https://developer.wordpress.org/reference/functions/wp_read_image_metadata/\#hooks)

[apply\_filters( ‘wp\_read\_image\_metadata’, array$meta, string$file, int$image\_type, array$iptc, array$exif )](https://developer.wordpress.org/reference/hooks/wp_read_image_metadata/)

Filters the array of meta data read from an image’s exif data.

[apply\_filters( ‘wp\_read\_image\_metadata\_types’, int\[\]$image\_types )](https://developer.wordpress.org/reference/hooks/wp_read_image_metadata_types/)

Filters the image types to check for exif data.

## [Related](https://developer.wordpress.org/reference/functions/wp_read_image_metadata/\#related)

| Uses | Description |
| --- | --- |
| [wp\_kses\_post\_deep()](https://developer.wordpress.org/reference/functions/wp_kses_post_deep/) `wp-includes/kses.php` | Navigates through an array, object, or scalar, and sanitizes content for allowed HTML tags for post content. |
| [wp\_exif\_frac2dec()](https://developer.wordpress.org/reference/functions/wp_exif_frac2dec/) `wp-admin/includes/image.php` | Converts a fraction string to a decimal. |
| [wp\_exif\_date2ts()](https://developer.wordpress.org/reference/functions/wp_exif_date2ts/) `wp-admin/includes/image.php` | Converts the exif date format to a unix timestamp. |
| [seems\_utf8()](https://developer.wordpress.org/reference/functions/seems_utf8/) `wp-includes/formatting.php` | Checks to see if a string is utf8 encoded. |
| [mbstring\_binary\_safe\_encoding()](https://developer.wordpress.org/reference/functions/mbstring_binary_safe_encoding/) `wp-includes/functions.php` | Sets the mbstring internal encoding to a binary safe encoding when func\_overload is enabled. |
| [reset\_mbstring\_encoding()](https://developer.wordpress.org/reference/functions/reset_mbstring_encoding/) `wp-includes/functions.php` | Resets the mbstring internal encoding to a users previously set encoding. |
| [apply\_filters()](https://developer.wordpress.org/reference/functions/apply_filters/) `wp-includes/plugin.php` | Calls the callback functions that have been added to a filter hook. |

[Show 2 more](https://developer.wordpress.org/reference/functions/wp_read_image_metadata/#) [Show less](https://developer.wordpress.org/reference/functions/wp_read_image_metadata/#)

| Used by | Description |
| --- | --- |
| [WP\_REST\_Attachments\_Controller::insert\_attachment()](https://developer.wordpress.org/reference/classes/wp_rest_attachments_controller/insert_attachment/) `wp-includes/rest-api/endpoints/class-wp-rest-attachments-controller.php` | Inserts the attachment post in the database. Does not update the attachment meta. |
| [wp\_create\_image\_subsizes()](https://developer.wordpress.org/reference/functions/wp_create_image_subsizes/) `wp-admin/includes/image.php` | Creates image sub-sizes, adds the new data to the image meta `sizes` array, and updates the image metadata. |
| [media\_handle\_upload()](https://developer.wordpress.org/reference/functions/media_handle_upload/) `wp-admin/includes/media.php` | Saves a file submitted from a POST request and create an attachment post for it. |
| [media\_handle\_sideload()](https://developer.wordpress.org/reference/functions/media_handle_sideload/) `wp-admin/includes/media.php` | Handles a side-loaded file in the same way as an uploaded file is handled by [media\_handle\_upload()](https://developer.wordpress.org/reference/functions/media_handle_upload/) . |

## [Changelog](https://developer.wordpress.org/reference/functions/wp_read_image_metadata/\#changelog)

| Version | Description |
| --- | --- |
| [2.5.0](https://developer.wordpress.org/reference/since/2.5.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/functions/wp_read_image_metadata/\#user-contributed-notes)

1. [Skip to note 2 content](https://developer.wordpress.org/reference/functions/wp_read_image_metadata/#comment-content-2123)



When you receive error upon calling this function



`PHP Fatal error:  Uncaught Error: Call to undefined function wp_read_image_metadata() ... `



Make sure to include the `wp-admin/includes/image.php` file





`wp-admin/includes/image.php`
[Copy](https://developer.wordpress.org/reference/functions/wp_read_image_metadata/#)




```php
require_once ABSPATH . '/wp-admin/includes/image.php';

$path = '/path/to/file.jpg';

wp_read_image_metadata( $path );
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_read_image_metadata%2F%3Freplytocom%3D2123%23feedback-editor-2123)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_read_image_metadata%2F) before being able to contribute a note or feedback.

Notifications