---
url: https://www.advancedcustomfields.com/resources/acf-load_field
scraped_at: 2025-10-20T02:19:39.305Z
---

# acf/load\_field

Last updated Feb 17, 2022

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-load_field/#description)

## Description

Link copied

Filters the `$field` settings array after being loaded.

A field is loaded anytime it is displayed, or its value is loaded. This filter applies to both fields saved in the database and also those registered locally via PHP or [JSON](https://www.advancedcustomfields.com/resources/local-json/).

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-load_field/#changelog)

## Changelog

Link copied

- Added in version 4.0.0

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-load_field/#parameters)

## Parameters

Link copied

```php
apply_filters( 'acf/load_field', $field );
```

- `$field` _(array)_ The field array containing all settings.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-load_field/#modifers)

## Modifers

Link copied

This filter provides modifiers to target specific fields. The following filter names are available:

- `acf/load_field` Applies to all fields.
- `acf/load_field/type={$type}` Applies to all fields of a specific type.
- `acf/load_field/name={$name}` Applies to all fields of a specific name.
- `acf/load_field/key={$key}` Applies to all fields of a specific key.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-load_field/#example)

## Example

Link copied

This example demonstrates how to modify a specific field’s settings.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-load_field/#functionsphp)

#### functions.php

Link copied

```php
<?php
function my_acf_load_field( $field ) {
    $field['required'] = true;
    $field['choices'] = array(
        'custom'    => 'My Custom Choice',
        'custom_2'  => 'My Custom Choice 2'
    );
    return $field;
}

// Apply to all fields.
// add_filter('acf/load_field', 'my_acf_load_field');

// Apply to select fields.
// add_filter('acf/load_field/type=select', 'my_acf_load_field');

// Apply to fields named "custom_select".
add_filter('acf/load_field/name=custom_select', 'my_acf_load_field');

// Apply to field with key "field_123abcf".
// add_filter('acf/load_field/key=field_123abcf', 'my_acf_load_field');
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

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-load_field/#related)

## Related

Link copied

- Filters: [acf/load\_value](https://www.advancedcustomfields.com/resources/acf-load_value/)
- Filters: [acf/prepare\_field](https://www.advancedcustomfields.com/resources/acf-prepare_field/)
- Filters: [acf/update\_field](https://www.advancedcustomfields.com/resources/acf-update_field/)
- Filters: [acf/format\_value](https://www.advancedcustomfields.com/resources/acf-format_value/)
- Filters: [acf/update\_value](https://www.advancedcustomfields.com/resources/acf-update_value/)

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

[Got it](https://www.advancedcustomfields.com/resources/acf-load_field/#)