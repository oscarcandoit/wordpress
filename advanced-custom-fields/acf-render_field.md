---
url: https://www.advancedcustomfields.com/resources/acf-render_field
scraped_at: 2025-10-20T02:18:26.605Z
---

# acf/render\_field

Last updated Feb 17, 2022

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-render_field/#description)

## Description

Link copied

Used to output additional HTML before or after a field’s input.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-render_field/#changelog)

## Changelog

Link copied

- Added in version 5.0.0

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-render_field/#parameters)

## Parameters

Link copied

```php
do_action( 'acf/render_field', $field );
```

- `$field` _(array)_ The field array containing all settings.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-render_field/#modifers)

## Modifers

Link copied

This action provides modifiers to target specific fields. The following action names are available:

- `acf/render_field` Applies to all fields.
- `acf/render_field/type={$type}` Applies to all fields of a specific type.
- `acf/render_field/name={$name}` Applies to all fields of a specific name.
- `acf/render_field/key={$key}` Applies to all fields of a specific key.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-render_field/#example)

## Example

Link copied

This example demonstrates how to output additional HTML after a field.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-render_field/#functionsphp)

#### functions.php

Link copied

```php
<?php
function my_acf_render_field( $field ) {
    echo '<p>Some extra HTML.</p>';
}

// Apply to all fields.
add_action('acf/render_field', 'my_acf_render_field');

// Apply to image fields.
// add_action('acf/render_field/type=image', 'my_acf_render_field');

// Apply to fields named "hero_text".
// add_action('acf/render_field/name=hero_text', 'my_acf_render_field');

// Apply to field with key "field_123abcf".
// add_action('acf/render_field/key=field_123abcf', 'my_acf_render_field');
```

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-render_field/#notes)

## Notes

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-render_field/#priority)

### Priority

Link copied

In order to hook-in before ACF outputs any field HTML, use a priority less than 10 with either the "global" or "type" action names.

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

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-render_field/#related)

## Related

Link copied

- Filters: [acf/format\_value](https://www.advancedcustomfields.com/resources/acf-format_value/)
- Filters: [acf/update\_field](https://www.advancedcustomfields.com/resources/acf-update_field/)
- Filters: [acf/load\_value](https://www.advancedcustomfields.com/resources/acf-load_value/)
- Filters: [acf/update\_value](https://www.advancedcustomfields.com/resources/acf-update_value/)
- Filters: [acf/prepare\_field](https://www.advancedcustomfields.com/resources/acf-prepare_field/)

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

[Got it](https://www.advancedcustomfields.com/resources/acf-render_field/#)