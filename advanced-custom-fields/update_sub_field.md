---
url: https://www.advancedcustomfields.com/resources/update_sub_field
scraped_at: 2025-10-20T02:23:12.606Z
---

# update\_sub\_field()

Last updated Feb 17, 2022

[Link to heading#](https://www.advancedcustomfields.com/resources/update_sub_field/#description)

## Description

Link copied

Updates the value of a specific sub field.

This function can be used inside or outside of a `have_rows()` loop. When used inside, the current row will be used to update the sub field value. When used outside, the rows and parents must be specified to target the correct value place.

[Link to heading#](https://www.advancedcustomfields.com/resources/update_sub_field/#parameters)

## Parameters

Link copied

```php
update_sub_field($selector, $value, [$post_id]);
```

- `$selector` _(string\|array)_ _(Required)_ The sub field name or key, or an array of ancestors and row numbers.
- `$value` _(mixed)_ _(Required)_ The new value.
- `$post_id` _(mixed)_ _(Optional)_ The post ID where the value is saved. Defaults to the current post.

[Link to heading#](https://www.advancedcustomfields.com/resources/update_sub_field/#return)

## Return

Link copied

_(bool)_ True on successful update, false on failure.

[Link to heading#](https://www.advancedcustomfields.com/resources/update_sub_field/#change-log)

## Change Log

Link copied

- Added in version 5.0.0

[Link to heading#](https://www.advancedcustomfields.com/resources/update_sub_field/#examples)

## Examples

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/update_sub_field/#update-a-sub-field-inside-of-a-haverows-loop)

### Update a sub field inside of a have\_rows() loop

Link copied

This example shows how to loop through a Repeater field and update one of its sub field values using the current row number.

```php
if( have_rows('repeater') ) {
    $i = 0;
    while( have_rows('repeater') ) {
        the_row();
        $i++;
        update_sub_field('caption', "This caption is in row {$i}");
    }
}
```

[Link to heading#](https://www.advancedcustomfields.com/resources/update_sub_field/#update-a-sub-field-outside-of-a-haverows-loop)

### Update a sub field outside of a have\_rows() loop

Link copied

This example shows how to update a sub field value outside of a `have_rows()` loop. Here, the `$selector` parameter is provided an array containing a mixture of field names and row numbers. This array should read from left to right, the parents to children relationship separated by the row number.

Please see notes regarding index offset.

```php
// Update "caption" within the first row of "repeater".
update_sub_field( array('repeater', 1, 'caption'), 'This caption is for the first row of the repeater!' );
```

[Link to heading#](https://www.advancedcustomfields.com/resources/update_sub_field/#update-a-nested-sub-field)

### Update a nested sub field

Link copied

The `update_sub_field()` function can also be used to target a nested sub field both inside and outside of a `have_rows()` loop. This example shows how to update a nested sub field function using both methods.

```php
// Loop over parent rows.
if( have_rows('repeater') ) {
    $parent_i = 0;
    while( have_rows('repeater') ) {
        the_row();
        $parent_i++;

        // Loop over child rows.
        if( have_rows('sub_repeater') ) {
            $child_i = 0;
            while( have_rows('sub_repeater') ) {
                the_row();
                $child_i++;

                // Update nested sub field value with reference to both parent and child indexes.
                update_sub_field('sub_sub_field', "This value is for repeater row {$parent_i}, and sub_repeater row {$child_i}");
            }
        }
    }
}

// target a nested sub field directly.
update_sub_field( array('repeater', 1, 'sub_repeater', 2, 'sub_sub_field'), 'This value is for repeater row 1, and sub_repeater row 2!' );
```

[Link to heading#](https://www.advancedcustomfields.com/resources/update_sub_field/#notes)

## Notes

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/update_sub_field/#index-offset)

### Index offset

Link copied

When targeting a sub field using a specific row number, please note that row numbers begin from 1 and not 0. This means that the first row has an index of 1, the second row has an index of 2, and so on.

To begin indexes from 0, please use the [row\_index\_offset](https://www.advancedcustomfields.com/resources/acf-settings/) setting like so.

[Link to heading#](https://www.advancedcustomfields.com/resources/update_sub_field/#functionsphp)

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

[Link to heading#](https://www.advancedcustomfields.com/resources/update_sub_field/#related)

## Related

Link copied

- Functions: [delete\_sub\_field()](https://www.advancedcustomfields.com/resources/delete_sub_field/)
- Functions: [add\_sub\_row()](https://www.advancedcustomfields.com/resources/add_sub_row/)
- Functions: [update\_sub\_row()](https://www.advancedcustomfields.com/resources/update_sub_row/)
- Functions: [delete\_sub\_row()](https://www.advancedcustomfields.com/resources/delete_sub_row/)
- Functions: [update\_row()](https://www.advancedcustomfields.com/resources/update_row/)

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

[Got it](https://www.advancedcustomfields.com/resources/update_sub_field/#)