---
url: https://www.advancedcustomfields.com/resources/the_flexible_field
scraped_at: 2025-10-20T02:29:33.510Z
---

# the\_flexible\_field()

Last updated Apr 4, 2024

[Link to heading#](https://www.advancedcustomfields.com/resources/the_flexible_field/#description)

## Description

Link copied

_![](https://www.advancedcustomfields.com/wp-content/themes/acf/assets/images/ui-icons/hash.svg)_

This function is deprecated. Please use the [have\_rows()](https://www.advancedcustomfields.com/resources/have_rows/) function instead.

This function is used within a while-loop to loop through each row of a Flexible Content field.

Unlike `have_rows()`, this function will take a step through the available rows each time it is called, causing undesired results when also used within an if-statment.

[Link to heading#](https://www.advancedcustomfields.com/resources/the_flexible_field/#parameters)

## Parameters

Link copied

```php
the_flexible_field( $field_name, $post_id );
```

- `$field_name` _(string)_ _(Required)_ The name of the Flexible Content field to be retrieved. e.g. ‘content’
- `$post_id` _(mixed)_ _(Optional)_ The post ID where the value is saved. Defaults to the current post.

[Link to heading#](https://www.advancedcustomfields.com/resources/the_flexible_field/#return)

## Return

Link copied

_(bool)_ True if a row exists.

[Link to heading#](https://www.advancedcustomfields.com/resources/the_flexible_field/#change-log)

## Change Log

Link copied

- Deprecated in version 3.3.4
- Added in version 3.1.0

[Link to heading#](https://www.advancedcustomfields.com/resources/the_flexible_field/#requirements)

## Requirements

Link copied

- [Flexible Content field Add-on](https://www.advancedcustomfields.com/add-ons/flexible-content-field/) version 1.0.0 or later.

[Link to heading#](https://www.advancedcustomfields.com/resources/the_flexible_field/#example)

## Example

Link copied

This example demonstrates how to loop through a Flexible Content field called “content” and display various layouts.

```php
<?php while( the_flexible_field("content") ): ?>
    <?php if( get_row_layout() == "paragraph" ): ?>
        <div>
            <?php the_sub_field("content"); ?>
        </div>
    <?php elseif( get_row_layout() == "file" ): ?>
        <div>
            <a href="<?php the_sub_field("file"); ?>" ><?php the_sub_field("name"); ?></a>
        </div>
    <?php elseif( get_row_layout() == "featured_posts" ): ?>
        <div>
            <h2><?php the_sub_field("title"); ?></h2>
            <?php the_sub_field("content"); ?>
            <?php if( get_sub_field("posts") ): ?>
                <ul>
                <?php foreach( get_sub_field("posts") as $p ): ?>
                    <li><a href="<?php echo get_permalink($p->ID); ?>"><?php echo get_the_title($p->ID); ?></a></li>
                <?php endforeach; ?>
                </ul>
            <?php endif; ?>
        </div>
    <?php endif; ?>
<?php endwhile; ?>
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

[Link to heading#](https://www.advancedcustomfields.com/resources/the_flexible_field/#related)

## Related

Link copied

- Deprecated: [has\_sub\_field()](https://www.advancedcustomfields.com/resources/has_sub_field/)
- Deprecated: [the\_repeater\_field()](https://www.advancedcustomfields.com/resources/the_repeater_field/)
- Functions: [get\_row\_layout()](https://www.advancedcustomfields.com/resources/get_row_layout/)
- Functions: [have\_rows()](https://www.advancedcustomfields.com/resources/have_rows/)
- Functions: [the\_sub\_field()](https://www.advancedcustomfields.com/resources/the_sub_field/)

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

[Got it](https://www.advancedcustomfields.com/resources/the_flexible_field/#)