---
url: https://www.advancedcustomfields.com/resources/get_row_layout
scraped_at: 2025-10-20T02:29:29.702Z
---

# get\_row\_layout()

Last updated Apr 4, 2024

[Link to heading#](https://www.advancedcustomfields.com/resources/get_row_layout/#description)

## Description

Link copied

Returns the current row layout name within a `have_rows()` loop.

This function becomes necessary when displaying values from a Flexible Content field as each row may be of a different layout type.

[Link to heading#](https://www.advancedcustomfields.com/resources/get_row_layout/#return)

## Return

Link copied

_(string)_ The name of the layout as defined in the Flexible Content field settings.

[Link to heading#](https://www.advancedcustomfields.com/resources/get_row_layout/#examples)

## Examples

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/get_row_layout/#basic-usage)

### Basic usage

Link copied

This example shows how to loop through a Flexible Content field and load the row layout for each row.

```php
if( have_rows('content') ) {
    while( have_rows('content') ) {
        the_row();

        // Get the row layout.
        $layout = get_row_layout();

        // Do something...
    }
}
```

[Link to heading#](https://www.advancedcustomfields.com/resources/get_row_layout/#display-layouts)

### Display layouts

Link copied

This example shows how to loop through a Flexible Content field and generate HTML for different layouts.

```php
<?php if( have_rows('content') ): ?>
    <?php while( have_rows('content') ): the_row(); ?>
        <?php

        //Paragraph layout.
        if( get_row_layout() == 'paragraph' ): ?>
            <?php the_sub_field('paragraph'); ?>
        <?php

        // Image layout.
        elseif( get_row_layout() == 'image' ):
            $image = get_sub_field('image');
            ?>
            <figure>
                <?php echo wp_get_attachment_image( $image['ID'], 'full' ); ?>
                <figcaption><?php echo $image['caption']; ?></figcaption>
            </figure>
        <?php

        // Posts.
        elseif( get_row_layout() == 'posts' ):
            $posts = get_sub_field('posts');
            ?>
            <div class="featured-posts">
                <h2><?php the_sub_field('title'); ?></h2>
                <?php the_sub_field('content'); ?>
                <?php if( posts ): ?>
                    <ul>
                    <?php foreach( $posts as $post ):
                        setup_postdata($post); ?>
                        <li><a href="<?php the_permalink(); ?>"><?php the_title(); ?></a></li>
                    <?php endforeach; ?>
                    <?php wp_reset_postdata(); ?>
                    </ul>
                <?php endif; ?>
            </div>
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

[Link to heading#](https://www.advancedcustomfields.com/resources/get_row_layout/#related)

## Related

Link copied

- Deprecated: [the\_flexible\_field()](https://www.advancedcustomfields.com/resources/the_flexible_field/)
- Deprecated: [has\_sub\_field()](https://www.advancedcustomfields.com/resources/has_sub_field/)
- Functions: [the\_sub\_field()](https://www.advancedcustomfields.com/resources/the_sub_field/)
- Functions: [have\_rows()](https://www.advancedcustomfields.com/resources/have_rows/)
- Field Types: [Flexible Content](https://www.advancedcustomfields.com/resources/flexible-content/)

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

[Got it](https://www.advancedcustomfields.com/resources/get_row_layout/#)