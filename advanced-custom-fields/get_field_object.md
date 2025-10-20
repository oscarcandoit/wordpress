---
url: https://www.advancedcustomfields.com/resources/get_field_object
scraped_at: 2025-10-20T02:28:36.439Z
---

# get\_field\_object()

Last updated Feb 6, 2024

[Link to heading#](https://www.advancedcustomfields.com/resources/get_field_object/#description)

## Description

Link copied

Returns the settings of a specific field.

Each field contains many settings such as a label, name and type. This function can be used to load these settings as an array along with the field’s value.

[Link to heading#](https://www.advancedcustomfields.com/resources/get_field_object/#parameters)

## Parameters

Link copied

```php
get_field_object($selector, [$post_id = false], [$format_value = true], [$load_value = true], [$escape_html = false]);
```

- `$selector` _(string)_ _(Required)_ The field name or field key.
- `$post_id` _(mixed)_ _(Optional)_ The post ID where the value is saved. Defaults to false, which uses the current post.
- `$format_value` _(bool)_ _(Optional)_ Whether to apply formatting logic. Defaults to true.
- `$load_value` _(bool)_ _(Optional)_ Whether to load the field’s value. Defaults to true.
- `$escape_html` _(bool)_ _(Optional)_ Since 6.2.6 – return an escaped HTML safe version of the field value. Requires $format\_value to be true. Defaults to false.

[Link to heading#](https://www.advancedcustomfields.com/resources/get_field_object/#return)

## Return

Link copied

_(array)_ This function will return an array looking something like the following. Please note that each field contains unique settings.

```php
array(
    'ID'                => 0,
    'key'               => '',
    'label'             => '',
    'name'              => '',
    'prefix'            => '',
    'type'              => 'text',
    'value'             => null,
    'menu_order'        => 0,
    'instructions'      => '',
    'required'          => 0,
    'id'                => '',
    'class'             => '',
    'conditional_logic' => 0,
    'parent'            => 0,
    'wrapper'           => array(
        'width'             => '',
        'class'             => '',
        'id'                => ''
    )
);
```

[Link to heading#](https://www.advancedcustomfields.com/resources/get_field_object/#examples)

## Examples

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/get_field_object/#display-a-fields-label-and-value)

### Display a field’s label and value

Link copied

This example shows how to load a field and display its label and value.

```php
<?php
$field = get_field_object('my_field');
?>
<p><?php echo $field['label']; ?>: <?php echo $field['value']; ?></p>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/get_field_object/#display-a-fields-label-and-value-from-a-specific-post)

### Display a field’s label and value from a specific post

Link copied

This example shows how to load a field and display its label and value from the post with ID = 123.

```php
<?php
$field = get_field_object('my_field', 123);
?>
<p><?php echo $field['label']; ?>: <?php echo $field['value']; ?></p>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/get_field_object/#retrieve-a-field-using-its-key)

### Retrieve a field using its key

Link copied

In some circumstances it may be necessary to load a field by its key, such as when a value has not yet been saved.
This example shows how to load a field using its key.

```php
<?php
$field = get_field_object('field_123456');
?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/get_field_object/#display-field-type-specific-data)

### Display field type specific data

Link copied

Some field types store extra data such as the Select field. This example shows how to loop over a Select field’s choices and display them in a list.

```php
<?php
$field = get_field_object('my_select');
if( $field['choices'] ): ?>
    <ul>
        <?php foreach( $field['choices'] as $value => $label ): ?>
            <li><?php echo $label; ?></li>
        <?php endforeach; ?>
    </ul>
<?php endif; ?>
```

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

[Link to heading#](https://www.advancedcustomfields.com/resources/get_field_object/#related)

## Related

Link copied

- Basic: [get\_field\_objects()](https://www.advancedcustomfields.com/resources/get_field_objects/)
- Functions: [get\_sub\_field\_object()](https://www.advancedcustomfields.com/resources/get_sub_field_object/)
- Basic: [get\_fields()](https://www.advancedcustomfields.com/resources/get_fields/)
- Basic: [get\_field()](https://www.advancedcustomfields.com/resources/get_field/)
- Basic: [the\_field()](https://www.advancedcustomfields.com/resources/the_field/)

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

[Got it](https://www.advancedcustomfields.com/resources/get_field_object/#)