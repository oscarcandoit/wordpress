---
url: https://developer.wordpress.org/reference/functions/wp_get_attachment_metadata
scraped_at: 2025-10-20T03:16:50.053Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/wp_get_attachment_metadata/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp\_get\_attachment\_metadata()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)wp\_get\_attachment\_metadata()

Search

# wp\_get\_attachment\_metadata( int$attachment\_id, bool$unfiltered = false ): array\|false

## In this article

Table of Contents

- [Parameters](https://developer.wordpress.org/reference/functions/wp_get_attachment_metadata/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/wp_get_attachment_metadata/#return)
- [Source](https://developer.wordpress.org/reference/functions/wp_get_attachment_metadata/#source)
- [Hooks](https://developer.wordpress.org/reference/functions/wp_get_attachment_metadata/#hooks)
- [Related](https://developer.wordpress.org/reference/functions/wp_get_attachment_metadata/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/wp_get_attachment_metadata/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/functions/wp_get_attachment_metadata/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/functions/wp_get_attachment_metadata/#wp--skip-link--target)

Retrieves attachment metadata for attachment ID.

## [Parameters](https://developer.wordpress.org/reference/functions/wp_get_attachment_metadata/\#parameters)

`$attachment_id` intrequired

Attachment post ID. Defaults to global $post.

`$unfiltered` booloptional

If true, filters are not run.

Default: `false`

## [Return](https://developer.wordpress.org/reference/functions/wp_get_attachment_metadata/\#return)

array\|false Attachment metadata. False on failure.

- `width` int
The width of the attachment.

- `height` int
The height of the attachment.

- `file` string
The file path relative to `wp-content/uploads`.

- `sizes` array
Keys are size slugs, each value is an array containing `'file'`, `'width'`, `'height'`, and `'mime-type'`.

- `image_meta` array
Image metadata.

- `filesize` int
File size of the attachment.


## [Source](https://developer.wordpress.org/reference/functions/wp_get_attachment_metadata/\#source)

`wp-includes/post.php`
[Expand code](https://developer.wordpress.org/reference/functions/wp_get_attachment_metadata/#)

[Copy](https://developer.wordpress.org/reference/functions/wp_get_attachment_metadata/#)

```php
function wp_get_attachment_metadata( $attachment_id = 0, $unfiltered = false ) {
	$attachment_id = (int) $attachment_id;

	if ( ! $attachment_id ) {
		$post = get_post();

		if ( ! $post ) {
			return false;
		}

		$attachment_id = $post->ID;
	}

	$data = get_post_meta( $attachment_id, '_wp_attachment_metadata', true );

	if ( ! $data ) {
		return false;
	}

	if ( $unfiltered ) {
		return $data;
	}

	/**
	 * Filters the attachment meta data.
	 *
	 * @since 2.1.0
	 *
	 * @param array $data          Array of meta data for the given attachment.
	 * @param int   $attachment_id Attachment post ID.
	 */
	return apply_filters( 'wp_get_attachment_metadata', $data, $attachment_id );
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/post.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/post.php#L6804) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/post.php#L6804-L6836)

## [Hooks](https://developer.wordpress.org/reference/functions/wp_get_attachment_metadata/\#hooks)

[apply\_filters( ‘wp\_get\_attachment\_metadata’, array$data, int$attachment\_id )](https://developer.wordpress.org/reference/hooks/wp_get_attachment_metadata/)

Filters the attachment meta data.

## [Related](https://developer.wordpress.org/reference/functions/wp_get_attachment_metadata/\#related)

| Uses | Description |
| --- | --- |
| [apply\_filters()](https://developer.wordpress.org/reference/functions/apply_filters/) `wp-includes/plugin.php` | Calls the callback functions that have been added to a filter hook. |
| [get\_post\_meta()](https://developer.wordpress.org/reference/functions/get_post_meta/) `wp-includes/post.php` | Retrieves a post meta field for the given post ID. |
| [get\_post()](https://developer.wordpress.org/reference/functions/get_post/) `wp-includes/post.php` | Retrieves post data given a post ID or post object. |

[Show 1 more](https://developer.wordpress.org/reference/functions/wp_get_attachment_metadata/#) [Show less](https://developer.wordpress.org/reference/functions/wp_get_attachment_metadata/#)

| Used by | Description |
| --- | --- |
| [WP\_REST\_Attachments\_Controller::edit\_media\_item()](https://developer.wordpress.org/reference/classes/wp_rest_attachments_controller/edit_media_item/) `wp-includes/rest-api/endpoints/class-wp-rest-attachments-controller.php` | Applies edits to a media item and creates a new attachment record. |
| [wp\_get\_original\_image\_path()](https://developer.wordpress.org/reference/functions/wp_get_original_image_path/) `wp-includes/post.php` | Retrieves the path to an uploaded image file. |
| [wp\_get\_original\_image\_url()](https://developer.wordpress.org/reference/functions/wp_get_original_image_url/) `wp-includes/post.php` | Retrieves the URL to an original attachment image. |
| [wp\_get\_missing\_image\_subsizes()](https://developer.wordpress.org/reference/functions/wp_get_missing_image_subsizes/) `wp-admin/includes/image.php` | Compare the existing image sub-sizes (as saved in the attachment meta) to the currently registered image sub-sizes, and return the difference. |
| [wp\_update\_image\_subsizes()](https://developer.wordpress.org/reference/functions/wp_update_image_subsizes/) `wp-admin/includes/image.php` | If any of the currently registered image sub-sizes are missing, create them and update the image meta data. |
| [WP\_Widget\_Media\_Image::render\_media()](https://developer.wordpress.org/reference/classes/wp_widget_media_image/render_media/) `wp-includes/widgets/class-wp-widget-media-image.php` | Render the media on the frontend. |
| [WP\_Customize\_Manager::import\_theme\_starter\_content()](https://developer.wordpress.org/reference/classes/wp_customize_manager/import_theme_starter_content/) `wp-includes/class-wp-customize-manager.php` | Imports theme starter content into the customized state. |
| [WP\_REST\_Attachments\_Controller::prepare\_item\_for\_response()](https://developer.wordpress.org/reference/classes/wp_rest_attachments_controller/prepare_item_for_response/) `wp-includes/rest-api/endpoints/class-wp-rest-attachments-controller.php` | Prepares a single attachment output for response. |
| [wp\_restore\_image()](https://developer.wordpress.org/reference/functions/wp_restore_image/) `wp-admin/includes/image-edit.php` | Restores the metadata for a given attachment. |
| [wp\_save\_image()](https://developer.wordpress.org/reference/functions/wp_save_image/) `wp-admin/includes/image-edit.php` | Saves image to post, along with enqueued changes in `$_REQUEST['history']`. |
| [wp\_image\_editor()](https://developer.wordpress.org/reference/functions/wp_image_editor/) `wp-admin/includes/image-edit.php` | Loads the WP image-editing interface. |
| [edit\_form\_image\_editor()](https://developer.wordpress.org/reference/functions/edit_form_image_editor/) `wp-admin/includes/media.php` | Displays the image and editor in the post editor |
| [attachment\_submitbox\_metadata()](https://developer.wordpress.org/reference/functions/attachment_submitbox_metadata/) `wp-admin/includes/media.php` | Displays non-editable attachment metadata in the publish meta box. |
| [get\_media\_item()](https://developer.wordpress.org/reference/functions/get_media_item/) `wp-admin/includes/media.php` | Retrieves HTML form for modifying the image attachment. |
| [edit\_post()](https://developer.wordpress.org/reference/functions/edit_post/) `wp-admin/includes/post.php` | Updates an existing post with values provided in `$_POST`. |
| [wp\_ajax\_save\_attachment()](https://developer.wordpress.org/reference/functions/wp_ajax_save_attachment/) `wp-admin/includes/ajax-actions.php` | Handles updating attachment attributes via AJAX. |
| [attachment\_id3\_data\_meta\_box()](https://developer.wordpress.org/reference/functions/attachment_id3_data_meta_box/) `wp-admin/includes/meta-boxes.php` | Displays fields for ID3 data. |
| [Custom\_Image\_Header::step\_2()](https://developer.wordpress.org/reference/classes/custom_image_header/step_2/) `wp-admin/includes/class-custom-image-header.php` | Displays second step of custom header image page. |
| [get\_uploaded\_header\_images()](https://developer.wordpress.org/reference/functions/get_uploaded_header_images/) `wp-includes/theme.php` | Gets the header images uploaded for the active theme. |
| [prepend\_attachment()](https://developer.wordpress.org/reference/functions/prepend_attachment/) `wp-includes/post-template.php` | Wraps attachment in paragraph tag before content. |
| [wp\_delete\_attachment()](https://developer.wordpress.org/reference/functions/wp_delete_attachment/) `wp-includes/post.php` | Trashes or deletes an attachment. |
| [wp\_get\_attachment\_thumb\_file()](https://developer.wordpress.org/reference/functions/wp_get_attachment_thumb_file/) `wp-includes/deprecated.php` | Retrieves thumbnail for an attachment. |
| [wp\_xmlrpc\_server::\_prepare\_media\_item()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/_prepare_media_item/) `wp-includes/class-wp-xmlrpc-server.php` | Prepares media item data for return in an XML-RPC object. |

[Show 18 more](https://developer.wordpress.org/reference/functions/wp_get_attachment_metadata/#) [Show less](https://developer.wordpress.org/reference/functions/wp_get_attachment_metadata/#)

## [Changelog](https://developer.wordpress.org/reference/functions/wp_get_attachment_metadata/\#changelog)

| Version | Description |
| --- | --- |
| [6.0.0](https://developer.wordpress.org/reference/since/6.0.0/) | The `$filesize` value was added to the returned array. |
| [2.1.0](https://developer.wordpress.org/reference/since/2.1.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/functions/wp_get_attachment_metadata/\#user-contributed-notes)

1. [Skip to note 5 content](https://developer.wordpress.org/reference/functions/wp_get_attachment_metadata/#comment-content-808)



Example return value





`wp-includes/post.php`
[Expand code](https://developer.wordpress.org/reference/functions/wp_get_attachment_metadata/#)

[Copy](https://developer.wordpress.org/reference/functions/wp_get_attachment_metadata/#)




```php
Array
(
   	[width] => 2400
   	[height] => 1559
   	[file] => 2011/12/press_image.jpg
   	[sizes] => Array
   	(
   		[thumbnail] => Array
   		(
   			[file] => press_image-150x150.jpg
   			[width] => 150
   			[height] => 150
   			[mime-type] => image/jpeg
   		)
   		 => Array
   		(
   			[file] => press_image-4-300x194.jpg
   			[width] => 300
   			[height] => 194
   			[mime-type] => image/jpeg
   		)
   		[large] => Array
   		(
   			[file] => press_image-1024x665.jpg
   			[width] => 1024
   			[height] => 665
   			[mime-type] => image/jpeg
   		)
   		[post-thumbnail] => Array
   		(
   			[file] => press_image-624x405.jpg
   			[width] => 624
   			[height] => 405
   			[mime-type] => image/jpeg
   		)
   	)
   	[image_meta] => Array
   	(
   		[aperture] => 5
   		[credit] =>
   		[camera] => Canon EOS-1Ds Mark III
   		 =>
   		[created_timestamp] => 1323190643
   		[copyright] =>
   		[focal_length] => 35
   		[iso] => 800
   		[shutter_speed] => 0.016666666666667
   		[title] =>
   	)
)
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_get_attachment_metadata%2F%3Freplytocom%3D808%23feedback-editor-808)

2. [Skip to note 6 content](https://developer.wordpress.org/reference/functions/wp_get_attachment_metadata/#comment-content-6168)



Note that, since WordPress 6.0, return value includes filesize. This is for can be utilized so that image file size ca be retrieved without having to call php function _filesize_.



See [Media: storing file size as part of metadata](https://make.wordpress.org/core/2022/05/02/media-storing-file-size-as-part-of-metadata/).





[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_get_attachment_metadata%2F%3Freplytocom%3D6168%23feedback-editor-6168)

3. [Skip to note 7 content](https://developer.wordpress.org/reference/functions/wp_get_attachment_metadata/#comment-content-3276)



Example for video format:





`wp-includes/post.php`
[Expand code](https://developer.wordpress.org/reference/functions/wp_get_attachment_metadata/#)

[Copy](https://developer.wordpress.org/reference/functions/wp_get_attachment_metadata/#)




```php
array(10) {
   	[&quot;filesize&quot;] =&gt; int(227431276)
   	[&quot;mime_type&quot;] =&gt; string(9) &quot;video/mp4&quot;
   	[&quot;length&quot;] =&gt; int(918)
   	[&quot;length_formatted&quot;] =&gt; string(5) &quot;15:18&quot;
   	[&quot;width&quot;] =&gt; int(1280)
   	[&quot;height&quot;] =&gt; int(720)
   	[&quot;fileformat&quot;] =&gt; string(3) &quot;mp4&quot;
   	[&quot;dataformat&quot;] =&gt; string(9) &quot;quicktime&quot;
   	[&quot;audio&quot;] =&gt; array(7) {
   		[&quot;dataformat&quot;] =&gt; string(3) &quot;mp4&quot;
   		[&quot;codec&quot;] =&gt; string(19) &quot;ISO/IEC 14496-3 AAC&quot;
   		[&quot;sample_rate&quot;] =&gt; float(44100)
   		[&quot;channels&quot;] =&gt; int(2)
   		[&quot;bits_per_sample&quot;] =&gt; int(16)
   		[&quot;lossless&quot;] =&gt; bool(false)
   		[&quot;channelmode&quot;] =&gt; string(6) &quot;stereo&quot;
   	}
   	[&quot;created_timestamp&quot;]=&gt; int(-2082844800)
}
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_get_attachment_metadata%2F%3Freplytocom%3D3276%23feedback-editor-3276)

4. [Skip to note 8 content](https://developer.wordpress.org/reference/functions/wp_get_attachment_metadata/#comment-content-4162)



NOTE that when calling [wp\_get\_attachment\_metadata()](https://developer.wordpress.org/reference/functions/wp_get_attachment_metadata/) , the ARRAY index returned from ‘file’ is the file path relative to wp-content/uploads.



If you want to get url of domain to link up, you can use snippet below





`wp-includes/post.php`
[Copy](https://developer.wordpress.org/reference/functions/wp_get_attachment_metadata/#)




```php
$upload_dir = wp_upload_dir();
$attachment_metadata = wp_get_attachment_metadata( $attachment_id );
echo var_dump( $upload_dir['url'] . '/' . $attachment_metadata['sizes']['medium_large']['file'] );
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_get_attachment_metadata%2F%3Freplytocom%3D4162%23feedback-editor-4162)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_get_attachment_metadata%2F) before being able to contribute a note or feedback.

Notifications