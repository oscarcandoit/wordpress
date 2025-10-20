---
url: https://developer.wordpress.org/reference/functions/wp_attachment_is_image
scraped_at: 2025-10-20T03:18:03.146Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/wp_attachment_is_image/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp\_attachment\_is\_image()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)wp\_attachment\_is\_image()

Search

# wp\_attachment\_is\_image( int\|WP\_Post$post = null ): bool

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/wp_attachment_is_image/#description)
- [Parameters](https://developer.wordpress.org/reference/functions/wp_attachment_is_image/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/wp_attachment_is_image/#return)
- [Source](https://developer.wordpress.org/reference/functions/wp_attachment_is_image/#source)
- [Related](https://developer.wordpress.org/reference/functions/wp_attachment_is_image/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/wp_attachment_is_image/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/functions/wp_attachment_is_image/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/functions/wp_attachment_is_image/#wp--skip-link--target)

Determines whether an attachment is an image.

## [Description](https://developer.wordpress.org/reference/functions/wp_attachment_is_image/\#description)

For more information on this and similar theme functions, check out the [Conditional Tags](https://developer.wordpress.org/themes/basics/conditional-tags/) article in the Theme Developer Handbook.

## [Parameters](https://developer.wordpress.org/reference/functions/wp_attachment_is_image/\#parameters)

`$post` int\|[WP\_Post](https://developer.wordpress.org/reference/classes/wp_post/)optional

Attachment ID or object. Default is global $post.

Default: `null`

## [Return](https://developer.wordpress.org/reference/functions/wp_attachment_is_image/\#return)

bool Whether the attachment is an image.

## [Source](https://developer.wordpress.org/reference/functions/wp_attachment_is_image/\#source)

`wp-includes/post.php`
[Copy](https://developer.wordpress.org/reference/functions/wp_attachment_is_image/#)

```php
function wp_attachment_is_image( $post = null ) {
	return wp_attachment_is( 'image', $post );
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/post.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/post.php#L7082) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/post.php#L7082-L7084)

## [Related](https://developer.wordpress.org/reference/functions/wp_attachment_is_image/\#related)

| Uses | Description |
| --- | --- |
| [wp\_attachment\_is()](https://developer.wordpress.org/reference/functions/wp_attachment_is/) `wp-includes/post.php` | Verifies an attachment is of a given type. |

| Used by | Description |
| --- | --- |
| [wp\_get\_original\_image\_path()](https://developer.wordpress.org/reference/functions/wp_get_original_image_path/) `wp-includes/post.php` | Retrieves the path to an uploaded image file. |
| [wp\_get\_original\_image\_url()](https://developer.wordpress.org/reference/functions/wp_get_original_image_url/) `wp-includes/post.php` | Retrieves the URL to an original attachment image. |
| [wp\_get\_missing\_image\_subsizes()](https://developer.wordpress.org/reference/functions/wp_get_missing_image_subsizes/) `wp-admin/includes/image.php` | Compare the existing image sub-sizes (as saved in the attachment meta) to the currently registered image sub-sizes, and return the difference. |
| [wp\_ajax\_media\_create\_image\_subsizes()](https://developer.wordpress.org/reference/functions/wp_ajax_media_create_image_subsizes/) `wp-admin/includes/ajax-actions.php` | Handles creating missing image sub-sizes for just uploaded images via AJAX. |
| [WP\_REST\_Attachments\_Controller::prepare\_item\_for\_response()](https://developer.wordpress.org/reference/classes/wp_rest_attachments_controller/prepare_item_for_response/) `wp-includes/rest-api/endpoints/class-wp-rest-attachments-controller.php` | Prepares a single attachment output for response. |
| [has\_custom\_logo()](https://developer.wordpress.org/reference/functions/has_custom_logo/) `wp-includes/general-template.php` | Determines whether the site has a custom logo. |
| [get\_oembed\_response\_data\_rich()](https://developer.wordpress.org/reference/functions/get_oembed_response_data_rich/) `wp-includes/embed.php` | Filters the oEmbed response data to return an iframe embed code. |
| [edit\_form\_image\_editor()](https://developer.wordpress.org/reference/functions/edit_form_image_editor/) `wp-admin/includes/media.php` | Displays the image and editor in the post editor |
| [get\_media\_item()](https://developer.wordpress.org/reference/functions/get_media_item/) `wp-admin/includes/media.php` | Retrieves HTML form for modifying the image attachment. |
| [get\_attachment\_icon\_src()](https://developer.wordpress.org/reference/functions/get_attachment_icon_src/) `wp-includes/deprecated.php` | Retrieve icon URL and Path. |

[Show 5 more](https://developer.wordpress.org/reference/functions/wp_attachment_is_image/#) [Show less](https://developer.wordpress.org/reference/functions/wp_attachment_is_image/#)

## [Changelog](https://developer.wordpress.org/reference/functions/wp_attachment_is_image/\#changelog)

| Version | Description |
| --- | --- |
| [4.2.0](https://developer.wordpress.org/reference/since/4.2.0/) | Modified into wrapper for [wp\_attachment\_is()](https://developer.wordpress.org/reference/functions/wp_attachment_is/) and allowed [WP\_Post](https://developer.wordpress.org/reference/classes/wp_post/) object to be passed. |
| [2.1.0](https://developer.wordpress.org/reference/since/2.1.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/functions/wp_attachment_is_image/\#user-contributed-notes)

1. [Skip to note 2 content](https://developer.wordpress.org/reference/functions/wp_attachment_is_image/#comment-content-1269)



**Basic Example**



To check if post ID 37’s attachment is an image:





`wp-includes/post.php`
[Copy](https://developer.wordpress.org/reference/functions/wp_attachment_is_image/#)




```php
$id = 37;
if ( wp_attachment_is_image( $id ) ) {
   	printf( 'Post %d is an image!', $id );
} else {
   	printf( 'Post %d is not an image.', $id );
}
```





_Edited with a contribution from @keraweb_





[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_attachment_is_image%2F%3Freplytocom%3D1269%23feedback-editor-1269)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_attachment_is_image%2F) before being able to contribute a note or feedback.

Notifications