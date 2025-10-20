---
url: https://developer.wordpress.org/reference/functions/wp_enqueue_media
scraped_at: 2025-10-20T03:42:16.309Z
retry_attempt: 1
---

[Skip to content](https://developer.wordpress.org/reference/functions/wp_enqueue_media/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp\_enqueue\_media()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)wp\_enqueue\_media()

Search

# wp\_enqueue\_media( array$args = array() )

## In this article

Table of Contents

- [Parameters](https://developer.wordpress.org/reference/functions/wp_enqueue_media/#parameters)
- [Source](https://developer.wordpress.org/reference/functions/wp_enqueue_media/#source)
- [Changelog](https://developer.wordpress.org/reference/functions/wp_enqueue_media/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/functions/wp_enqueue_media/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/functions/wp_enqueue_media/#wp--skip-link--target)

Enqueues all scripts, styles, settings, and templates necessary to use all media JS APIs.

## [Parameters](https://developer.wordpress.org/reference/functions/wp_enqueue_media/\#parameters)

`$args` arrayoptional

Arguments for enqueuing media scripts.

- `post` int\| [WP\_Post](https://developer.wordpress.org/reference/classes/wp_post/)
Post ID or post object.


Default: `array()`

## [Source](https://developer.wordpress.org/reference/functions/wp_enqueue_media/\#source)

`wp-includes/media.php`
[Expand code](https://developer.wordpress.org/reference/functions/wp_enqueue_media/#)

[Copy](https://developer.wordpress.org/reference/functions/wp_enqueue_media/#)

```php
	if ( $bytes ) {
		$response['filesizeInBytes']       = $bytes;
		$response['filesizeHumanReadable'] = size_format( $bytes );
	}

	$context             = get_post_meta( $attachment->ID, '_wp_attachment_context', true );
	$response['context'] = ( $context ) ? $context : '';

	if ( current_user_can( 'edit_post', $attachment->ID ) ) {
		$response['nonces']['update'] = wp_create_nonce( 'update-post_' . $attachment->ID );
		$response['nonces']['edit']   = wp_create_nonce( 'image_editor-' . $attachment->ID );
		$response['editLink']         = get_edit_post_link( $attachment->ID, 'raw' );
	}

	if ( current_user_can( 'delete_post', $attachment->ID ) ) {
		$response['nonces']['delete'] = wp_create_nonce( 'delete-post_' . $attachment->ID );
	}

	if ( $meta && ( 'image' === $type || ! empty( $meta['sizes'] ) ) ) {
		$sizes = array();

		/** This filter is documented in wp-admin/includes/media.php */
		$possible_sizes = apply_filters(
			'image_size_names_choose',
			array(
				'thumbnail' => __( 'Thumbnail' ),
				'medium'    => __( 'Medium' ),
				'large'     => __( 'Large' ),
				'full'      => __( 'Full Size' ),
			)
		);
		unset( $possible_sizes['full'] );

		/*
		 * Loop through all potential sizes that may be chosen. Try to do this with some efficiency.
		 * First: run the image_downsize filter. If it returns something, we can use its data.
		 * If the filter does not return something, then image_downsize() is just an expensive way
		 * to check the image metadata, which we do second.
		 */
		foreach ( $possible_sizes as $size => $label ) {

			/** This filter is documented in wp-includes/media.php */
			$downsize = apply_filters( 'image_downsize', false, $attachment->ID, $size );

			if ( $downsize ) {
				if ( empty( $downsize[3] ) ) {
					continue;
				}

				$sizes[ $size ] = array(
					'height'      => $downsize[2],
					'width'       => $downsize[1],
					'url'         => $downsize[0],
					'orientation' => $downsize[2] > $downsize[1] ? 'portrait' : 'landscape',
				);
			} elseif ( isset( $meta['sizes'][ $size ] ) ) {
				// Nothing from the filter, so consult image metadata if we have it.
				$size_meta = $meta['sizes'][ $size ];

				/*
				 * We have the actual image size, but might need to further constrain it if content_width is narrower.
				 * Thumbnail, medium, and full sizes are also checked against the site's height/width options.
				 */
				list( $width, $height ) = image_constrain_size_for_editor( $size_meta['width'], $size_meta['height'], $size, 'edit' );

				$sizes[ $size ] = array(
					'height'      => $height,
					'width'       => $width,
					'url'         => $base_url . $size_meta['file'],
					'orientation' => $height > $width ? 'portrait' : 'landscape',
				);
			}
		}

		if ( 'image' === $type ) {
			if ( ! empty( $meta['original_image'] ) ) {
				$response['originalImageURL']  = wp_get_original_image_url( $attachment->ID );
				$response['originalImageName'] = wp_basename( wp_get_original_image_path( $attachment->ID ) );
			}

			$sizes['full'] = array( 'url' => $attachment_url );

			if ( isset( $meta['height'], $meta['width'] ) ) {
				$sizes['full']['height']      = $meta['height'];
				$sizes['full']['width']       = $meta['width'];
				$sizes['full']['orientation'] = $meta['height'] > $meta['width'] ? 'portrait' : 'landscape';
			}

			$response = array_merge( $response, $sizes['full'] );
		} elseif ( $meta['sizes']['full']['file'] ) {
			$sizes['full'] = array(
				'url'         => $base_url . $meta['sizes']['full']['file'],
				'height'      => $meta['sizes']['full']['height'],
				'width'       => $meta['sizes']['full']['width'],
				'orientation' => $meta['sizes']['full']['height'] > $meta['sizes']['full']['width'] ? 'portrait' : 'landscape',
			);
		}

		$response = array_merge( $response, array( 'sizes' => $sizes ) );
	}

	if ( $meta && 'video' === $type ) {
		if ( isset( $meta['width'] ) ) {
			$response['width'] = (int) $meta['width'];
		}
		if ( isset( $meta['height'] ) ) {
			$response['height'] = (int) $meta['height'];
		}
	}

	if ( $meta && ( 'audio' === $type || 'video' === $type ) ) {
		if ( isset( $meta['length_formatted'] ) ) {
			$response['fileLength']              = $meta['length_formatted'];
			$response['fileLengthHumanReadable'] = human_readable_duration( $meta['length_formatted'] );
		}

		$response['meta'] = array();
		foreach ( wp_get_attachment_id3_keys( $attachment, 'js' ) as $key => $label ) {
			$response['meta'][ $key ] = false;

			if ( ! empty( $meta[ $key ] ) ) {
				$response['meta'][ $key ] = $meta[ $key ];
			}
		}

		$id = get_post_thumbnail_id( $attachment->ID );
		if ( ! empty( $id ) ) {
			list( $src, $width, $height ) = wp_get_attachment_image_src( $id, 'full' );
			$response['image']            = compact( 'src', 'width', 'height' );
			list( $src, $width, $height ) = wp_get_attachment_image_src( $id, 'thumbnail' );
			$response['thumb']            = compact( 'src', 'width', 'height' );
		} else {
			$src               = wp_mime_type_icon( $attachment->ID, '.svg' );
			$width             = 48;
			$height            = 64;
			$response['image'] = compact( 'src', 'width', 'height' );
			$response['thumb'] = compact( 'src', 'width', 'height' );
		}
	}

	if ( function_exists( 'get_compat_media_markup' ) ) {
		$response['compat'] = get_compat_media_markup( $attachment->ID, array( 'in_modal' => true ) );
	}

	if ( function_exists( 'get_media_states' ) ) {
		$media_states = get_media_states( $attachment );
		if ( ! empty( $media_states ) ) {
			$response['mediaStates'] = implode( ', ', $media_states );
		}
	}

	/**
	 * Filters the attachment data prepared for JavaScript.
	 *
	 * @since 3.5.0
	 *
	 * @param array       $response   Array of prepared attachment data. See wp_prepare_attachment_for_js().
	 * @param WP_Post     $attachment Attachment object.
	 * @param array|false $meta       Array of attachment meta data, or false if there is none.
	 */
	return apply_filters( 'wp_prepare_attachment_for_js', $response, $attachment, $meta );
}

/**
 * Enqueues all scripts, styles, settings, and templates necessary to use
 * all media JS APIs.
 *
 * @since 3.5.0
 *
 * @global int       $content_width
 * @global wpdb      $wpdb          WordPress database abstraction object.
 * @global WP_Locale $wp_locale     WordPress date and time locale object.
 *
 * @param array $args {
 *     Arguments for enqueuing media scripts.
 *
 *     @type int|WP_Post $post Post ID or post object.
 * }
 */
function wp_enqueue_media( $args = array() ) {
	// Enqueue me just once per page, please.
	if ( did_action( 'wp_enqueue_media' ) ) {
		return;
	}

	global $content_width, $wpdb, $wp_locale;

	$defaults = array(
		'post' => null,
	);
	$args     = wp_parse_args( $args, $defaults );

	/*
	 * We're going to pass the old thickbox media tabs to `media_upload_tabs`
	 * to ensure plugins will work. We will then unset those tabs.
	 */
	$tabs = array(
		// handler action suffix => tab label
		'type'     => '',
		'type_url' => '',
		'gallery'  => '',
		'library'  => '',
	);

	/** This filter is documented in wp-admin/includes/media.php */
	$tabs = apply_filters( 'media_upload_tabs', $tabs );
	unset( $tabs['type'], $tabs['type_url'], $tabs['gallery'], $tabs['library'] );

	$props = array(
		'link'  => get_option( 'image_default_link_type' ), // DB default is 'file'.
		'align' => get_option( 'image_default_align' ),     // Empty default.
		'size'  => get_option( 'image_default_size' ),      // Empty default.
	);

	$exts      = array_merge( wp_get_audio_extensions(), wp_get_video_extensions() );
	$mimes     = get_allowed_mime_types();
	$ext_mimes = array();
	foreach ( $exts as $ext ) {
		foreach ( $mimes as $ext_preg => $mime_match ) {
			if ( preg_match( '#' . $ext . '#i', $ext_preg ) ) {
				$ext_mimes[ $ext ] = $mime_match;
				break;
			}
		}
	}

	/**
	 * Allows showing or hiding the "Create Audio Playlist" button in the media library.
	 *
	 * By default, the "Create Audio Playlist" button will always be shown in
	 * the media library.  If this filter returns `null`, a query will be run
	 * to determine whether the media library contains any audio items.  This
	 * was the default behavior prior to version 4.8.0, but this query is
	 * expensive for large media libraries.
	 *
	 * @since 4.7.4
	 * @since 4.8.0 The filter's default value is `true` rather than `null`.
	 *
	 * @link https://core.trac.wordpress.org/ticket/31071
	 *
	 * @param bool|null $show Whether to show the button, or `null` to decide based
	 *                        on whether any audio files exist in the media library.
	 */
	$show_audio_playlist = apply_filters( 'media_library_show_audio_playlist', true );
	if ( null === $show_audio_playlist ) {
		$show_audio_playlist = $wpdb->get_var(
			"SELECT ID
			FROM $wpdb->posts
			WHERE post_type = 'attachment'
			AND post_mime_type LIKE 'audio%'
			LIMIT 1"
		);
	}

	/**
	 * Allows showing or hiding the "Create Video Playlist" button in the media library.
	 *
	 * By default, the "Create Video Playlist" button will always be shown in
	 * the media library.  If this filter returns `null`, a query will be run
	 * to determine whether the media library contains any video items.  This
	 * was the default behavior prior to version 4.8.0, but this query is
	 * expensive for large media libraries.
	 *
	 * @since 4.7.4
	 * @since 4.8.0 The filter's default value is `true` rather than `null`.
	 *
	 * @link https://core.trac.wordpress.org/ticket/31071
	 *
	 * @param bool|null $show Whether to show the button, or `null` to decide based
	 *                        on whether any video files exist in the media library.
	 */
	$show_video_playlist = apply_filters( 'media_library_show_video_playlist', true );
	if ( null === $show_video_playlist ) {
		$show_video_playlist = $wpdb->get_var(
			"SELECT ID
			FROM $wpdb->posts
			WHERE post_type = 'attachment'
			AND post_mime_type LIKE 'video%'
			LIMIT 1"
		);
	}

	/**
	 * Allows overriding the list of months displayed in the media library.
	 *
	 * By default (if this filter does not return an array), a query will be
	 * run to determine the months that have media items.  This query can be
	 * expensive for large media libraries, so it may be desirable for sites to
	 * override this behavior.
	 *
	 * @since 4.7.4
	 *
	 * @link https://core.trac.wordpress.org/ticket/31071
	 *
	 * @param stdClass[]|null $months An array of objects with `month` and `year`
	 *                                properties, or `null` for default behavior.
	 */
	$months = apply_filters( 'media_library_months_with_files', null );
	if ( ! is_array( $months ) ) {
		$months = $wpdb->get_results(
			$wpdb->prepare(
				"SELECT DISTINCT YEAR( post_date ) AS year, MONTH( post_date ) AS month
				FROM $wpdb->posts
				WHERE post_type = %s
				ORDER BY post_date DESC",
				'attachment'
			)
		);
	}
	foreach ( $months as $month_year ) {
		$month_year->text = sprintf(
			/* translators: 1: Month, 2: Year. */
			__( '%1$s %2$d' ),
			$wp_locale->get_month( $month_year->month ),
			$month_year->year
		);
	}

	/**
	 * Filters whether the Media Library grid has infinite scrolling. Default `false`.
	 *
	 * @since 5.8.0
	 *
	 * @param bool $infinite Whether the Media Library grid has infinite scrolling.
	 */
	$infinite_scrolling = apply_filters( 'media_library_infinite_scrolling', false );

	$settings = array(
		'tabs'              => $tabs,
		'tabUrl'            => add_query_arg( array( 'chromeless' => true ), admin_url( 'media-upload.php' ) ),
		'mimeTypes'         => wp_list_pluck( get_post_mime_types(), 0 ),
		/** This filter is documented in wp-admin/includes/media.php */
		'captions'          => ! apply_filters( 'disable_captions', '' ),
		'nonce'             => array(
			'sendToEditor'           => wp_create_nonce( 'media-send-to-editor' ),
			'setAttachmentThumbnail' => wp_create_nonce( 'set-attachment-thumbnail' ),
		),
		'post'              => array(
			'id' => 0,
		),
		'defaultProps'      => $props,
		'attachmentCounts'  => array(
			'audio' => ( $show_audio_playlist ) ? 1 : 0,
			'video' => ( $show_video_playlist ) ? 1 : 0,
		),
		'oEmbedProxyUrl'    => rest_url( 'oembed/1.0/proxy' ),
		'embedExts'         => $exts,
		'embedMimes'        => $ext_mimes,
		'contentWidth'      => $content_width,
		'months'            => $months,
		'mediaTrash'        => MEDIA_TRASH ? 1 : 0,
		'infiniteScrolling' => ( $infinite_scrolling ) ? 1 : 0,
	);

	$post = null;
	if ( isset( $args['post'] ) ) {
		$post             = get_post( $args['post'] );
		$settings['post'] = array(
			'id'    => $post->ID,
			'nonce' => wp_create_nonce( 'update-post_' . $post->ID ),
		);

		$thumbnail_support = current_theme_supports( 'post-thumbnails', $post->post_type ) && post_type_supports( $post->post_type, 'thumbnail' );
		if ( ! $thumbnail_support && 'attachment' === $post->post_type && $post->post_mime_type ) {
			if ( wp_attachment_is( 'audio', $post ) ) {
				$thumbnail_support = post_type_supports( 'attachment:audio', 'thumbnail' ) || current_theme_supports( 'post-thumbnails', 'attachment:audio' );
			} elseif ( wp_attachment_is( 'video', $post ) ) {
				$thumbnail_support = post_type_supports( 'attachment:video', 'thumbnail' ) || current_theme_supports( 'post-thumbnails', 'attachment:video' );
			}
		}

		if ( $thumbnail_support ) {
			$featured_image_id                   = get_post_meta( $post->ID, '_thumbnail_id', true );
			$settings['post']['featuredImageId'] = $featured_image_id ? $featured_image_id : -1;
		}
	}

	if ( $post ) {
		$post_type_object = get_post_type_object( $post->post_type );
	} else {
		$post_type_object = get_post_type_object( 'post' );
	}

	$strings = array(
		// Generic.
		'mediaFrameDefaultTitle'      => __( 'Media' ),
		'url'                         => __( 'URL' ),
		'addMedia'                    => __( 'Add media' ),

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/media.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/media.php#L4571) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/media.php#L4571-L4958)

## [Changelog](https://developer.wordpress.org/reference/functions/wp_enqueue_media/\#changelog)

| Version | Description |
| --- | --- |
| [3.5.0](https://developer.wordpress.org/reference/since/3.5.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/functions/wp_enqueue_media/\#user-contributed-notes)

1. [Skip to note 3 content](https://developer.wordpress.org/reference/functions/wp_enqueue_media/#comment-content-1961)



This function should be called from the `['admin\_enqueue\_scripts'](https://developer.wordpress.org/reference/hooks/admin_enqueue_scripts/)` action hook, or later.





[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_enqueue_media%2F%3Freplytocom%3D1961%23feedback-editor-1961)

2. [Skip to note 4 content](https://developer.wordpress.org/reference/functions/wp_enqueue_media/#comment-content-752)



Enqueue the media scripts for a particular post:





`wp-includes/media.php`
[Copy](https://developer.wordpress.org/reference/functions/wp_enqueue_media/#)




```php
<?php
$args = array( 'post' => 34 );
wp_enqueue_media( $args );
?>
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_enqueue_media%2F%3Freplytocom%3D752%23feedback-editor-752)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_enqueue_media%2F) before being able to contribute a note or feedback.

Notifications