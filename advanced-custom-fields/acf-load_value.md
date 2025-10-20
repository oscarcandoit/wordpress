---
url: https://www.advancedcustomfields.com/resources/acf-load_value
scraped_at: 2025-10-20T02:19:43.811Z
---

# acf/load\_value

Last updated Feb 17, 2022

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-load_value/#description)

## Description

Link copied

Filters the field `$value` after being loaded.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-load_value/#changelog)

## Changelog

Link copied

- Added in version 4.0.0

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-load_value/#parameters)

## Parameters

Link copied

```php
apply_filters( 'acf/load_value', $value, $post_id, $field );
```

- `$value` _(mixed)_ The field value.
- `$post_id` _(int\|string)_ The post ID where the value is saved.
- `$field` _(array)_ The field array containing all settings.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-load_value/#modifers)

## Modifers

Link copied

This filter provides modifiers to target specific fields. The following filter names are available:

- `acf/load_value` Applies to all fields.
- `acf/load_value/type={$type}` Applies to all fields of a specific type.
- `acf/load_value/name={$name}` Applies to all fields of a specific name.
- `acf/load_value/key={$key}` Applies to all fields of a specific key.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-load_value/#example)

## Example

Link copied

This example demonstrates how to modify a field’s value.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-load_value/#functionsphp)

#### functions.php

Link copied

```php
<?php
function my_acf_load_value( $value, $post_id, $field ) {
    if( is_string($value) ) {
        $value = str_replace( 'Old Company Name', 'New Company Name',  $value );
    }
    return $value;
}

// Apply to all fields.
add_filter('acf/load_value', 'my_acf_load_value', 10, 3);

// Apply to textarea fields.
// add_filter('acf/load_value/type=textarea', 'my_acf_load_value', 10, 3);

// Apply to fields named "hero_text".
// add_filter('acf/load_value/name=hero_text', 'my_acf_load_value', 10, 3);

// Apply to field with key "field_123abcf".
// add_filter('acf/load_value/key=field_123abcf', 'my_acf_load_value', 10, 3);
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

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-load_value/#related)

## Related

Link copied

- Filters: [acf/format\_value](https://www.advancedcustomfields.com/resources/acf-format_value/)
- Filters: [acf/update\_value](https://www.advancedcustomfields.com/resources/acf-update_value/)
- Filters: [acf/update\_field](https://www.advancedcustomfields.com/resources/acf-update_field/)
- Filters: [acf/load\_field](https://www.advancedcustomfields.com/resources/acf-load_field/)
- Filters: [acf/validate\_value](https://www.advancedcustomfields.com/resources/acf-validate_value/)

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

[Got it](https://www.advancedcustomfields.com/resources/acf-load_value/#)