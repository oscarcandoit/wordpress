---
url: https://www.advancedcustomfields.com/resources/acf-init
scraped_at: 2025-10-20T02:18:04.015Z
---

# acf/init

Last updated Feb 17, 2022

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-init/#description)

## Description

Link copied

Fires after ACF is fully initialized.

This action is similar to the WordPress [init](https://developer.wordpress.org/reference/hooks/init/) action, and should be used to extend or register items such as Blocks, Forms and Options Pages.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-init/#changelog)

## Changelog

Link copied

- Added in version 5.2.7

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-init/#example)

## Example

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-init/#functionsphp)

#### functions.php

Link copied

```php
add_action('acf/init', 'my_acf_init');
function my_acf_init() {

    // Get ACF version.
    $version = acf_get_setting('version');

    // Do something.
}
```

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-init/#notes)

## Notes

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-init/#timing)

### Timing

Link copied

Under normal circumstances, this action will fire during the "init" action (priority of 5). However, it may alternatively be triggered earlier if a field value is loaded during the `functions.php` file.

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

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-init/#related)

## Related

Link copied

- Actions: [acf/save\_post](https://www.advancedcustomfields.com/resources/acf-save_post/)
- Actions: [acf/validate\_save\_post](https://www.advancedcustomfields.com/resources/acf-validate_save_post/)
- Actions: [acf/options\_page/save](https://www.advancedcustomfields.com/resources/acf-options_page-save/)
- Functions: [acf\_add\_options\_sub\_page()](https://www.advancedcustomfields.com/resources/acf_add_options_sub_page/)
- Actions: [acf/input/admin\_footer](https://www.advancedcustomfields.com/resources/acf-input-admin_footer/)

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

[Got it](https://www.advancedcustomfields.com/resources/acf-init/#)