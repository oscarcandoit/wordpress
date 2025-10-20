---
url: https://www.advancedcustomfields.com/resources/acf_set_options_page_menu
scraped_at: 2025-10-20T02:22:06.207Z
---

# acf\_set\_options\_page\_menu()

Last updated Feb 17, 2022

[Link to heading#](https://www.advancedcustomfields.com/resources/acf_set_options_page_menu/#description)

## Description

Link copied

_![](https://www.advancedcustomfields.com/wp-content/themes/acf/assets/images/ui-icons/hash.svg)_

This function has been deprecated. Please use the [acf/options\_page/settings](https://www.advancedcustomfields.com/resources/acf-options_page-settings/) filter instead.

Modifies the default Options Page menu name, displayed in the admin menu.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf_set_options_page_menu/#requirements)

## Requirements

Link copied

- [Options Page Add-on](https://www.advancedcustomfields.com/add-ons/options-page/) version 1.2.0 or later

[Link to heading#](https://www.advancedcustomfields.com/resources/acf_set_options_page_menu/#parameters)

## Parameters

Link copied

```php
acf_set_options_page_menu( $menu_name );
```

- `$menu_name` _(string)_ _(Required)_ The menu name for the default Options Page. Defaults to ‘Options’.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf_set_options_page_menu/#example)

## Example

Link copied

This example demonstrates how to change the default Options Page menu name to ‘Extra’.

```php
if( function_exists('acf_set_options_page_menu') ) {
    acf_set_options_page_menu( __('Extra') );
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

[Link to heading#](https://www.advancedcustomfields.com/resources/acf_set_options_page_menu/#related)

## Related

Link copied

- Deprecated: [acf\_set\_options\_page\_title()](https://www.advancedcustomfields.com/resources/acf_set_options_page_title/)
- Deprecated: [acf\_set\_options\_page\_capability()](https://www.advancedcustomfields.com/resources/acf_set_options_page_capability/)
- Deprecated: [acf/options\_page/settings](https://www.advancedcustomfields.com/resources/acf-options_page-settings/)
- Actions: [acf/options\_page/save](https://www.advancedcustomfields.com/resources/acf-options_page-save/)
- Functions: [acf\_add\_options\_page()](https://www.advancedcustomfields.com/resources/acf_add_options_page/)

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

[Got it](https://www.advancedcustomfields.com/resources/acf_set_options_page_menu/#)