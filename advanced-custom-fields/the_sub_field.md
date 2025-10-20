---
url: https://www.advancedcustomfields.com/resources/the_sub_field
scraped_at: 2025-10-20T02:22:59.808Z
---

# the\_sub\_field()

Last updated Feb 17, 2022

[Link to heading#](https://www.advancedcustomfields.com/resources/the_sub_field/#description)

## Description

Link copied

Displays the value of a specific sub field value from a Repeater or Flexible Content field loop.

This function is essentially the same as `echo get_sub_field()`.

[Link to heading#](https://www.advancedcustomfields.com/resources/the_sub_field/#parameters)

## Parameters

Link copied

```php
the_sub_field( $selector, [$format_value] );
```

- `$selector` _(string)_ _(Required)_ The sub field name or field key.
- `$format_value` _(bool)_ _(Optional)_ Whether to apply formatting logic. Defaults to true.

[Link to heading#](https://www.advancedcustomfields.com/resources/the_sub_field/#examples)

## Examples

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/the_sub_field/#display-a-value-from-within-a-repeater-field)

### Display a value from within a Repeater field.

Link copied

This example shows how to loop through a Repeater field and display a sub field value.

```php
<?php if( have_rows('todo') ): ?>
    <ul>
    <?php while ( have_rows('todo') ) : the_row(); ?>
        <li><?php the_sub_field('item'); ?></li>
    <?php endwhile; ?>
    </ul>
<?php else : ?>
    <p>No todos found.</p>
<?php endif; ?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/the_sub_field/#display-a-value-from-within-a-flexible-content-field)

### Display a value from within a Flexible Content field.

Link copied

This example shows how to loop through a Flexible Content field and generate HTML for different layouts.

```php
<?php if( have_rows('content') ): ?>
    <?php while( have_rows('content') ): the_row(); ?>
        <?php if( get_row_layout() == 'paragraph' ): ?>
            <?php the_sub_field('paragraph'); ?>
        <?php elseif( get_row_layout() == 'quote' ): ?>
            <blockquote>
                <p><?php the_sub_field('quote'); ?></p>
                <footer>—<?php the_sub_field('author'); ?></footer>
            </blockquote>
        <?php endif; ?>
    <?php endwhile; ?>
<?php endif; ?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/the_sub_field/#nested-loops)

### Nested loops

Link copied

This example shows how to loop through a nested Repeater field and display sub field values.

```php
<?php

/**
 * Field Structure:
 *
 * - locations (Repeater)
 *   - title (Text)
 *   - description (Textarea)
 *   - staff_members (Repeater)
 *     - image (Image)
 *     - name (Text)
 */
if( have_rows('locations') ): ?>
    <div class="locations">
    <?php while( have_rows('locations') ): the_row(); ?>
        <div class="location">
            <h3><?php the_sub_field('title'); ?></h3>
            <p><?php the_sub_field('description'); ?></p>
            <?php if( have_rows('staff_members') ): ?>
                <ul class="staff-members">
                <?php while( have_rows('staff_members') ): the_row();
                    $image = get_sub_field('image');
                    ?>
                    <li>
                        <?php echo wp_get_attachment_image( $image['ID'], 'full' ); ?>
                        <h4><?php the_sub_field('name'); ?></h4>
                    </li>
                <?php endwhile; ?>
                </ul>
            <?php endif; ?>
        </div>
    <?php endwhile; ?>
    </div>
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

[Link to heading#](https://www.advancedcustomfields.com/resources/the_sub_field/#related)

## Related

Link copied

- Functions: [get\_sub\_field()](https://www.advancedcustomfields.com/resources/get_sub_field/)
- Functions: [have\_rows()](https://www.advancedcustomfields.com/resources/have_rows/)
- Deprecated: [has\_sub\_field()](https://www.advancedcustomfields.com/resources/has_sub_field/)
- Functions: [get\_row\_layout()](https://www.advancedcustomfields.com/resources/get_row_layout/)
- Functions: [get\_sub\_field\_object()](https://www.advancedcustomfields.com/resources/get_sub_field_object/)

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

[Got it](https://www.advancedcustomfields.com/resources/the_sub_field/#)