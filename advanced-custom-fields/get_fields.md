---
url: https://www.advancedcustomfields.com/resources/get_fields
scraped_at: 2025-10-20T02:28:31.642Z
---

# get\_fields()

Last updated Feb 6, 2024

[Link to heading#](https://www.advancedcustomfields.com/resources/get_fields/#description)

## Description

Link copied

Returns an array of field values (name => value) for a specific post.

[Link to heading#](https://www.advancedcustomfields.com/resources/get_fields/#parameters)

## Parameters

Link copied

```php
get_fields([$post_id = false], [$format_value = true], [$escape_html = false]);
```

- `$post_id` _(mixed)_ _(Optional)_ The post ID where the value is saved. Defaults to false, which uses the current post.
- `$format_value` _(bool)_ _(Optional)_ Whether to apply formatting logic. Defaults to true.
- `$escape_html` _(bool)_ _(Optional)_ Since 6.2.6 – return an escaped HTML safe version of the field value. Requires $format\_value to be true. Defaults to false.

[Link to heading#](https://www.advancedcustomfields.com/resources/get_fields/#return)

## Return

Link copied

_(array\|false)_ Array of values or false if no fields are found.

[Link to heading#](https://www.advancedcustomfields.com/resources/get_fields/#examples)

## Examples

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/get_fields/#get-values-from-the-current-post)

### Get values from the current post

Link copied

This example shows how to display all fields (name and value) in a list from the current post.

```php
<?php

$fields = get_fields();

if( $fields ): ?>
    <ul>
        <?php foreach( $fields as $name => $value ): ?>
            <li><b><?php echo $name; ?></b> <?php echo $value; ?></li>
        <?php endforeach; ?>
    </ul>
<?php endif; ?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/get_fields/#get-values-from-a-specific-post)

### Get values from a specific post

Link copied

This example shows how to load all fields (name and value) from different data objects.

```php
// Get values from the current post.
$fields = get_fields();

// Get values from post ID = 1.
$post_fields = get_fields( 1 );

// Get values from user ID = 2.
$user_fields = get_fields( 'user_2' );

// Get values from category ID = 3.
$term_fields = get_fields( 'term_3' );

// ... or using taxonomy name.
$term_fields = get_fields( 'category_3' );

// Get values from comment ID = 4.
$comment_fields = get_fields( 'comment_4' );

// Get values from ACF Options page.
$option_fields = get_fields( 'options' );

// ... or using 'option'.
$option_fields = get_fields( 'option' );
```

[Link to heading#](https://www.advancedcustomfields.com/resources/get_fields/#get-values-without-formatting)

### Get values without formatting

Link copied

This example shows how to load all fields (name and value) without any formatting applied.

Formatting refers to how the values are modified after being loaded from the database. For example, an image field value is saved into the database as just the attachment ID but can be returned as a URL depending on the field’s settings.

In some cases it may be useful to ensure only the raw value is returned regardless of field settings. To do this, we use the `$format_value` parameter.

```php
$fields = get_fields( 123, false );
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

[Link to heading#](https://www.advancedcustomfields.com/resources/get_fields/#related)

## Related

Link copied

- Basic: [get\_field\_object()](https://www.advancedcustomfields.com/resources/get_field_object/)
- Basic: [get\_field\_objects()](https://www.advancedcustomfields.com/resources/get_field_objects/)
- Basic: [get\_field()](https://www.advancedcustomfields.com/resources/get_field/)
- Functions: [get\_sub\_field\_object()](https://www.advancedcustomfields.com/resources/get_sub_field_object/)
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

[Got it](https://www.advancedcustomfields.com/resources/get_fields/#)