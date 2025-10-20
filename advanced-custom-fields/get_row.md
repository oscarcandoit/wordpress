---
url: https://www.advancedcustomfields.com/resources/get_row
scraped_at: 2025-10-20T02:22:42.809Z
---

# get\_row()

Last updated Feb 17, 2022

[Link to heading#](https://www.advancedcustomfields.com/resources/get_row/#description)

## Description

Link copied

Returns an array containing all values (in the format name => value) for the current row within a `have_rows()` loop.

[Link to heading#](https://www.advancedcustomfields.com/resources/get_row/#parameters)

## Parameters

Link copied

```php
get_row([$format_value = false]);
```

- `$format_value` _(bool)_ _(Optional)_ Whether to apply formatting logic. Defaults to false.

[Link to heading#](https://www.advancedcustomfields.com/resources/get_row/#return)

## Return

Link copied

_(array)_ Array of values in the format name => value.

[Link to heading#](https://www.advancedcustomfields.com/resources/get_row/#changelog)

## Changelog

Link copied

- Added in version 5.3.3

[Link to heading#](https://www.advancedcustomfields.com/resources/get_row/#example)

## Example

Link copied

This example demonstrates how to load the current row values and display them.

```php
<?php if( have_rows('slides') ): ?>
    <?php while( have_rows('slides') ): the_row();

        // Get all values for this row.
        $row = get_row();

        // Check for image value.
        if( $row['image'] ): ?>
            <img src="<?php echo $row['image']; ?>" />
            <p><?php echo $row['caption']; ?></p>
        <?php endif; ?>
    <?php endwhile; ?>
<?php endif; ?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/get_row/#notes)

## Notes

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/get_row/#similarities-to-therow)

### Similarities to the\_row()

Link copied

This function returns the same data as `the_row()`, however, it doesn’t step through the rows of a `have_rows()` loop.

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

[Link to heading#](https://www.advancedcustomfields.com/resources/get_row/#related)

## Related

Link copied

- Functions: [have\_rows()](https://www.advancedcustomfields.com/resources/have_rows/)
- Functions: [get\_sub\_field\_object()](https://www.advancedcustomfields.com/resources/get_sub_field_object/)
- Functions: [get\_row\_index()](https://www.advancedcustomfields.com/resources/get_row_index/)
- Deprecated: [has\_sub\_field()](https://www.advancedcustomfields.com/resources/has_sub_field/)
- Functions: [get\_row\_layout()](https://www.advancedcustomfields.com/resources/get_row_layout/)

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

[Got it](https://www.advancedcustomfields.com/resources/get_row/#)