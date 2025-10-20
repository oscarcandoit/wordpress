---
url: https://www.advancedcustomfields.com/resources/get_sub_field_object
scraped_at: 2025-10-20T02:28:49.332Z
---

# get\_sub\_field\_object()

Last updated Feb 6, 2024

[Link to heading#](https://www.advancedcustomfields.com/resources/get_sub_field_object/#description)

## Description

Link copied

Returns the settings of a specific sub field within a have\_rows() loop.

Each field contains many settings such as a label, name and type. This function can be used to load these settings as an array along with the field’s value.

[Link to heading#](https://www.advancedcustomfields.com/resources/get_sub_field_object/#parameters)

## Parameters

Link copied

```php
get_sub_field_object($selector, [$format_value = true], [$load_value = true], [$escape_html = true]);
```

- `$selector` _(string)_ _(Required)_ The field name or field key.
- `$format_value` _(bool)_ _(Optional)_ Whether to apply formatting logic. Defaults to true.
- `$load_value` _(bool)_ _(Optional)_ Whether to load the field’s value. Defaults to true.
- `$escape_html` _(bool)_ _(Optional)_ Since 6.2.6 – return an escaped HTML safe version of the field value. Requires $format\_value to be true. Defaults to false.

[Link to heading#](https://www.advancedcustomfields.com/resources/get_sub_field_object/#return)

## Return

Link copied

_(array)_ This function will return an array looking something like the following. Please note that each field contains unique settings.

```php
array(
    'ID'                => 0,
    'key'               => '',
    'label'             => '',
    'name'              => '',
    'prefix'            => '',
    'type'              => 'text',
    'value'             => null,
    'menu_order'        => 0,
    'instructions'      => '',
    'required'          => 0,
    'id'                => '',
    'class'             => '',
    'conditional_logic' => 0,
    'parent'            => 0,
    'wrapper'           => array(
        'width'             => '',
        'class'             => '',
        'id'                => ''
    )
);
```

[Link to heading#](https://www.advancedcustomfields.com/resources/get_sub_field_object/#changelog)

## Changelog

Link copied

- Added in version 4.0

[Link to heading#](https://www.advancedcustomfields.com/resources/get_sub_field_object/#example)

## Example

Link copied

This function works in a similar way to `get_sub_field()`, meaning it must be used within a `have_rows()` loop. This example shows how to list out a sub field’s choices using its value to highlight the selected one.

```php
<?php if( have_rows('repeater') ): ?>
    <?php while( have_rows('repeater') ): the_row(); ?>
        <?php

        // Get the sub field called "select".
        $select = get_sub_field_object('select');

        // Get its value.
        $value = $select['value'];

        // Loop over its choices.
        ?>
        <ul>
            <?php foreach( $select['choices'] as $k => $v ): ?>
                <li <?php echo ($k === $value) ? 'class="selected"' : ''; ?>>
                    <?php echo $v; ?>
                </li>
            <?php endforeach; ?>
        </ul>
    <?php endwhile; ?>
<?php endif; ?>
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

[Link to heading#](https://www.advancedcustomfields.com/resources/get_sub_field_object/#related)

## Related

Link copied

- Basic: [get\_field\_object()](https://www.advancedcustomfields.com/resources/get_field_object/)
- Basic: [get\_field\_objects()](https://www.advancedcustomfields.com/resources/get_field_objects/)
- Functions: [get\_sub\_field()](https://www.advancedcustomfields.com/resources/get_sub_field/)
- Functions: [get\_row()](https://www.advancedcustomfields.com/resources/get_row/)
- Basic: [get\_fields()](https://www.advancedcustomfields.com/resources/get_fields/)

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

[Got it](https://www.advancedcustomfields.com/resources/get_sub_field_object/#)