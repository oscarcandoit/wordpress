---
url: https://www.advancedcustomfields.com/resources/the_repeater_field
scraped_at: 2025-10-20T02:23:57.252Z
---

# the\_repeater\_field()

Last updated Oct 19, 2022

[Link to heading#](https://www.advancedcustomfields.com/resources/the_repeater_field/#description)

## Description

Link copied

_![](https://www.advancedcustomfields.com/wp-content/themes/acf/assets/images/ui-icons/hash.svg)_

This function is deprecated. Please use the [have\_rows()](https://www.advancedcustomfields.com/resources/have_rows/) function instead.

This function is used within a while-loop to loop through each row of a repeater field.

Unlike `have_rows()`, this function will take a step through the available rows each time it is called, causing undesired results when also used within an if-statment.

[Link to heading#](https://www.advancedcustomfields.com/resources/the_repeater_field/#parameters)

## Parameters

Link copied

```php
the_repeater_field( $field_name, $post_id );
```

- `$field_name` _(string)_ _(Required)_ The name of the Repeater field to be retrieved. e.g. ‘gallery\_images’
- `$post_id` _(mixed)_ _(Optional)_ The post ID where the value is saved. Defaults to the current post.

[Link to heading#](https://www.advancedcustomfields.com/resources/the_repeater_field/#return)

## Return

Link copied

_(bool)_ True if a row exists.

[Link to heading#](https://www.advancedcustomfields.com/resources/the_repeater_field/#change-log)

## Change Log

Link copied

- Deprecated in version 3.3.4
- Added in version 2.0.3

[Link to heading#](https://www.advancedcustomfields.com/resources/the_repeater_field/#requirements)

## Requirements

Link copied

- [Repeater field Add-on](https://www.advancedcustomfields.com/add-ons/repeater-field/) version 1.0.0 or later.

[Link to heading#](https://www.advancedcustomfields.com/resources/the_repeater_field/#examples)

## Examples

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/the_repeater_field/#loop-through-repeater-field)

### Loop through Repeater field

Link copied

This example demonstrates how to loop through a repeater field called “gallery\_images”.

```php
<?php if( get_field('gallery_images') ): ?>
    <?php while( the_repeater_field('gallery_images') ): ?>
        <img src="<?php the_sub_field('image'); ?>" alt="<?php the_sub_field('alt'); ?>" />
    <?php endwhile; ?>
 <?php endif; ?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/the_repeater_field/#loop-through-repeater-field-from-another-post)

### Loop through Repeater field from another post

Link copied

This example demonstrates looping through a Repeater field from a different post with the ID of 123.

_Note:_ You don’t need to specify the `$post_id` for any sub field functions.

```php
<?php
if( get_field('repeater_field_name', 123) ) {
    echo '<ul>';
    while( the_repeater_field('repeater_field_name', 123) ) {
        echo '<li>sub_field_1 = ' . get_sub_field('sub_field_1') . ', sub_field_2 = ' . get_sub_field('sub_field_2') .', etc</li>';
    }
    echo '</ul>';
}
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

[Link to heading#](https://www.advancedcustomfields.com/resources/the_repeater_field/#related)

## Related

Link copied

- Deprecated: [has\_sub\_field()](https://www.advancedcustomfields.com/resources/has_sub_field/)
- Deprecated: [the\_flexible\_field()](https://www.advancedcustomfields.com/resources/the_flexible_field/)
- Functions: [have\_rows()](https://www.advancedcustomfields.com/resources/have_rows/)
- Guides: [Get Values From a User](https://www.advancedcustomfields.com/resources/how-to-get-values-from-a-user/)
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

[Got it](https://www.advancedcustomfields.com/resources/the_repeater_field/#)