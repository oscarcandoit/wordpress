---
url: https://www.advancedcustomfields.com/resources/update_field
scraped_at: 2025-10-20T02:28:54.215Z
---

# update\_field()

Last updated Feb 7, 2024

[Link to heading#](https://www.advancedcustomfields.com/resources/update_field/#description)

## Description

Link copied

Updates the value of a specific field.

[Link to heading#](https://www.advancedcustomfields.com/resources/update_field/#parameters)

## Parameters

Link copied

```php
update_field($selector, $value, [$post_id]);
```

- `$selector` _(string)_ _(Required)_ The field name or field key.
- `$value` _(mixed)_ _(Required)_ The new value.
- `$post_id` _(mixed)_ _(Optional)_ The post ID where the value is saved. Defaults to the current post.

[Link to heading#](https://www.advancedcustomfields.com/resources/update_field/#return)

## Return

Link copied

_(int\|bool)_ Meta ID if the field value didn’t exist and the field is not being saved as an option. Otherwise true on successful update, false on failure.

[Link to heading#](https://www.advancedcustomfields.com/resources/update_field/#examples)

## Examples

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/update_field/#updating-via-field-name)

### Updating via field name

Link copied

This example shows how to update the value of a field called ‘views’ on the current post being viewed.

```php
// Get the current value.
$count = (int) get_field('views');

// Increase it.
$count++;

// Update with new value.
update_field('views', $count);
```

[Link to heading#](https://www.advancedcustomfields.com/resources/update_field/#updating-via-field-key)

### Updating via field key

Link copied

This example shows how to achieve the same result as above using the field’s key instead of its name. The field’s key should be used when saving a **new** value to a post (when no value exists). This helps ACF create the correct ‘reference’ between the value and the field’s settings.

Each value saved in the database is given a ‘reference’ of the field’s key. This allows ACF to connect a value with its field. ACF does this so it can format values when loaded based of the field type and settings. For example, the image field contains a setting to return an array of image data instead of the attachment ID.

```php
// Get the current value.
$count = (int) get_field('field_123456');

// Increase it.
$count++;

// Update with new value.
update_field('field_123456', $count);
```

[Link to heading#](https://www.advancedcustomfields.com/resources/update_field/#update-a-value-from-different-objects)

### Update a value from different objects

Link copied

This example shows a variety of **$post\_id** values to update a value from a post, user, term and option.

```php
$post_id = false; // current post
$post_id = 1; // post ID = 1
$post_id = "user_2"; // user ID = 2
$post_id = "category_3"; // category term ID = 3
$post_id = "event_4"; // event (custom taxonomy) term ID = 4
$post_id = "option"; // options page
$post_id = "options"; // same as above

update_field( 'my_field', 'my_value', $post_id );
```

[Link to heading#](https://www.advancedcustomfields.com/resources/update_field/#saving-values-to-a-new-post)

### Saving values to a new post

Link copied

This example will demonstrate how to create a new post, and save multiple field values to it.

```php
// Create new post.
$post_data = array(
    'post_title'    => 'My post',
    'post_type'     => 'post',
    'post_status'   => 'publish'
);
$post_id = wp_insert_post( $post_data );

// Save a basic text value.
$field_key = "field_123456";
$value = "some new string";
update_field( $field_key, $value, $post_id );

// Save a checkbox or select value.
$field_key = "field_1234567";
$value = array("red", "blue", "yellow");
update_field( $field_key, $value, $post_id );

// Save a repeater field value.
$field_key = "field_12345678";
$value = array(
    array(
        "sub_field_1"   => "Foo",
        "sub_field_2"   => "Bar"
    )
);
update_field( $field_key, $value, $post_id );

// Save a flexible content field value.
$field_key = "field_123456789";
$value = array(
    array( "sub_field_1" => "Foo1", "sub_field_2" => "Bar1", "acf_fc_layout" => "layout_1_name" ),
    array( "sub_field_x" => "Foo2", "sub_field_y" => "Bar2", "acf_fc_layout" => "layout_2_name" )
);
update_field( $field_key, $value, $post_id );

// Save a value for a clone field set to “Prefix Field Names”.
update_field( ‘clone_field_name_original_field_name’, $post_id, $value );
```

[Link to heading#](https://www.advancedcustomfields.com/resources/update_field/#notes)

## Notes

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/update_field/#no-change-detected)

### No change detected

Link copied

If the value passed to this function is the same as the value that is already in the database, this function returns false.

##### Supercharge Your Website With Premium Features Using ACF PRO

Speed up your workflow and unlock features to better develop websites using ACF Blocks and Options Pages, with the Flexible Content, Repeater,
Clone, Gallery Fields & More.


[Explore Features](https://www.advancedcustomfields.com/pro/) [View Pricing](https://www.advancedcustomfields.com/pro/#pricing-table/)

PRO Features

ACF Blocks

Options Pages

PRO Fields

Repeater

Flexible Content

Gallery

Clone

[Link to heading#](https://www.advancedcustomfields.com/resources/update_field/#related)

## Related

Link copied

- Filters: [acf/update\_value](https://www.advancedcustomfields.com/resources/acf-update_value/)
- Basic: [get\_field()](https://www.advancedcustomfields.com/resources/get_field/)
- Functions: [update\_row()](https://www.advancedcustomfields.com/resources/update_row/)
- Functions: [delete\_field()](https://www.advancedcustomfields.com/resources/delete_field/)
- Functions: [add\_row()](https://www.advancedcustomfields.com/resources/add_row/)

Sign up for the latest Advanced Custom Fields news, updates, and developer tutorials

First name\*

Last name\*

Email\*

Anonymous ID (Segment)

GA Client ID

GA Session ID

FBC

FBP

GCLID

FBCLID

MSCLKID

LI FAT ID

Everflow Transaction ID

Kameleoon Visitor Code

UETVID

UTM Medium

UTM Content

UTM Campaign

UETSID

UTM Term

UTM Source

Logged In

MF User

Last Marketing (Form) Activity

We use cookies to offer you a better browsing experience, analyze site traffic and personalize content. Read about how we use cookies and how you can control them in our [Privacy Policy](https://wpengine.com/legal/privacy/). If you continue to use this site, you consent to our use of cookies.

[Got it](https://www.advancedcustomfields.com/resources/update_field/#)