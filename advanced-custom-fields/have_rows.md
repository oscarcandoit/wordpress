---
url: https://www.advancedcustomfields.com/resources/have_rows
scraped_at: 2025-10-20T02:22:55.212Z
---

# have\_rows()

Last updated Feb 17, 2022

[Link to heading#](https://www.advancedcustomfields.com/resources/have_rows/#description)

## Description

Link copied

This function checks to see if a parent field (such as Repeater or Flexible Content) has any rows of data to loop over. This is a boolean function, meaning it returns either `true` or `false`.

This function is intended to be used in conjunction with `the_row()` to step through available values.

Using `have_rows()` together with `the_row()` is intended to feel native much like the [have\_posts()](https://codex.wordpress.org/Function_Reference/have_posts/) and [the\_post()](https://developer.wordpress.org/reference/functions/the_post/) WordPress functions.

[Link to heading#](https://www.advancedcustomfields.com/resources/have_rows/#parameters)

## Parameters

Link copied

```php
have_rows( $selector, [$post_id = false] );
```

- `$selector` _(string)_ _(Required)_ The field name or field key.
- `$post_id` _(mixed)_ _(Optional)_ The post ID where the value is saved. Defaults to the current post.

[Link to heading#](https://www.advancedcustomfields.com/resources/have_rows/#return)

## Return

Link copied

_(bool)_ True if a row exists.

[Link to heading#](https://www.advancedcustomfields.com/resources/have_rows/#changelog)

## Changelog

Link copied

- Added in version 4.3.0

[Link to heading#](https://www.advancedcustomfields.com/resources/have_rows/#examples)

## Examples

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/have_rows/#basic-loop)

### Basic loop

Link copied

This example shows how to loop through a repeater field called "parent\_field" and load a sub field value.

```php
if( have_rows('parent_field') ):
    while ( have_rows('parent_field') ) : the_row();
        $sub_value = get_sub_field('sub_field');
        // Do something...
    endwhile;
else :
    // no rows found
endif;
```

[Link to heading#](https://www.advancedcustomfields.com/resources/have_rows/#display-a-slider)

### Display a slider.

Link copied

This example shows how to loop through a repeater field and generate HTML for a basic image slider.

```php
<?php if( have_rows('slides') ): ?>
    <ul class="slides">
    <?php while( have_rows('slides') ): the_row();
        $image = get_sub_field('image');
        ?>
        <li>
            <?php echo wp_get_attachment_image( $image, 'full' ); ?>
            <p><?php the_sub_field('caption'); ?></p>
        </li>
    <?php endwhile; ?>
    </ul>
<?php endif; ?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/have_rows/#display-layouts)

### Display layouts.

Link copied

This example shows how to loop through a Flexible Content field and generate HTML for different layouts.

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

[Link to heading#](https://www.advancedcustomfields.com/resources/have_rows/#nested-loops)

### Nested loops

Link copied

This example shows how to loop through a nested Repeater field.

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

[Link to heading#](https://www.advancedcustomfields.com/resources/have_rows/#notes)

## Notes

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/have_rows/#infinite-loops)

### Infinite Loops

Link copied

Because the `have_rows()` function does not step through each row by itself, using this function without `the_row()` will create an infinite loop resulting in a white screen.

[Link to heading#](https://www.advancedcustomfields.com/resources/have_rows/#scope)

### Scope

Link copied

The scope of a `have_rows()` loop is limited to the current row. This means that any sub field function such as `get_sub_field()` or `the_sub_field()` will only find data from the current row, not from parent or child rows.

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

[Link to heading#](https://www.advancedcustomfields.com/resources/have_rows/#related)

## Related

Link copied

- Functions: [the\_sub\_field()](https://www.advancedcustomfields.com/resources/the_sub_field/)
- Deprecated: [has\_sub\_field()](https://www.advancedcustomfields.com/resources/has_sub_field/)
- Functions: [get\_row()](https://www.advancedcustomfields.com/resources/get_row/)
- Functions: [get\_row\_layout()](https://www.advancedcustomfields.com/resources/get_row_layout/)
- Functions: [get\_sub\_field()](https://www.advancedcustomfields.com/resources/get_sub_field/)

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

[Got it](https://www.advancedcustomfields.com/resources/have_rows/#)