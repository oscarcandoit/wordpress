---
url: https://www.advancedcustomfields.com/resources/acf-fields-flexible_content-layout_title
scraped_at: 2025-10-20T02:24:01.721Z
---

# acf/fields/flexible\_content/layout\_title

Last updated Nov 17, 2022

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-fields-flexible_content-layout_title/#description)

## Description

Link copied

Used to modify the `$title` HTML displayed at the top of each flexible content layout.

Within the filter callback, it is possible to load sub field values via the `get_sub_field()`, `the_sub_field()` and `get_row()` functions and display them within the returned string.

This filter is also run via an AJAX request each time the layout is toggled open or closed.

Here is a before/after visual example to demonstrate how this filter can improve UX.

[![Screenshot of default Flexible Content layout titles.](https://www.advancedcustomfields.com/wp-content/uploads/2016/03/flexible-content-layout-title-before.png)](https://www.advancedcustomfields.com/wp-content/uploads/2016/03/flexible-content-layout-title-before.png) Default layout titles[![Screenshot of customized Flexible Content layout titles.](https://www.advancedcustomfields.com/wp-content/uploads/2016/03/flexible-content-layout-title-after.png)](https://www.advancedcustomfields.com/wp-content/uploads/2016/03/flexible-content-layout-title-after.png) Customized layout titles

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-fields-flexible_content-layout_title/#changelog)

## Changelog

Link copied

- Added in version 5.3.6

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-fields-flexible_content-layout_title/#parameters)

## Parameters

Link copied

```php
apply_filters( 'acf/fields/flexible_content/layout_title', $title, $field, $layout, $i );
```

- `$title` _(string)_ The layout title text. Defaults to the layout name.
- `$field` _(array)_ The field array containing all settings.
- `$layout` _(array)_ The layout array containing all settings.
- `$i` _(int)_ The layout index beginning at 0.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-fields-flexible_content-layout_title/#modifers)

## Modifers

Link copied

This filter provides modifiers to target specific fields. The following filter names are available:
– `acf/fields/flexible_content/layout_title` Applies to all fields.
– `acf/fields/flexible_content/layout_title/name={$name}` Applies to all fields of a specific name.
– `acf/fields/flexible_content/layout_title/key={$key}` Applies to all fields of a specific key.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-fields-flexible_content-layout_title/#example)

## Example

Link copied

This example demonstrates how to customize the title of each Flexible Content layout and display sub field values.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-fields-flexible_content-layout_title/#functionsphp)

#### functions.php

Link copied

```php
<?php
add_filter('acf/fields/flexible_content/layout_title/name=my_flex_field', 'my_acf_fields_flexible_content_layout_title', 10, 4);
function my_acf_fields_flexible_content_layout_title( $title, $field, $layout, $i ) {

    // Remove layout name from title.
    $title = '';

    // Display thumbnail image.
    if( $image = get_sub_field('image') ) {
        $title .= '<div class="thumbnail"><img src="' . esc_url($image['sizes']['thumbnail']) . '" height="36px" /></div>';
    }

    // load text sub field
    if( $text = get_sub_field('text') ) {
        $title .= '<b>' . esc_html($text) . '</b>';
    }
    return $title;
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

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-fields-flexible_content-layout_title/#related)

## Related

Link copied

- Filters: [acf/load\_field](https://www.advancedcustomfields.com/resources/acf-load_field/)
- Filters: [acf/load\_value](https://www.advancedcustomfields.com/resources/acf-load_value/)
- Filters: [acf/prepare\_field](https://www.advancedcustomfields.com/resources/acf-prepare_field/)
- Filters: [acf/update\_field](https://www.advancedcustomfields.com/resources/acf-update_field/)
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

[Got it](https://www.advancedcustomfields.com/resources/acf-fields-flexible_content-layout_title/#)