---
url: https://www.advancedcustomfields.com/resources/acf_set_options_page_capability
scraped_at: 2025-10-20T02:22:02.135Z
---

# acf\_set\_options\_page\_capability()

Last updated Feb 17, 2022

[Link to heading#](https://www.advancedcustomfields.com/resources/acf_set_options_page_capability/#description)

## Description

Link copied

_![](https://www.advancedcustomfields.com/wp-content/themes/acf/assets/images/ui-icons/hash.svg)_

This function has been deprecated. Please use the [acf/options\_page/settings](https://www.advancedcustomfields.com/resources/acf-options_page-settings/) filter instead.

Modifies the default Options Page capability setting.

The term ‘capability’ refers to the user roles and permissions that grant access to the Options Page. You can learn more about [capability settings here](http://codex.wordpress.org/Roles_and_Capabilities).

[Link to heading#](https://www.advancedcustomfields.com/resources/acf_set_options_page_capability/#requirements)

## Requirements

Link copied

- [Options Page Add-on](https://www.advancedcustomfields.com/add-ons/options-page/) version 1.1.0 or later.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf_set_options_page_capability/#parameters)

## Parameters

Link copied

```php
acf_set_options_page_capability( $capability );
```

- `$capability` _(string)_ _(Required)_ The capability for the default Options Page. Defaults to ‘edit\_posts’.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf_set_options_page_capability/#example)

## Example

Link copied

This example demonstrates how to change the default Options Page capability to ‘manage\_options’.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf_set_options_page_capability/#functionsphp)

#### functions.php

Link copied

```php
if( function_exists('acf_set_options_page_capability') ) {
    acf_set_options_page_capability('manage_options');
}
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

[Link to heading#](https://www.advancedcustomfields.com/resources/acf_set_options_page_capability/#related)

## Related

Link copied

- Deprecated: [acf\_set\_options\_page\_title()](https://www.advancedcustomfields.com/resources/acf_set_options_page_title/)
- Deprecated: [acf\_set\_options\_page\_menu()](https://www.advancedcustomfields.com/resources/acf_set_options_page_menu/)
- Deprecated: [acf/options\_page/settings](https://www.advancedcustomfields.com/resources/acf-options_page-settings/)
- Functions: [acf\_add\_options\_page()](https://www.advancedcustomfields.com/resources/acf_add_options_page/)
- Functions: [acf\_form()](https://www.advancedcustomfields.com/resources/acf_form/)

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

[Got it](https://www.advancedcustomfields.com/resources/acf_set_options_page_capability/#)