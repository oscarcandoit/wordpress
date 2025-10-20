---
url: https://www.advancedcustomfields.com/resources/acf-prepare_field
scraped_at: 2025-10-20T02:20:01.276Z
---

# acf/prepare\_field

Last updated Feb 17, 2022

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-prepare_field/#description)

## Description

Link copied

Used to modify the `$field` settings or to prevent the field from being rendered within a form.

This filter is similar to `acf/load_field`, only it is applied later in the lifecycle when the field is about to be rendered. By this time, the field’s value has also been loaded.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-prepare_field/#changelog)

## Changelog

Link copied

- Added in version 5.0.0

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-prepare_field/#parameters)

## Parameters

Link copied

```php
apply_filters( 'acf/prepare_field', $field );
```

- `$field` _(array)_ The field array containing all settings (including value).

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-prepare_field/#modifers)

## Modifers

Link copied

This filter provides modifiers to target specific fields. The following filter names are available:

- `acf/prepare_field` Applies to all fields.
- `acf/prepare_field/type={$type}` Applies to all fields of a specific type.
- `acf/prepare_field/name={$name}` Applies to all fields of a specific name.
- `acf/prepare_field/key={$key}` Applies to all fields of a specific key.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-prepare_field/#examples)

## Examples

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-prepare_field/#modifying-a-field)

### Modifying a field

Link copied

This example demonstrates how to modify a specific field’s settings before it is rendered.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-prepare_field/#functionsphp)

#### functions.php

Link copied

```php
<?php
function my_acf_prepare_field( $field ) {

    // Lock-in the value "Example".
    if( $field['value'] === 'Example' ) {
        $field['readonly'] = true;
    };
    return $field;
}

// Apply to all fields.
// add_filter('acf/prepare_field', 'my_acf_prepare_field');

// Apply to select fields.
// add_filter('acf/prepare_field/type=select', 'my_acf_prepare_field');

// Apply to fields named "example_field".
add_filter('acf/prepare_field/name=example_field', 'my_acf_prepare_field');

// Apply to field with key "field_123abcf".
// add_filter('acf/prepare_field/key=field_123abcf', 'my_acf_prepare_field');
```

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-prepare_field/#preventing-a-field)

### Preventing a field

Link copied

This example demonstrates how to prevent a field from being rendered.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-prepare_field/#functionsphp)

#### functions.php

Link copied

```php
<?php
function my_acf_prepare_field( $field ) {

    // Don't show this field once it contains a value.
    if( $field['value'] ) {
        return false;
    }
    return $field;
}

// Apply to fields named "example_field".
add_filter('acf/prepare_field/name=example_field', 'my_acf_prepare_field');
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

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-prepare_field/#related)

## Related

Link copied

- Filters: [acf/load\_value](https://www.advancedcustomfields.com/resources/acf-load_value/)
- Filters: [acf/load\_field](https://www.advancedcustomfields.com/resources/acf-load_field/)
- Filters: [acf/update\_field](https://www.advancedcustomfields.com/resources/acf-update_field/)
- Filters: [acf/format\_value](https://www.advancedcustomfields.com/resources/acf-format_value/)
- Actions: [acf/render\_field](https://www.advancedcustomfields.com/resources/acf-render_field/)

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

[Got it](https://www.advancedcustomfields.com/resources/acf-prepare_field/#)