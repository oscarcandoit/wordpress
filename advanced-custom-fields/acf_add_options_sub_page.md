---
url: https://www.advancedcustomfields.com/resources/acf_add_options_sub_page
scraped_at: 2025-10-20T02:21:45.808Z
---

# acf\_add\_options\_sub\_page()

Last updated Feb 17, 2022

[Link to heading#](https://www.advancedcustomfields.com/resources/acf_add_options_sub_page/#description)

## Description

Link copied

Adds a new options sub page to the admin menu.

Options pages are used to store global settings. These settings are not tied to a specific post, but are instead stored in the `wp_options` table.

Once registered, your page will appear in the admin menu. You can then assign fields to your page via the "Options Page" location rule when editing a field group.

This function is essentially a wrapper for [acf\_add\_options\_page()](https://www.advancedcustomfields.com/resources/acf_add_options_page/) providing a default value for the _parent\_slug_ attribute of "acf-options".

[Link to heading#](https://www.advancedcustomfields.com/resources/acf_add_options_sub_page/#parameters)

## Parameters

Link copied

```php
acf_add_options_sub_page( [$settings] );
```

[Link to heading#](https://www.advancedcustomfields.com/resources/acf_add_options_sub_page/#settings)

### $settings

Link copied

_(array)_ _(Optional)_ Array of arguments for registering an options page. [See list of available parameters](https://www.advancedcustomfields.com/resources/acf_add_options_page/)

[Link to heading#](https://www.advancedcustomfields.com/resources/acf_add_options_sub_page/#examples)

## Examples

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/acf_add_options_sub_page/#default-options-sub-page)

### Default options sub page

Link copied

This example shows how to create a default options sub page.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf_add_options_sub_page/#functionsphp)

#### functions.php

Link copied

```php
if( function_exists('acf_add_options_sub_page') ) {
    acf_add_options_sub_page();
}
```

[Link to heading#](https://www.advancedcustomfields.com/resources/acf_add_options_sub_page/#customized-options-sub-page)

### Customized options sub page

Link copied

This example shows how to create a customized options sub page and store the data in a variable for later use.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf_add_options_sub_page/#functionsphp)

#### functions.php

Link copied

```php
add_action('acf/init', 'my_acf_op_init');
function my_acf_op_init() {

    // Check function exists.
    if( function_exists('acf_add_options_sub_page') ) {

        // Add parent.
        $parent = acf_add_options_page(array(
            'page_title'  => __('Theme General Settings'),
            'menu_title'  => __('Theme Settings'),
            'redirect'    => false,
        ));

        // Add sub page.
        $child = acf_add_options_sub_page(array(
            'page_title'  => __('Social Settings'),
            'menu_title'  => __('Social'),
            'parent_slug' => $parent['menu_slug'],
        ));
    }
}
```

[Link to heading#](https://www.advancedcustomfields.com/resources/acf_add_options_sub_page/#notes)

## Notes

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/acf_add_options_sub_page/#priority)

### Priority

Link copied

This function must be used before the action `admin_menu` (priority 99) as this is when admin pages are registered in WordPress core. We advise using the "acf/init" action.

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

[Link to heading#](https://www.advancedcustomfields.com/resources/acf_add_options_sub_page/#related)

## Related

Link copied

- Functions: [acf\_add\_options\_page()](https://www.advancedcustomfields.com/resources/acf_add_options_page/)
- Guides: [Register multiple options pages](https://www.advancedcustomfields.com/resources/register-multiple-options-pages/)
- Functions: [acf\_form()](https://www.advancedcustomfields.com/resources/acf_form/)
- Guides: [How to Create an Options Page](https://www.advancedcustomfields.com/resources/how-to-create-an-options-page/)
- Features: [Options Page](https://www.advancedcustomfields.com/resources/options-page/)

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

[Got it](https://www.advancedcustomfields.com/resources/acf_add_options_sub_page/#)