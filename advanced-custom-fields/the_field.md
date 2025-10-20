---
url: https://www.advancedcustomfields.com/resources/the_field
scraped_at: 2025-10-20T02:22:46.994Z
---

# the\_field()

Last updated Feb 17, 2022

[Link to heading#](https://www.advancedcustomfields.com/resources/the_field/#description)

## Description

Link copied

Displays the value of a specific field.

Intuitive and powerful, this function can be used to output the value of any field from any location. Please note this function is the same as `echo get_field()`.

[Link to heading#](https://www.advancedcustomfields.com/resources/the_field/#parameters)

## Parameters

Link copied

```php
the_field($selector, [$post_id], [$format_value]);
```

- `$selector` _(string)_ _(Required)_ The field name or field key.
- `$post_id` _(mixed)_ _(Optional)_ The post ID where the value is saved. Defaults to the current post.
- `$format_value` _(bool)_ _(Optional)_ Whether to apply formatting logic. Defaults to true.

[Link to heading#](https://www.advancedcustomfields.com/resources/the_field/#examples)

## Examples

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/the_field/#display-a-value-from-the-current-post)

### Display a value from the current post

Link copied

This example shows how to display the value of field "text\_field" from the current post.

```php
<h2><?php the_field('text_field'); ?></h2>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/the_field/#display-a-value-from-a-specific-post)

### Display a value from a specific post

Link copied

This example shows how to display the value of field "text\_field" from the post with ID = 123.

```php
<h2><?php the_field('text_field', 123); ?></h2>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/the_field/#check-if-value-exists)

### Check if value exists

Link copied

This example shows how to check if a value exists before displaying it.

```php
<?php if( get_field('text_field') ): ?>
    <h2><?php the_field('text_field'); ?></h2>
<?php endif; ?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/the_field/#get-a-value-from-different-objects)

### Get a value from different objects

Link copied

This example shows a variety of valid **$post\_id** values that specify where the value is saved.

```php
$post_id = false;           // current post
$post_id = 123;             // post ID = 123
$post_id = "user_123";      // user ID = 123
$post_id = "term_123";      // term ID = 123
$post_id = "category_123";  // same as above
$post_id = "option";        // options page
$post_id = "options";       // same as above

the_field( 'my_field', $post_id );
```

[Link to heading#](https://www.advancedcustomfields.com/resources/the_field/#notes)

## Notes

Link copied

Prior to ACF 5.11, `the_field()` could be used to display the values of options or meta for items not associated with ACF fields. This had security implications as site options could be exposed. `the_field()` also could display values of fields that are no longer registered with ACF.

This was updated in ACF 5.11, see the [Updates to ACF Field Functions in 5.11](https://www.advancedcustomfields.com/resources/acf-field-functions/) resource for more info.

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

[Link to heading#](https://www.advancedcustomfields.com/resources/the_field/#related)

## Related

Link copied

- Basic: [get\_field()](https://www.advancedcustomfields.com/resources/get_field/)
- Basic: [get\_field\_object()](https://www.advancedcustomfields.com/resources/get_field_object/)
- Basic: [get\_fields()](https://www.advancedcustomfields.com/resources/get_fields/)
- Functions: [the\_sub\_field()](https://www.advancedcustomfields.com/resources/the_sub_field/)
- Basic: [get\_field\_objects()](https://www.advancedcustomfields.com/resources/get_field_objects/)

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

[Got it](https://www.advancedcustomfields.com/resources/the_field/#)