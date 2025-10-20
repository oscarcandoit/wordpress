---
url: https://www.advancedcustomfields.com/resources/acf-field_group-auto_add_first_field
scraped_at: 2025-10-20T02:26:36.839Z
---

# acf/field\_group/auto\_add\_first\_field

Last updated Aug 17, 2023

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-field_group-auto_add_first_field/#description)

## Description

Link copied

Filter for determining if a new field group should load with a text field automatically. The default behavior for this filter is true, meaning field groups will initialize with a text field automatically.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-field_group-auto_add_first_field/#changelog)

## Changelog

Link copied

- Added in version 6.1.7

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-field_group-auto_add_first_field/#example)

## Example

Link copied

This example demonstrates how to disable the auto generation of a text field on a newly created field group.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-field_group-auto_add_first_field/#functionsphp)

#### functions.php

Link copied

```php
<?php
add_filter( 'acf/field_group/auto_add_first_field', '__return_false' );
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

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-field_group-auto_add_first_field/#related)

## Related

Link copied

- Filters: [acf/load\_value](https://www.advancedcustomfields.com/resources/acf-load_value/)
- Filters: [acf/load\_field](https://www.advancedcustomfields.com/resources/acf-load_field/)
- Filters: [acf/shortcode/prevent\_access](https://www.advancedcustomfields.com/resources/acf-shortcode-prevent_access/)
- Filters: [acf/field\_group/disable\_field\_settings\_tabs](https://www.advancedcustomfields.com/resources/acf-field_group-disable_field_settings_tabs/)
- Filters: [acf/format\_value](https://www.advancedcustomfields.com/resources/acf-format_value/)

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

[Got it](https://www.advancedcustomfields.com/resources/acf-field_group-auto_add_first_field/#)