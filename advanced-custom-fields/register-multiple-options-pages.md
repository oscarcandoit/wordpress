---
url: https://www.advancedcustomfields.com/resources/register-multiple-options-pages
scraped_at: 2025-10-20T02:16:32.590Z
---

# Register multiple options pages

Last updated Mar 24, 2015

[Link to heading#](https://www.advancedcustomfields.com/resources/register-multiple-options-pages/#overview)

## Overview

Link copied

Multiple options pages can be registered by making use of the [acf\_add\_options\_page()](https://www.advancedcustomfields.com/resources/acf_add_options_page/ "acf_add_options_page()") and [acf\_add\_options\_sub\_page()](https://www.advancedcustomfields.com/resources/acf_add_options_sub_page/ "acf_add_options_sub_page()") functions. Both functions can be used within the theme `functions.php` file.

Once registered, each options page will appear within the field group location rules making it quite easy to assign specific field groups to specific options pages.

Please note that for each options page, all values are saved and loaded using ‘option’ as the `$post_id`. This means that values are not saved to individual options pages, therefore, all fields require unique names to avoid data loss.

[Link to heading#](https://www.advancedcustomfields.com/resources/register-multiple-options-pages/#requirements)

## Requirements

Link copied

To make use of the options page feature, you will need a copy of [ACF PRO](https://www.advancedcustomfields.com/pro) (ACF v5), or the [options page add-on](https://www.advancedcustomfields.com/add-ons/options-page/ "Options Page") (ACF v4)

[Link to heading#](https://www.advancedcustomfields.com/resources/register-multiple-options-pages/#examples)

## Examples

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/register-multiple-options-pages/#basic)

### Basic

Link copied

This example demonstrates how to create the default options page with 3 extra sub pages. By default the parent options page will redirect to the first child, however, this setting can be customized (please see following example).

[Link to heading#](https://www.advancedcustomfields.com/resources/register-multiple-options-pages/#functionsphp)

#### functions.php

Link copied

```php
if( function_exists('acf_add_options_page') ) {

    acf_add_options_page();

    acf_add_options_sub_page('General');
    acf_add_options_sub_page('Header');
    acf_add_options_sub_page('Footer');

}
```

[Link to heading#](https://www.advancedcustomfields.com/resources/register-multiple-options-pages/#advanced)

### Advanced

Link copied

This example demonstrates how to create a new parent options page with 2 extra sub pages. Please note the use of `redirect => false` which allows the parent to have it’s own page instead of redirecting to the first child.

[Link to heading#](https://www.advancedcustomfields.com/resources/register-multiple-options-pages/#functionsphp)

#### functions.php

Link copied

```php
if( function_exists('acf_add_options_page') ) {

    acf_add_options_page(array(
        'page_title'    => 'Theme General Settings',
        'menu_title'    => 'Theme Settings',
        'menu_slug'     => 'theme-general-settings',
        'capability'    => 'edit_posts',
        'redirect'      => false
    ));

    acf_add_options_sub_page(array(
        'page_title'    => 'Theme Header Settings',
        'menu_title'    => 'Header',
        'parent_slug'   => 'theme-general-settings',
    ));

    acf_add_options_sub_page(array(
        'page_title'    => 'Theme Footer Settings',
        'menu_title'    => 'Footer',
        'parent_slug'   => 'theme-general-settings',
    ));

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

[Link to heading#](https://www.advancedcustomfields.com/resources/register-multiple-options-pages/#related)

## Related

Link copied

- Functions: [acf\_add\_options\_sub\_page()](https://www.advancedcustomfields.com/resources/acf_add_options_sub_page/)
- Functions: [acf\_add\_options\_page()](https://www.advancedcustomfields.com/resources/acf_add_options_page/)
- Functions: [acf\_form()](https://www.advancedcustomfields.com/resources/acf_form/)
- Guides: [Register fields via PHP](https://www.advancedcustomfields.com/resources/register-fields-via-php/)
- Guides: [How to Create an Options Page](https://www.advancedcustomfields.com/resources/how-to-create-an-options-page/)

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

[Got it](https://www.advancedcustomfields.com/resources/register-multiple-options-pages/#)