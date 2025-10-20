---
url: https://www.advancedcustomfields.com/resources/acf-options_page-settings
scraped_at: 2025-10-20T02:30:06.887Z
---

# acf/options\_page/settings

Last updated Apr 4, 2024

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-options_page-settings/#overview)

## Overview

Link copied

This filter allows you to modify the setting used by the [options page add-on](https://www.advancedcustomfields.com/add-ons/options-page/).

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-options_page-settings/#changelog)

## Changelog

Link copied

- Deprecated in [ACF PRO](https://advancedcustomfields.com/pro/)
- Added to the [Options Page Add-on](https://www.advancedcustomfields.com/add-ons/options-page/)

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-options_page-settings/#notes)

## Notes

Link copied

This filter has been deprecated in ACF PRO as it is no longer needed. ACF PRO does not add an options page by default and requires each options page to be added using the [add\_options\_page()](https://www.advancedcustomfields.com/resources/acf_add_options_page/) and [add\_options\_sub\_page()](https://www.advancedcustomfields.com/resources/acf_add_options_sub_page/) functions.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-options_page-settings/#parameters)

## Parameters

Link copied

```php
apply_filters('acf/options_page/settings', $settings);
```

- `$settings` (array)  an array of settings described below

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-options_page-settings/#settings)

#### $settings

Link copied

```php
$settings = array(

    /* (string) the options page title. Defaults to 'Options' */
    'title' => __('Options', 'acf'),

    /* (string) the options page menu title. Defaults to 'Options' */
    'menu' => __('Options', 'acf'),

    /* (string) the options page url slug. Defaults to 'acf-options' */
    'slug' => 'acf-options',

    /* the capability needed to access this admin page. Defaults to 'edit_posts' */
    'capability' => 'edit_posts',

    /* an array of sub menu pages (strings or arrays). Defaults to an empty array */
    'pages' => array()
);
```

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-options_page-settings/#usage)

## Usage

Link copied

This example will change the menu item title to ‘Global’ and add 3 sub pages!

```php
function my_acf_options_page_settings( $settings )
{
    $settings['title'] = 'Global';
    $settings['pages'] = array('Header', 'Sidebar', 'Footer');

    return $settings;
}

add_filter('acf/options_page/settings', 'my_acf_options_page_settings');
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

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-options_page-settings/#related)

## Related

Link copied

- Deprecated: [acf\_set\_options\_page\_menu()](https://www.advancedcustomfields.com/resources/acf_set_options_page_menu/)
- Deprecated: [acf\_set\_options\_page\_title()](https://www.advancedcustomfields.com/resources/acf_set_options_page_title/)
- Deprecated: [acf\_set\_options\_page\_capability()](https://www.advancedcustomfields.com/resources/acf_set_options_page_capability/)
- Functions: [acf\_add\_options\_page()](https://www.advancedcustomfields.com/resources/acf_add_options_page/)
- Actions: [acf/options\_page/save](https://www.advancedcustomfields.com/resources/acf-options_page-save/)

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

[Got it](https://www.advancedcustomfields.com/resources/acf-options_page-settings/#)