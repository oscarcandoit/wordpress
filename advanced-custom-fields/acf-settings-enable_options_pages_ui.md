---
url: https://www.advancedcustomfields.com/resources/acf-settings-enable_options_pages_ui
scraped_at: 2025-10-20T02:29:58.487Z
---

# acf/settings/enable\_options\_pages\_ui

Last updated Apr 4, 2024

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-settings-enable_options_pages_ui/#description)

## Description

Link copied

Used to disable the UI for registering options pages.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-settings-enable_options_pages_ui/#changelog)

## Changelog

Link copied

- Added in version 6.2.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-settings-enable_options_pages_ui/#example)

## Example

Link copied

This example demonstrates how to disable the UI for registering options pages. Options pages can still be registered with PHP using the `acf_add_options_page()` or `acf_add_options_sub_page()` functions.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-settings-enable_options_pages_ui/#functionsphp)

#### functions.php

Link copied

```php
<?php
add_filter( 'acf/settings/enable_options_pages_ui', '__return_false' );
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

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-settings-enable_options_pages_ui/#related)

## Related

Link copied

- Filters: [acf/settings/enable\_post\_types](https://www.advancedcustomfields.com/resources/acf-settings-enable_post_types/)
- Functions: [acf\_add\_options\_sub\_page()](https://www.advancedcustomfields.com/resources/acf_add_options_sub_page/)
- Filters: [acf/shortcode/prevent\_access](https://www.advancedcustomfields.com/resources/acf-shortcode-prevent_access/)
- Actions: [acf/options\_page/save](https://www.advancedcustomfields.com/resources/acf-options_page-save/)
- Filters: [acf/field\_group/disable\_field\_settings\_tabs](https://www.advancedcustomfields.com/resources/acf-field_group-disable_field_settings_tabs/)

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

[Got it](https://www.advancedcustomfields.com/resources/acf-settings-enable_options_pages_ui/#)