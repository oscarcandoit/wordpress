---
url: https://developer.wordpress.org/reference/hooks/attachment_fields_to_edit
scraped_at: 2025-10-20T03:17:07.544Z
---

[Skip to content](https://developer.wordpress.org/reference/hooks/attachment_fields_to_edit/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

attachment\_fields\_to\_edit


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Hooks](https://developer.wordpress.org/reference/hooks/)attachment\_fields\_to\_edit

Search

# apply\_filters( ‘attachment\_fields\_to\_edit’, array$form\_fields, WP\_Post$post )

## In this article

Table of Contents

- [Parameters](https://developer.wordpress.org/reference/hooks/attachment_fields_to_edit/#parameters)
- [More Information](https://developer.wordpress.org/reference/hooks/attachment_fields_to_edit/#more-information)
- [Source](https://developer.wordpress.org/reference/hooks/attachment_fields_to_edit/#source)
- [Related](https://developer.wordpress.org/reference/hooks/attachment_fields_to_edit/#related)
- [Changelog](https://developer.wordpress.org/reference/hooks/attachment_fields_to_edit/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/hooks/attachment_fields_to_edit/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/hooks/attachment_fields_to_edit/#wp--skip-link--target)

Filters the attachment fields to edit.

## [Parameters](https://developer.wordpress.org/reference/hooks/attachment_fields_to_edit/\#parameters)

`$form_fields` array

An array of attachment form fields.

`$post` [WP\_Post](https://developer.wordpress.org/reference/classes/wp_post/)

The [WP\_Post](https://developer.wordpress.org/reference/classes/wp_post/) attachment object.

## [More Information](https://developer.wordpress.org/reference/hooks/attachment_fields_to_edit/\#more-information)

- WordPress does not pass standard fields through this filter, though this can still be used for adding attachment form fields.
- Note that the filter function **must** return an array of attachment form fields after it is finished processing; otherwise, no fields will be displayed when editing an attachment and other plugins also filtering the `$form_fields` array may generate errors.

## [Source](https://developer.wordpress.org/reference/hooks/attachment_fields_to_edit/\#source)

`wp-admin/includes/media.php`
[Copy](https://developer.wordpress.org/reference/hooks/attachment_fields_to_edit/#)

```php
$form_fields = apply_filters( 'attachment_fields_to_edit', $form_fields, $post );

```

[View all references](https://developer.wordpress.org/reference/files/wp-admin/includes/media.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-admin/includes/media.php#L1509) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-admin/includes/media.php#L1509-L1509)

## [Related](https://developer.wordpress.org/reference/hooks/attachment_fields_to_edit/\#related)

| Used by | Description |
| --- | --- |
| [get\_attachment\_fields\_to\_edit()](https://developer.wordpress.org/reference/functions/get_attachment_fields_to_edit/) `wp-admin/includes/media.php` | Retrieves the attachment fields to edit form fields. |
| [get\_compat\_media\_markup()](https://developer.wordpress.org/reference/functions/get_compat_media_markup/) `wp-admin/includes/media.php` |  |

## [Changelog](https://developer.wordpress.org/reference/hooks/attachment_fields_to_edit/\#changelog)

| Version | Description |
| --- | --- |
| [2.5.0](https://developer.wordpress.org/reference/since/2.5.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/hooks/attachment_fields_to_edit/\#user-contributed-notes)

1. [Skip to note 5 content](https://developer.wordpress.org/reference/hooks/attachment_fields_to_edit/#comment-content-2713)



This is the way to add custom fields to attachments:





`wp-admin/includes/media.php`
[Expand code](https://developer.wordpress.org/reference/hooks/attachment_fields_to_edit/#)

[Copy](https://developer.wordpress.org/reference/hooks/attachment_fields_to_edit/#)




```php
// Add custom text/textarea attachment field
function add_custom_text_field_to_attachment_fields_to_edit( $form_fields, $post ) {
       $text_field = get_post_meta($post->ID, 'text_field', true);
       $form_fields['text_field'] = array(
           'label' => 'Custom text field',
           'input' => 'text', // you may alos use 'textarea' field
           'value' => $text_field,
           'helps' => 'This is help text'
       );
       return $form_fields;
}
add_filter('attachment_fields_to_edit', 'add_custom_text_field_to_attachment_fields_to_edit', null, 2);

// Save custom text/textarea attachment field
function save_custom_text_attachment_field($post, $attachment) {
       if( isset($attachment['text_field']) ){
           update_post_meta($post['ID'], 'text_field', sanitize_text_field( $attachment['text_field'] ) );
       }else{
            delete_post_meta($post['ID'], 'text_field' );
       }
       return $post;
}
add_filter('attachment_fields_to_save', 'save_custom_text_attachment_field', null, 2);


// Add custom checkbox attachment field
function add_custom_checkbox_field_to_attachment_fields_to_edit( $form_fields, $post ) {
       $checkbox_field = (bool) get_post_meta($post->ID, 'checkbox_field', true);
       $form_fields['checkbox_field'] = array(
           'label' => 'Checkbox',
           'input' => 'html',
           'html' => '<input type="checkbox" id="attachments-'.$post->ID.'-checkbox_field" name="attachments['.$post->ID.'][checkbox_field]" value="1"'.($checkbox_field ? ' checked="checked"' : '').' /> ',
           'value' => $checkbox_field,
           'helps' => ''
       );
   	return $form_fields;
}
add_filter('attachment_fields_to_edit', 'add_custom_checkbox_field_to_attachment_fields_to_edit', null, 2);

// Save custom checkbox attachment field
function save_custom_checkbox_attachment_field($post, $attachment) {
       if( isset($attachment['checkbox_field']) ){
           update_post_meta($post['ID'], 'checkbox_field', sanitize_text_field( $attachment['checkbox_field'] ) );
       }else{
            delete_post_meta($post['ID'], 'checkbox_field' );
       }
       return $post;
}
add_filter('attachment_fields_to_save', 'save_custom_checkbox_attachment_field', null, 2);
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Fattachment_fields_to_edit%2F%3Freplytocom%3D2713%23feedback-editor-2713)

2. [Skip to note 6 content](https://developer.wordpress.org/reference/hooks/attachment_fields_to_edit/#comment-content-4744)



Example migrated from Codex:



The following example adds a “Location” field for all attachments. This example also uses the “ [edit\_attachment](https://developer.wordpress.org/reference/hooks/edit_attachment/)” action hook to save the submitted custom attachment form fields value to the post meta of the post in which the attachment belongs.





`wp-admin/includes/media.php`
[Expand code](https://developer.wordpress.org/reference/hooks/attachment_fields_to_edit/#)

[Copy](https://developer.wordpress.org/reference/hooks/attachment_fields_to_edit/#)




```php
add_filter( 'attachment_fields_to_edit', 'my_add_attachment_location_field', 10, 2 );

function my_add_attachment_location_field( $form_fields, $post ) {
       $field_value = get_post_meta( $post->ID, 'location', true );
       $form_fields['location'] = array(
           'value' => $field_value ? $field_value : '',
           'label' => __( 'Location' ),
           'helps' => __( 'Set a location for this attachment' )
       );
       return $form_fields;
}

add_action( 'edit_attachment', 'my_save_attachment_location' );

function my_save_attachment_location( $attachment_id ) {
       if ( isset( $_REQUEST['attachments'][$attachment_id]['location'] ) ) {
           $location = $_REQUEST['attachments'][$attachment_id]['location'];
           update_post_meta( $attachment_id, 'location', $location );
       }
}
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Fattachment_fields_to_edit%2F%3Freplytocom%3D4744%23feedback-editor-4744)

3. [Skip to note 7 content](https://developer.wordpress.org/reference/hooks/attachment_fields_to_edit/#comment-content-4856)



If you add a custom field to attachments as described above, the field will be displayed and saved as well. **But:** There is no complete Ajax feedback to the user: the save icon appears in the top-right corner. “attachment-details” gets the class “save-waiting”, then again “save-ready”. The class “save-complete” is omitted. For the standard fields again this status is displayed. The text “Saved.” appears. This should be displayed for custom fields, too!





[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Fattachment_fields_to_edit%2F%3Freplytocom%3D4856%23feedback-editor-4856)

4. [Skip to note 8 content](https://developer.wordpress.org/reference/hooks/attachment_fields_to_edit/#comment-content-6980)



There are “text” and “textarea” field types that can be used by default. To have another field type, you can simply use the “html” type. Here is an example of how to add a button:





`wp-admin/includes/media.php`
[Expand code](https://developer.wordpress.org/reference/hooks/attachment_fields_to_edit/#)

[Copy](https://developer.wordpress.org/reference/hooks/attachment_fields_to_edit/#)




```php
// Add the custom meta field to the media file settings
function wpdocs_button_attachment_ui( $form_fields ) {
       // Add your custom meta field
       $form_fields['custom_meta_field'] = array(
           'label' => __( 'My Button' ),
           'input' => 'html',
           'html'  => 'My Button Name',
           'helps' => __( 'Some help here if you need it.' ),
       );

       return $form_fields;
}

add_filter( 'attachment_fields_to_edit', 'wpdocs_button_attachment_ui' );
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Fattachment_fields_to_edit%2F%3Freplytocom%3D6980%23feedback-editor-6980)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Fattachment_fields_to_edit%2F) before being able to contribute a note or feedback.

Notifications