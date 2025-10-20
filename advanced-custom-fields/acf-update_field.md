---
url: https://www.advancedcustomfields.com/resources/acf-update_field
scraped_at: 2025-10-20T02:21:22.399Z
---

# acf/update\_field

Last updated Feb 17, 2022

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-update_field/#description)

## Description

Link copied

Used to modify the `$field` settings array before being saved into the database.

This filter should not be confused with `acf/update_value` which is used similarly to modify field values.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-update_field/#changelog)

## Changelog

Link copied

- Added in version 5.0.0

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-update_field/#parameters)

## Parameters

Link copied

```php
apply_filters( 'acf/update_field', $field );
```

- `$field` _(array)_ The field array containing all settings.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-update_field/#modifers)

## Modifers

Link copied

This filter provides modifiers to target specific fields. The following filter names are available:

- `acf/update_field` Applies to all fields.
- `acf/update_field/type={$type}` Applies to all fields of a specific type.
- `acf/update_field/name={$name}` Applies to all fields of a specific name.
- `acf/update_field/key={$key}` Applies to all fields of a specific key.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-update_field/#example)

## Example

Link copied

This example demonstrates how to modify a field’s settings.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-update_field/#functionsphp)

#### functions.php

Link copied

```php
<?php
function my_acf_update_field( $field ) {

    // Ensure all "company" fields are required.
    if( strpos($field['name'], 'company') !== false ) {
        $field['required'] = true;
    }
    return $field;
}

// Apply to all fields.
add_filter('acf/update_field', 'my_acf_update_field', 10, 1);

// Apply to textarea fields.
// add_filter('acf/update_field/type=textarea', 'my_acf_update_field', 10, 1);

// Apply to fields named "hero_text".
// add_filter('acf/update_field/name=hero_text', 'my_acf_update_field', 10, 1);

// Apply to field with key "field_123abcf".
// add_filter('acf/update_field/key=field_123abcf', 'my_acf_update_field', 10, 1);
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

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-update_field/#related)

## Related

Link copied

- Filters: [acf/update\_value](https://www.advancedcustomfields.com/resources/acf-update_value/)
- Filters: [acf/load\_value](https://www.advancedcustomfields.com/resources/acf-load_value/)
- Filters: [acf/format\_value](https://www.advancedcustomfields.com/resources/acf-format_value/)
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

[Got it](https://www.advancedcustomfields.com/resources/acf-update_field/#)