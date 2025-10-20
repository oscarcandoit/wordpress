---
url: https://www.advancedcustomfields.com/resources/get_row_index
scraped_at: 2025-10-20T02:29:25.273Z
---

# get\_row\_index()

Last updated Apr 4, 2024

[Link to heading#](https://www.advancedcustomfields.com/resources/get_row_index/#description)

## Description

Link copied

Returns the current row index within a `have_rows()` loop.

Whilst stepping though the rows of a Repeater or Flexible Content field, you may find it necessary to determine the row number (index). This function does exactly that, avoiding the need of a custom `$i++` counter.

[Link to heading#](https://www.advancedcustomfields.com/resources/get_row_index/#return)

## Return

Link copied

_(int)_ A numeric index of the current row. See notes regarding index offset.

[Link to heading#](https://www.advancedcustomfields.com/resources/get_row_index/#changelog)

## Changelog

Link copied

- Added in version 5.3.4

[Link to heading#](https://www.advancedcustomfields.com/resources/get_row_index/#example)

## Example

Link copied

This example demonstrates how to use this function to output unique ID’s into each row’s wrapper. This is useful for CSS / JS customization.

```php
<?php if( have_rows('slides') ): ?>
    <?php while( have_rows('slides') ): the_row(); ?>
        <div class="accordion" id="accordion-<?php echo get_row_index(); ?>">
            <h3><?php the_sub_field('title'); ?></h3>
            <?php the_sub_field('text'); ?>
        </div>
    <?php endwhile; ?>
<?php endif; ?>
```

```php
<div class="accordion" id="accordion-1">
    <h3>My first accordion</h3>
    <p>Some text here.</p>
</div>
<div class="accordion" id="accordion-2">
    <h3>My second accordion</h3>
    <p>Some moretext here.</p>
</div>

## Notes

### Index offset
The index returned from this function begins at 1. This means a Repeater field with 3 rows of data will produce indexes of 1, 2 and 3.

To begin indexes from 0, please use the [row_index_offset](https://www.advancedcustomfields.com/resources/acf-settings/) setting like so.
#### functions.php

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

[Link to heading#](https://www.advancedcustomfields.com/resources/get_row_index/#related)

## Related

Link copied

- Functions: [have\_rows()](https://www.advancedcustomfields.com/resources/have_rows/)
- Deprecated: [has\_sub\_field()](https://www.advancedcustomfields.com/resources/has_sub_field/)
- Functions: [get\_row()](https://www.advancedcustomfields.com/resources/get_row/)
- Functions: [get\_row\_layout()](https://www.advancedcustomfields.com/resources/get_row_layout/)
- Deprecated: [the\_flexible\_field()](https://www.advancedcustomfields.com/resources/the_flexible_field/)

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

[Got it](https://www.advancedcustomfields.com/resources/get_row_index/#)