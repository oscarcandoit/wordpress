---
url: https://www.advancedcustomfields.com/resources/acf-format_value
scraped_at: 2025-10-20T02:19:53.169Z
---

# acf/format\_value

Last updated Feb 17, 2022

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-format_value/#description)

## Description

Link copied

Filters the field `$value` after being loaded by a template function such as `get_field()`.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-format_value/#changelog)

## Changelog

Link copied

- Added in version 5.0
- Previously named "acf/format\_value\_for\_api" in version 4.0

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-format_value/#parameters)

## Parameters

Link copied

```php
apply_filters( 'acf/format_value', $value, $post_id, $field );
```

- `$value` _(mixed)_ The field value.
- `$post_id` _(int\|string)_ The post ID where the value is saved.
- `$field` _(array)_ The field array containing all settings.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-format_value/#modifers)

## Modifers

Link copied

This filter provides modifiers to target specific fields. The following filter names are available:

- `acf/format_value` Applies to all fields.
- `acf/format_value/type={$type}` Applies to all fields of a specific type.
- `acf/format_value/name={$name}` Applies to all fields of a specific name.
- `acf/format_value/key={$key}` Applies to all fields of a specific key.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-format_value/#example)

## Example

Link copied

This example demonstrates how to modify a field’s value when loaded by a template function.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-format_value/#functionsphp)

#### functions.php

Link copied

```php
<?php
function my_acf_format_value( $value, $post_id, $field ) {

    // Render shortcodes in all textarea values.
    return do_shortcode( $value );
}

// Apply to all fields.
// add_filter('acf/format_value', 'my_acf_format_value', 10, 3);

// Apply to textarea fields.
add_filter('acf/format_value/type=textarea', 'my_acf_format_value', 10, 3);

// Apply to fields named "hero_text".
// add_filter('acf/format_value/name=hero_text', 'my_acf_format_value', 10, 3);

// Apply to field with key "field_123abcf".
// add_filter('acf/format_value/key=field_123abcf', 'my_acf_format_value', 10, 3);
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

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-format_value/#related)

## Related

Link copied

- Filters: [acf/load\_value](https://www.advancedcustomfields.com/resources/acf-load_value/)
- Filters: [acf/update\_value](https://www.advancedcustomfields.com/resources/acf-update_value/)
- Filters: [acf/update\_field](https://www.advancedcustomfields.com/resources/acf-update_field/)
- Filters: [acf/validate\_value](https://www.advancedcustomfields.com/resources/acf-validate_value/)
- Filters: [acf/load\_field](https://www.advancedcustomfields.com/resources/acf-load_field/)

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

[Got it](https://www.advancedcustomfields.com/resources/acf-format_value/#)