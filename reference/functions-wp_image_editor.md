---
url: https://developer.wordpress.org/reference/functions/wp_image_editor
scraped_at: 2025-10-20T03:16:53.506Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/wp_image_editor/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp\_image\_editor()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)wp\_image\_editor()

Search

# wp\_image\_editor( int$post\_id, false\|object$msg = false )

## In this article

Table of Contents

- [Parameters](https://developer.wordpress.org/reference/functions/wp_image_editor/#parameters)
- [Source](https://developer.wordpress.org/reference/functions/wp_image_editor/#source)
- [Hooks](https://developer.wordpress.org/reference/functions/wp_image_editor/#hooks)
- [Related](https://developer.wordpress.org/reference/functions/wp_image_editor/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/wp_image_editor/#changelog)

[↑ Back to top](https://developer.wordpress.org/reference/functions/wp_image_editor/#wp--skip-link--target)

Loads the WP image-editing interface.

## [Parameters](https://developer.wordpress.org/reference/functions/wp_image_editor/\#parameters)

`$post_id` intrequired

Attachment post ID.

`$msg` false\|objectoptional

Message to display for image editor updates or errors.

Default: `false`

## [Source](https://developer.wordpress.org/reference/functions/wp_image_editor/\#source)

`wp-admin/includes/image-edit.php`
[Expand code](https://developer.wordpress.org/reference/functions/wp_image_editor/#)

[Copy](https://developer.wordpress.org/reference/functions/wp_image_editor/#)

```php
function wp_image_editor( $post_id, $msg = false ) {
	$nonce     = wp_create_nonce( "image_editor-$post_id" );
	$meta      = wp_get_attachment_metadata( $post_id );
	$thumb     = image_get_intermediate_size( $post_id, 'thumbnail' );
	$sub_sizes = isset( $meta['sizes'] ) && is_array( $meta['sizes'] );
	$note      = '';

	if ( isset( $meta['width'], $meta['height'] ) ) {
		$big = max( $meta['width'], $meta['height'] );
	} else {
		die( __( 'Image data does not exist. Please re-upload the image.' ) );
	}

	$sizer = $big > 600 ? 600 / $big : 1;

	$backup_sizes = get_post_meta( $post_id, '_wp_attachment_backup_sizes', true );
	$can_restore  = false;

	if ( ! empty( $backup_sizes ) && isset( $backup_sizes['full-orig'], $meta['file'] ) ) {
		$can_restore = wp_basename( $meta['file'] ) !== $backup_sizes['full-orig']['file'];
	}

	if ( $msg ) {
		if ( isset( $msg->error ) ) {
			$note = "<div class='notice notice-error' role='alert'><p>$msg->error</p></div>";
		} elseif ( isset( $msg->msg ) ) {
			$note = "<div class='notice notice-success' role='alert'><p>$msg->msg</p></div>";
		}
	}

	/**
	 * Shows the settings in the Image Editor that allow selecting to edit only the thumbnail of an image.
	 *
	 * @since 6.3.0
	 *
	 * @param bool $show Whether to show the settings in the Image Editor. Default false.
	 */
	$edit_thumbnails_separately = (bool) apply_filters( 'image_edit_thumbnails_separately', false );

	?>
	<div class="imgedit-wrap wp-clearfix">
	<div id="imgedit-panel-<?php echo $post_id; ?>">
	<?php echo $note; ?>
	<div class="imgedit-panel-content imgedit-panel-tools wp-clearfix">
		<div class="imgedit-menu wp-clearfix">
			<button type="button" onclick="imageEdit.toggleCropTool( <?php echo "$post_id, '$nonce'"; ?>, this );" aria-expanded="false" aria-controls="imgedit-crop" class="imgedit-crop button disabled" disabled><?php esc_html_e( 'Crop' ); ?></button>
			<button type="button" class="imgedit-scale button" onclick="imageEdit.toggleControls(this);" aria-expanded="false" aria-controls="imgedit-scale"><?php esc_html_e( 'Scale' ); ?></button>
			<div class="imgedit-rotate-menu-container">
				<button type="button" aria-controls="imgedit-rotate-menu" class="imgedit-rotate button" aria-expanded="false" onclick="imageEdit.togglePopup(this)" onblur="imageEdit.monitorPopup()"><?php esc_html_e( 'Image Rotation' ); ?></button>
				<div id="imgedit-rotate-menu" class="imgedit-popup-menu">
			<?php
			// On some setups GD library does not provide imagerotate() - Ticket #11536.
			if ( wp_image_editor_supports(
				array(
					'mime_type' => get_post_mime_type( $post_id ),
					'methods'   => array( 'rotate' ),
				)
			) ) {
				$note_no_rotate = '';
				?>
					<button type="button" class="imgedit-rleft button" onkeydown="imageEdit.browsePopup(event, this)" onclick="imageEdit.rotate( 90, <?php echo "$post_id, '$nonce'"; ?>, this)" onblur="imageEdit.monitorPopup()"><?php esc_html_e( 'Rotate 90&deg; left' ); ?></button>
					<button type="button" class="imgedit-rright button" onkeydown="imageEdit.browsePopup(event, this)" onclick="imageEdit.rotate(-90, <?php echo "$post_id, '$nonce'"; ?>, this)" onblur="imageEdit.monitorPopup()"><?php esc_html_e( 'Rotate 90&deg; right' ); ?></button>
					<button type="button" class="imgedit-rfull button" onkeydown="imageEdit.browsePopup(event, this)" onclick="imageEdit.rotate(180, <?php echo "$post_id, '$nonce'"; ?>, this)" onblur="imageEdit.monitorPopup()"><?php esc_html_e( 'Rotate 180&deg;' ); ?></button>
				<?php
			} else {
				$note_no_rotate = '<p class="note-no-rotate"><em>' . __( 'Image rotation is not supported by your web host.' ) . '</em></p>';
				?>
					<button type="button" class="imgedit-rleft button disabled" disabled></button>
					<button type="button" class="imgedit-rright button disabled" disabled></button>
				<?php
			}
			?>
					<hr />
					<button type="button" onkeydown="imageEdit.browsePopup(event, this)" onclick="imageEdit.flip(1, <?php echo "$post_id, '$nonce'"; ?>, this)" onblur="imageEdit.monitorPopup()" class="imgedit-flipv button"><?php esc_html_e( 'Flip vertical' ); ?></button>
					<button type="button" onkeydown="imageEdit.browsePopup(event, this)" onclick="imageEdit.flip(2, <?php echo "$post_id, '$nonce'"; ?>, this)" onblur="imageEdit.monitorPopup()" class="imgedit-fliph button"><?php esc_html_e( 'Flip horizontal' ); ?></button>
					<?php echo $note_no_rotate; ?>
				</div>
			</div>
		</div>
		<div class="imgedit-submit imgedit-menu">
			<button type="button" id="image-undo-<?php echo $post_id; ?>" onclick="imageEdit.undo(<?php echo "$post_id, '$nonce'"; ?>, this)" class="imgedit-undo button disabled" disabled><?php esc_html_e( 'Undo' ); ?></button>
			<button type="button" id="image-redo-<?php echo $post_id; ?>" onclick="imageEdit.redo(<?php echo "$post_id, '$nonce'"; ?>, this)" class="imgedit-redo button disabled" disabled><?php esc_html_e( 'Redo' ); ?></button>
			<button type="button" onclick="imageEdit.close(<?php echo $post_id; ?>, 1)" class="button imgedit-cancel-btn"><?php esc_html_e( 'Cancel Editing' ); ?></button>
			<button type="button" onclick="imageEdit.save(<?php echo "$post_id, '$nonce'"; ?>)" disabled="disabled" class="button button-primary imgedit-submit-btn"><?php esc_html_e( 'Save Edits' ); ?></button>
		</div>
	</div>

	<div class="imgedit-panel-content wp-clearfix">
		<div class="imgedit-tools">
			<input type="hidden" id="imgedit-nonce-<?php echo $post_id; ?>" value="<?php echo $nonce; ?>" />
			<input type="hidden" id="imgedit-sizer-<?php echo $post_id; ?>" value="<?php echo $sizer; ?>" />
			<input type="hidden" id="imgedit-history-<?php echo $post_id; ?>" value="" />
			<input type="hidden" id="imgedit-undone-<?php echo $post_id; ?>" value="0" />
			<input type="hidden" id="imgedit-selection-<?php echo $post_id; ?>" value="" />
			<input type="hidden" id="imgedit-x-<?php echo $post_id; ?>" value="<?php echo isset( $meta['width'] ) ? $meta['width'] : 0; ?>" />
			<input type="hidden" id="imgedit-y-<?php echo $post_id; ?>" value="<?php echo isset( $meta['height'] ) ? $meta['height'] : 0; ?>" />

			<div id="imgedit-crop-<?php echo $post_id; ?>" class="imgedit-crop-wrap">
			<div class="imgedit-crop-grid"></div>
			<img id="image-preview-<?php echo $post_id; ?>" onload="imageEdit.imgLoaded('<?php echo $post_id; ?>')"
				src="<?php echo esc_url( admin_url( 'admin-ajax.php', 'relative' ) ) . '?action=imgedit-preview&amp;_ajax_nonce=' . $nonce . '&amp;postid=' . $post_id . '&amp;rand=' . rand( 1, 99999 ); ?>" alt="" />
			</div>
		</div>
		<div class="imgedit-settings">
			<div class="imgedit-tool-active">
				<div class="imgedit-group">
				<div id="imgedit-scale" tabindex="-1" class="imgedit-group-controls">
					<div class="imgedit-group-top">
						<h2><?php _e( 'Scale Image' ); ?></h2>
						<button type="button" class="dashicons dashicons-editor-help imgedit-help-toggle" onclick="imageEdit.toggleHelp(this);" aria-expanded="false"><span class="screen-reader-text">
						<?php
						/* translators: Hidden accessibility text. */
						esc_html_e( 'Scale Image Help' );
						?>
						</span></button>
						<div class="imgedit-help">
						<p><?php _e( 'You can proportionally scale the original image. For best results, scaling should be done before you crop, flip, or rotate. Images can only be scaled down, not up.' ); ?></p>
						</div>
						<?php if ( isset( $meta['width'], $meta['height'] ) ) : ?>
						<p>
							<?php
							printf(
								/* translators: %s: Image width and height in pixels. */
								__( 'Original dimensions %s' ),
								'<span class="imgedit-original-dimensions">' . $meta['width'] . ' &times; ' . $meta['height'] . '</span>'
							);
							?>
						</p>
						<?php endif; ?>
						<div class="imgedit-submit">
						<fieldset class="imgedit-scale-controls">
							<legend><?php _e( 'New dimensions:' ); ?></legend>
							<div class="nowrap">
							<label for="imgedit-scale-width-<?php echo $post_id; ?>" class="screen-reader-text">
							<?php
							/* translators: Hidden accessibility text. */
							_e( 'scale height' );
							?>
							</label>
							<input type="number" step="1" min="0" max="<?php echo isset( $meta['width'] ) ? $meta['width'] : ''; ?>" aria-describedby="imgedit-scale-warn-<?php echo $post_id; ?>"  id="imgedit-scale-width-<?php echo $post_id; ?>" onkeyup="imageEdit.scaleChanged(<?php echo $post_id; ?>, 1, this)" onblur="imageEdit.scaleChanged(<?php echo $post_id; ?>, 1, this)" value="<?php echo isset( $meta['width'] ) ? $meta['width'] : 0; ?>" />
							<span class="imgedit-separator" aria-hidden="true">&times;</span>
							<label for="imgedit-scale-height-<?php echo $post_id; ?>" class="screen-reader-text"><?php _e( 'scale height' ); ?></label>
							<input type="number" step="1" min="0" max="<?php echo isset( $meta['height'] ) ? $meta['height'] : ''; ?>" aria-describedby="imgedit-scale-warn-<?php echo $post_id; ?>" id="imgedit-scale-height-<?php echo $post_id; ?>" onkeyup="imageEdit.scaleChanged(<?php echo $post_id; ?>, 0, this)" onblur="imageEdit.scaleChanged(<?php echo $post_id; ?>, 0, this)" value="<?php echo isset( $meta['height'] ) ? $meta['height'] : 0; ?>" />
							<button id="imgedit-scale-button" type="button" onclick="imageEdit.action(<?php echo "$post_id, '$nonce'"; ?>, 'scale')" class="button button-primary"><?php esc_html_e( 'Scale' ); ?></button>
							</div>
							<span class="imgedit-scale-warn" id="imgedit-scale-warn-<?php echo $post_id; ?>"><span class="dashicons dashicons-warning" aria-hidden="true"></span><?php esc_html_e( 'Images cannot be scaled to a size larger than the original.' ); ?></span>
						</fieldset>
						</div>
					</div>
				</div>
			</div>

		<?php if ( $can_restore ) { ?>
				<div class="imgedit-group">
				<div class="imgedit-group-top">
					<h2><button type="button" onclick="imageEdit.toggleHelp(this);" class="button-link" aria-expanded="false"><?php _e( 'Restore original image' ); ?> <span class="dashicons dashicons-arrow-down imgedit-help-toggle"></span></button></h2>
					<div class="imgedit-help imgedit-restore">
					<p>
					<?php
					_e( 'Discard any changes and restore the original image.' );
					if ( ! defined( 'IMAGE_EDIT_OVERWRITE' ) || ! IMAGE_EDIT_OVERWRITE ) {
						echo ' ' . __( 'Previously edited copies of the image will not be deleted.' );
					}
					?>
					</p>
					<div class="imgedit-submit">
						<input type="button" onclick="imageEdit.action(<?php echo "$post_id, '$nonce'"; ?>, 'restore')" class="button button-primary" value="<?php esc_attr_e( 'Restore image' ); ?>" <?php echo $can_restore; ?> />
					</div>
				</div>
			</div>
			</div>
		<?php } ?>
			<div class="imgedit-group">
				<div id="imgedit-crop" tabindex="-1" class="imgedit-group-controls">
				<div class="imgedit-group-top">
					<h2><?php _e( 'Crop Image' ); ?></h2>
					<button type="button" class="dashicons dashicons-editor-help imgedit-help-toggle" onclick="imageEdit.toggleHelp(this);" aria-expanded="false"><span class="screen-reader-text">
					<?php
					/* translators: Hidden accessibility text. */
					_e( 'Image Crop Help' );
					?>
					</span></button>
					<div class="imgedit-help">
						<p><?php _e( 'To crop the image, click on it and drag to make your selection.' ); ?></p>
						<p><strong><?php _e( 'Crop Aspect Ratio' ); ?></strong><br />
						<?php _e( 'The aspect ratio is the relationship between the width and height. You can preserve the aspect ratio by holding down the shift key while resizing your selection. Use the input box to specify the aspect ratio, e.g. 1:1 (square), 4:3, 16:9, etc.' ); ?></p>

						<p><strong><?php _e( 'Crop Selection' ); ?></strong><br />
						<?php _e( 'Once you have made your selection, you can adjust it by entering the size in pixels. The minimum selection size is the thumbnail size as set in the Media settings.' ); ?></p>
					</div>
				</div>
				<fieldset class="imgedit-crop-ratio">
					<legend><?php _e( 'Aspect ratio:' ); ?></legend>
					<div class="nowrap">
					<label for="imgedit-crop-width-<?php echo $post_id; ?>" class="screen-reader-text">
					<?php
					/* translators: Hidden accessibility text. */
					_e( 'crop ratio width' );
					?>
					</label>
					<input type="number" step="1" min="1" id="imgedit-crop-width-<?php echo $post_id; ?>" onkeyup="imageEdit.setRatioSelection(<?php echo $post_id; ?>, 0, this)" onblur="imageEdit.setRatioSelection(<?php echo $post_id; ?>, 0, this)" />
					<span class="imgedit-separator" aria-hidden="true">:</span>
					<label for="imgedit-crop-height-<?php echo $post_id; ?>" class="screen-reader-text">
					<?php
					/* translators: Hidden accessibility text. */
					_e( 'crop ratio height' );
					?>
					</label>
					<input  type="number" step="1" min="0" id="imgedit-crop-height-<?php echo $post_id; ?>" onkeyup="imageEdit.setRatioSelection(<?php echo $post_id; ?>, 1, this)" onblur="imageEdit.setRatioSelection(<?php echo $post_id; ?>, 1, this)" />
					</div>
				</fieldset>
				<fieldset id="imgedit-crop-sel-<?php echo $post_id; ?>" class="imgedit-crop-sel">
					<legend><?php _e( 'Selection:' ); ?></legend>
					<div class="nowrap">
					<label for="imgedit-sel-width-<?php echo $post_id; ?>" class="screen-reader-text">
					<?php
					/* translators: Hidden accessibility text. */
					_e( 'selection width' );
					?>
					</label>
					<input  type="number" step="1" min="0" id="imgedit-sel-width-<?php echo $post_id; ?>" onkeyup="imageEdit.setNumSelection(<?php echo $post_id; ?>, this)" onblur="imageEdit.setNumSelection(<?php echo $post_id; ?>, this)" />
					<span class="imgedit-separator" aria-hidden="true">&times;</span>
					<label for="imgedit-sel-height-<?php echo $post_id; ?>" class="screen-reader-text">
					<?php
					/* translators: Hidden accessibility text. */
					_e( 'selection height' );
					?>
					</label>
					<input  type="number" step="1" min="0" id="imgedit-sel-height-<?php echo $post_id; ?>" onkeyup="imageEdit.setNumSelection(<?php echo $post_id; ?>, this)" onblur="imageEdit.setNumSelection(<?php echo $post_id; ?>, this)" />
					</div>
				</fieldset>
				<fieldset id="imgedit-crop-sel-<?php echo $post_id; ?>" class="imgedit-crop-sel">
					<legend><?php _e( 'Starting Coordinates:' ); ?></legend>
					<div class="nowrap">
					<label for="imgedit-start-x-<?php echo $post_id; ?>" class="screen-reader-text">
					<?php
					/* translators: Hidden accessibility text. */
					_e( 'horizontal start position' );
					?>
					</label>
					<input  type="number" step="1" min="0" id="imgedit-start-x-<?php echo $post_id; ?>" onkeyup="imageEdit.setNumSelection(<?php echo $post_id; ?>, this)" onblur="imageEdit.setNumSelection(<?php echo $post_id; ?>, this)" value="0" />
					<span class="imgedit-separator" aria-hidden="true">&times;</span>
					<label for="imgedit-start-y-<?php echo $post_id; ?>" class="screen-reader-text">
					<?php
					/* translators: Hidden accessibility text. */
					_e( 'vertical start position' );
					?>
					</label>
					<input  type="number" step="1" min="0" id="imgedit-start-y-<?php echo $post_id; ?>" onkeyup="imageEdit.setNumSelection(<?php echo $post_id; ?>, this)" onblur="imageEdit.setNumSelection(<?php echo $post_id; ?>, this)" value="0" />
					</div>
				</fieldset>
				<div class="imgedit-crop-apply imgedit-menu container">
					<button class="button-primary" type="button" onclick="imageEdit.handleCropToolClick( <?php echo "$post_id, '$nonce'"; ?>, this );" class="imgedit-crop-apply button"><?php esc_html_e( 'Apply Crop' ); ?></button> <button type="button" onclick="imageEdit.handleCropToolClick( <?php echo "$post_id, '$nonce'"; ?>, this );" class="imgedit-crop-clear button" disabled="disabled"><?php esc_html_e( 'Clear Crop' ); ?></button>
				</div>
			</div>
		</div>
	</div>

	<?php
	if ( $edit_thumbnails_separately && $thumb && $sub_sizes ) {
		$thumb_img = wp_constrain_dimensions( $thumb['width'], $thumb['height'], 160, 120 );
		?>

	<div class="imgedit-group imgedit-applyto">
		<div class="imgedit-group-top">
			<h2><?php _e( 'Thumbnail Settings' ); ?></h2>
			<button type="button" class="dashicons dashicons-editor-help imgedit-help-toggle" onclick="imageEdit.toggleHelp(this);" aria-expanded="false"><span class="screen-reader-text">
			<?php
			/* translators: Hidden accessibility text. */
			esc_html_e( 'Thumbnail Settings Help' );
			?>
			</span></button>
			<div class="imgedit-help">
			<p><?php _e( 'You can edit the image while preserving the thumbnail. For example, you may wish to have a square thumbnail that displays just a section of the image.' ); ?></p>
			</div>
		</div>
		<div class="imgedit-thumbnail-preview-group">
			<figure class="imgedit-thumbnail-preview">
				<img src="<?php echo esc_url( $thumb['url'] ); ?>" width="<?php echo esc_attr( $thumb_img[0] ); ?>" height="<?php echo esc_attr( $thumb_img[1] ); ?>" class="imgedit-size-preview" alt="" draggable="false" />
				<figcaption class="imgedit-thumbnail-preview-caption"><?php _e( 'Current thumbnail' ); ?></figcaption>
			</figure>
			<div id="imgedit-save-target-<?php echo $post_id; ?>" class="imgedit-save-target">
			<fieldset>
				<legend><?php _e( 'Apply changes to:' ); ?></legend>

				<span class="imgedit-label">
					<input type="radio" id="imgedit-target-all" name="imgedit-target-<?php echo $post_id; ?>" value="all" checked="checked" />
					<label for="imgedit-target-all"><?php _e( 'All image sizes' ); ?></label>
				</span>

				<span class="imgedit-label">
					<input type="radio" id="imgedit-target-thumbnail" name="imgedit-target-<?php echo $post_id; ?>" value="thumbnail" />
					<label for="imgedit-target-thumbnail"><?php _e( 'Thumbnail' ); ?></label>
				</span>

				<span class="imgedit-label">
					<input type="radio" id="imgedit-target-nothumb" name="imgedit-target-<?php echo $post_id; ?>" value="nothumb" />
					<label for="imgedit-target-nothumb"><?php _e( 'All sizes except thumbnail' ); ?></label>
				</span>

				</fieldset>
			</div>
		</div>
	</div>
	<?php } ?>
		</div>
	</div>

	</div>

	<div class="imgedit-wait" id="imgedit-wait-<?php echo $post_id; ?>"></div>
	<div class="hidden" id="imgedit-leaving-<?php echo $post_id; ?>"><?php _e( "There are unsaved changes that will be lost. 'OK' to continue, 'Cancel' to return to the Image Editor." ); ?></div>
	</div>
	<?php
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-admin/includes/image-edit.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-admin/includes/image-edit.php#L18) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-admin/includes/image-edit.php#L18-L332)

## [Hooks](https://developer.wordpress.org/reference/functions/wp_image_editor/\#hooks)

[apply\_filters( ‘image\_edit\_thumbnails\_separately’, bool$show )](https://developer.wordpress.org/reference/hooks/image_edit_thumbnails_separately/)

Shows the settings in the Image Editor that allow selecting to edit only the thumbnail of an image.

## [Related](https://developer.wordpress.org/reference/functions/wp_image_editor/\#related)

| Uses | Description |
| --- | --- |
| [wp\_basename()](https://developer.wordpress.org/reference/functions/wp_basename/) `wp-includes/formatting.php` | i18n-friendly version of basename(). |
| [wp\_create\_nonce()](https://developer.wordpress.org/reference/functions/wp_create_nonce/) `wp-includes/pluggable.php` | Creates a cryptographic token tied to a specific action, user, user session, and window of time. |
| [wp\_get\_attachment\_metadata()](https://developer.wordpress.org/reference/functions/wp_get_attachment_metadata/) `wp-includes/post.php` | Retrieves attachment metadata for attachment ID. |
| [get\_post\_mime\_type()](https://developer.wordpress.org/reference/functions/get_post_mime_type/) `wp-includes/post.php` | Retrieves the mime type of an attachment based on the ID. |
| [esc\_url()](https://developer.wordpress.org/reference/functions/esc_url/) `wp-includes/formatting.php` | Checks and cleans a URL. |
| [esc\_attr()](https://developer.wordpress.org/reference/functions/esc_attr/) `wp-includes/formatting.php` | Escaping for HTML attributes. |
| [admin\_url()](https://developer.wordpress.org/reference/functions/admin_url/) `wp-includes/link-template.php` | Retrieves the URL to the admin area for the current site. |
| [apply\_filters()](https://developer.wordpress.org/reference/functions/apply_filters/) `wp-includes/plugin.php` | Calls the callback functions that have been added to a filter hook. |
| [get\_post\_meta()](https://developer.wordpress.org/reference/functions/get_post_meta/) `wp-includes/post.php` | Retrieves a post meta field for the given post ID. |

[Show 5 more](https://developer.wordpress.org/reference/functions/wp_image_editor/#) [Show less](https://developer.wordpress.org/reference/functions/wp_image_editor/#)

| Used by | Description |
| --- | --- |
| [edit\_form\_image\_editor()](https://developer.wordpress.org/reference/functions/edit_form_image_editor/) `wp-admin/includes/media.php` | Displays the image and editor in the post editor |
| [wp\_ajax\_image\_editor()](https://developer.wordpress.org/reference/functions/wp_ajax_image_editor/) `wp-admin/includes/ajax-actions.php` | Handles image editing via AJAX. |

## [Changelog](https://developer.wordpress.org/reference/functions/wp_image_editor/\#changelog)

| Version | Description |
| --- | --- |
| [2.9.0](https://developer.wordpress.org/reference/since/2.9.0/) | Introduced. |

## User Contributed Notes

You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_image_editor%2F) before being able to contribute a note or feedback.

Notifications