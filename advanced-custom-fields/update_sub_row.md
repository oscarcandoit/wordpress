---
url: https://www.advancedcustomfields.com/resources/update_sub_row
scraped_at: 2025-10-20T02:23:08.817Z
---

# update\_sub\_row()

Last updated Feb 17, 2022

[Link to heading#](https://www.advancedcustomfields.com/resources/update_sub_row/#overview)

## Overview

Link copied

Updates a row of data for an existing Repeater or Flexible Content sub field value.

This function can be used inside or outside of a `have_rows()` loop. When used inside, the current row will be used to update the sub field value. When used outside, the rows and parents must be specified to target the correct value place.

Please note this function is used to modify a sub field value. To modify a parent field value, please use the [update\_row()](https://www.advancedcustomfields.com/resources/update_row/) function.

[Link to heading#](https://www.advancedcustomfields.com/resources/update_sub_row/#parameters)

## Parameters

Link copied

```php
update_sub_row($selector, $row, $value, [$post_id])
```

- `$selector` _(string\|array)_ _(Required)_ The sub field name or key, or an array of ancestors and row numbers.
- `$row` _(int)_ _(Required)_ The row number to update.
- `$value` _(array)_ _(Required)_ The new row data.
- `$post_id` _(mixed)_ _(Optional)_ The post ID where the value is saved. Defaults to the current post.

[Link to heading#](https://www.advancedcustomfields.com/resources/update_sub_row/#return)

## Return

Link copied

_(bool)_ True on successful update, false on failure.

[Link to heading#](https://www.advancedcustomfields.com/resources/update_sub_row/#change-log)

## Change Log

Link copied

- Added in version 5.4.7

[Link to heading#](https://www.advancedcustomfields.com/resources/update_sub_row/#update-a-sub-row-inside-of-a-haverows-loop)

### Update a sub row inside of a have\_rows() loop

Link copied

This example shows how to update a row of data to an existing nested repeater field called ‘images’. This nested repeater field contains 3 sub fields (‘image’, ‘alt’, ‘link’).

```php
// Loop over all staff members.
if( have_rows('staff_members') ) {
    while( have_rows('staff_members') ) {
        the_row();

        // Get this staff member's name.
        $name = get_sub_field('name');

        // Update this staff member's first image.
        $value = array(
            'image' => 123,
            'alt'   => "The first photo of $name",
            'link'  => 'http://website.com'
        );
        update_sub_row('images', 1, $value);
    }
}
```

[Link to heading#](https://www.advancedcustomfields.com/resources/update_sub_row/#update-a-sub-row-outside-of-a-haverows-loop)

### Update a sub row outside of a have\_rows() loop

Link copied

This example shows how to update a row of data outside of a `have_rows()` loop. Here, the `$selector` parameter is provided an array containing a mixture of field names and row numbers. This array should read from left to right, the parents to children relationship separated by the row number.

Please see notes regarding index offset.

```php
// Update the first staff member's first image.
$value = array(
    'image' => 123,
    'alt'   => "The first photo of the first staff member",
    'link'  => 'http://website.com'
);
update_sub_row( array('staff_members', 1, 'images'), 1, $value );

// Update the first staff member's second image.
update_sub_row( array('staff_members', 1, 'images'), 2, $value );
```

[Link to heading#](https://www.advancedcustomfields.com/resources/update_sub_row/#notes)

## Notes

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/update_sub_row/#index-offset)

### Index offset

Link copied

When targeting a sub field using a specific row number, please note that row numbers begin from 1 and not 0. This means that the first row has an index of 1, the second row has an index of 2, and so on.

To begin indexes from 0, please use the [row\_index\_offset](https://www.advancedcustomfields.com/resources/acf-settings/) setting like so.

[Link to heading#](https://www.advancedcustomfields.com/resources/update_sub_row/#functionsphp)

#### functions.php

Link copied

```php
add_filter('acf/settings/row_index_offset', '__return_zero');
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

[Link to heading#](https://www.advancedcustomfields.com/resources/update_sub_row/#related)

## Related

Link copied

- Functions: [add\_sub\_row()](https://www.advancedcustomfields.com/resources/add_sub_row/)
- Functions: [delete\_sub\_row()](https://www.advancedcustomfields.com/resources/delete_sub_row/)
- Functions: [update\_row()](https://www.advancedcustomfields.com/resources/update_row/)
- Functions: [update\_sub\_field()](https://www.advancedcustomfields.com/resources/update_sub_field/)
- Functions: [add\_row()](https://www.advancedcustomfields.com/resources/add_row/)

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

[Got it](https://www.advancedcustomfields.com/resources/update_sub_row/#)