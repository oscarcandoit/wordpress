---
url: https://www.advancedcustomfields.com/resources/acf-compatibility
scraped_at: 2025-10-20T02:19:27.734Z
---

# acf/compatibility

Last updated Feb 17, 2022

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-compatibility/#description)

## Description

Link copied

Used to enable backwards compatibility support for changed functionality.

Support for each compatibility can be enabled by its own filter. Compatibilities are disabled by default and can be opted-in using the `__return_true()` function.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-compatibility/#changelog)

## Changelog

Link copied

- Added in version 5.2.0

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-compatibility/#parameters)

## Parameters

Link copied

```php
apply_filters( "acf/compatibility/{$name}", $enabled );
```

- `$enabled` _(bool)_ Whether of not backwards compatibility support is enabled. Defaults to `false`.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-compatibility/#compatibilities)

## Compatibilities

Link copied

The following table lists the available compatibilities which can be enabled.

| Name | Added | Description |
| --- | --- | --- |
| `field_wrapper_class` | 5.2.0 | Field class names changed in v5.2.0 from `field_type-{$type}` to `acf-field-{$type}`. This change was introduced to better optimise JS performance. |

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-compatibility/#example)

## Example

Link copied

This example demonstrates how to enable backwards-compatibility for field class names.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-compatibility/#functionsphp)

#### functions.php

Link copied

```php
add_filter('acf/compatibility/field_wrapper_class', '__return_true');
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

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-compatibility/#related)

## Related

Link copied

- Filters: [acf/update\_value](https://www.advancedcustomfields.com/resources/acf-update_value/)
- Filters: [acf/shortcode/prevent\_access](https://www.advancedcustomfields.com/resources/acf-shortcode-prevent_access/)
- Filters: [acf/format\_value](https://www.advancedcustomfields.com/resources/acf-format_value/)
- Filters: [acf/validate\_value](https://www.advancedcustomfields.com/resources/acf-validate_value/)
- Filters: [acf/update\_field](https://www.advancedcustomfields.com/resources/acf-update_field/)

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

[Got it](https://www.advancedcustomfields.com/resources/acf-compatibility/#)