---
url: https://www.advancedcustomfields.com/resources/flexible-content
scraped_at: 2025-10-20T02:16:03.407Z
---

# Flexible Content

Last updated Feb 17, 2022

[Link to heading#](https://www.advancedcustomfields.com/resources/flexible-content/#description)

## Description

Link copied

The Flexible Content field provides a simple, structured, block-based editor.

Using layouts and sub fields to design the available blocks, this field type acts as a blank canvas to which you can define, create and manage content with total control.

[Link to heading#](https://www.advancedcustomfields.com/resources/flexible-content/#screenshots)

## Screenshots

Link copied

[![A Flexible Content field that allows you to choose a layout](https://www.advancedcustomfields.com/wp-content/uploads/2013/02/acf-flexible-content-field-interface.jpg)](https://www.advancedcustomfields.com/wp-content/uploads/2013/02/acf-flexible-content-field-interface.jpg) The Flexible Content field interface[![List of field settings shown when setting up a Flexible Content field](https://www.advancedcustomfields.com/wp-content/uploads/2013/02/acf-flexible-content-field-settings.jpg)](https://www.advancedcustomfields.com/wp-content/uploads/2013/02/acf-flexible-content-field-settings.jpg) The Flexible Content field settings

[Link to heading#](https://www.advancedcustomfields.com/resources/flexible-content/#settings)

## Settings

Link copied

- **Layouts**


Defines the layouts available when editing content. Each layout contains Label, Name, Limit, Display and Field settings.

- **Button Label**


The text shown in the ‘Add Row’ button.

- **Minimum Layouts**


Sets a limit on how many layouts are required.

- **Maximum Layouts**


Sets a limit on how many layouts are allowed.


[Link to heading#](https://www.advancedcustomfields.com/resources/flexible-content/#template-usage)

## Template usage

Link copied

The Flexible Content field returns a multi-dimensional array containing the layouts and their sub field values.

Accessing the value is done via the [have\_rows](https://www.advancedcustomfields.com/resources/functions/have_rows/), [the\_row](https://www.advancedcustomfields.com/resources/functions/have_rows/), [get\_sub\_field](https://www.advancedcustomfields.com/resources/functions/get_sub_field/), and [the\_sub\_field](https://www.advancedcustomfields.com/resources/functions/the_sub_field/) functions.

[Link to heading#](https://www.advancedcustomfields.com/resources/flexible-content/#loop-example)

### Loop example

Link copied

This example demonstrates how to loop over a Flexible Content field value and access sub fields from different layouts.

```php
<?php

// Check value exists.
if( have_rows('content') ):

    // Loop through rows.
    while ( have_rows('content') ) : the_row();

        // Case: Paragraph layout.
        if( get_row_layout() == 'paragraph' ):
            $text = get_sub_field('text');
            // Do something...

        // Case: Download layout.
        elseif( get_row_layout() == 'download' ):
            $file = get_sub_field('file');
            // Do something...

        endif;

    // End loop.
    endwhile;

// No value.
else :
    // Do something...
endif;
```

[Link to heading#](https://www.advancedcustomfields.com/resources/flexible-content/#display-layouts)

### Display layouts

Link copied

This example demonstrates how to loop through a Flexible Content field and generate HTML for different layouts.

```php
<?php if( have_rows('content') ): ?>
    <?php while( have_rows('content') ): the_row(); ?>
        <?php if( get_row_layout() == 'paragraph' ): ?>
            <?php the_sub_field('paragraph'); ?>
        <?php elseif( get_row_layout() == 'image' ):
            $image = get_sub_field('image');
            ?>
            <figure>
                <?php echo wp_get_attachment_image( $image['ID'], 'full' ); ?>
                <figcaption><?php echo $image['caption']; ?></figcaption>
            </figure>
        <?php endif; ?>
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

[Link to heading#](https://www.advancedcustomfields.com/resources/flexible-content/#related)

## Related

Link copied

- Functions: [get\_row\_layout()](https://www.advancedcustomfields.com/resources/get_row_layout/)
- Deprecated: [the\_flexible\_field()](https://www.advancedcustomfields.com/resources/the_flexible_field/)
- Functions: [the\_sub\_field()](https://www.advancedcustomfields.com/resources/the_sub_field/)
- Deprecated: [has\_sub\_field()](https://www.advancedcustomfields.com/resources/has_sub_field/)
- Field Types: [Repeater](https://www.advancedcustomfields.com/resources/repeater/)

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

[Got it](https://www.advancedcustomfields.com/resources/flexible-content/#)