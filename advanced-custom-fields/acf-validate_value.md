---
url: https://www.advancedcustomfields.com/resources/acf-validate_value
scraped_at: 2025-10-20T02:21:54.045Z
---

# acf/validate\_value

Last updated Feb 17, 2022

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-validate_value/#description)

## Description

Link copied

Used to perform custom validation on the field’s `$value` before it is saved into the database.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-validate_value/#changelog)

## Changelog

Link copied

- Added in version 5.0.0

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-validate_value/#parameters)

## Parameters

Link copied

```php
apply_filters( 'acf/validate_value', $valid, $value, $field, $input_name );
```

- `$valid` _(mixed)_ Whether or not the value is valid (boolean) or a custom error message (string).
- `$value` _(mixed)_ The field value.
- `$field` _(array)_ The field array containing all settings.
- `$input_name` _(string)_ The field DOM element name attribute.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-validate_value/#modifers)

## Modifers

Link copied

This filter provides modifiers to target specific fields. The following filter names are available:

- `acf/validate_value` Applies to all fields.
- `acf/validate_value/type={$type}` Applies to all fields of a specific type.
- `acf/validate_value/name={$name}` Applies to all fields of a specific name.
- `acf/validate_value/key={$key}` Applies to all fields of a specific key.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-validate_value/#example)

## Example

Link copied

This example demonstrates how to validate a field’s value and return a custom error message.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-validate_value/#functionsphp)

#### functions.php

Link copied

```php
<?php
function my_acf_validate_value( $valid, $value, $field, $input_name ) {

    // Bail early if value is already invalid.
    if( $valid !== true ) {
        return $valid;
    }

    // Prevent value from saving if it contains the companies old name.
    if( is_string($value) && strpos($value, 'Old Company Name') !== false ) {
        return __( 'Please remove mention of "Old Company Name".' );
    }
    return $valid;
}

// Apply to all fields.
add_filter('acf/validate_value', 'my_acf_validate_value', 10, 4);

// Apply to textarea fields.
// add_filter('acf/validate_value/type=textarea', 'my_acf_validate_value', 10, 4);

// Apply to fields named "hero_text".
// add_filter('acf/validate_value/name=hero_text', 'my_acf_validate_value', 10, 4);

// Apply to field with key "field_123abcf".
// add_filter('acf/validate_value/key=field_123abcf', 'my_acf_validate_value', 10, 4);
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

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-validate_value/#related)

## Related

Link copied

- Filters: [acf/update\_value](https://www.advancedcustomfields.com/resources/acf-update_value/)
- Filters: [acf/load\_value](https://www.advancedcustomfields.com/resources/acf-load_value/)
- Filters: [acf/update\_field](https://www.advancedcustomfields.com/resources/acf-update_field/)
- Filters: [acf/format\_value](https://www.advancedcustomfields.com/resources/acf-format_value/)
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

[Got it](https://www.advancedcustomfields.com/resources/acf-validate_value/#)