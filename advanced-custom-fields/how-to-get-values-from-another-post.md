---
url: https://www.advancedcustomfields.com/resources/how-to-get-values-from-another-post
scraped_at: 2025-10-20T02:17:08.502Z
---

# Get values from another post

Last updated Jul 7, 2017

[Link to heading#](https://www.advancedcustomfields.com/resources/how-to-get-values-from-another-post/#overview)

## Overview

Link copied

All the template functions ( [get\_field](https://www.advancedcustomfields.com/resources/get_field/ "get_field()"), [the\_field](https://www.advancedcustomfields.com/resources/the_field/ "the_field()"), [etc](https://www.advancedcustomfields.com/resources/#functions)) can be used to load values from another post, however, a second parameter is required to target the post.

Each post has a unique ID which can be found in the URL when editing, or found via code such as `$post->ID`.

[Link to heading#](https://www.advancedcustomfields.com/resources/how-to-get-values-from-another-post/#examples)

## Examples

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/how-to-get-values-from-another-post/#display-a-field)

### Display a field

Link copied

This example will display a field value from the post with an ID of 123.

```php
<p><?php the_field('field_name', 123); ?></p>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/how-to-get-values-from-another-post/#retrieving-a-field)

### Retrieving a field

Link copied

This example will retrieve a field value from the post with an ID of 123.

```php
<?php

$variable = get_field('field_name', 123);

// do something with $variable

?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/how-to-get-values-from-another-post/#retrieving-a-field-from-post-object)

### Retrieving a field from post object

Link copied

This example will retrieve a field value from a previously found `$post` object.

```php
<?php

$variable = get_field('field_name', $post->ID);

// do something with $variable

?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/how-to-get-values-from-another-post/#working-with-the-repeater-field)

### Working with the Repeater Field

Link copied

Note that when inside of a `have_rows` loop, you do not need to use the `$post_id` parameter for any sub field functions ( [get\_sub\_field](https://www.advancedcustomfields.com/resources/get_sub_field/ "get_sub_field()"), [the\_sub\_field](https://www.advancedcustomfields.com/resources/the_sub_field/ "the_sub_field()"))

```php
<?php if( have_rows('repeater', 123) ): ?>

    <ul>

    <?php while( have_rows('repeater', 123) ): the_row(); ?>

        <li><?php the_sub_field('title'); ?></li>

    <?php endwhile; ?>

    </ul>

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

[Link to heading#](https://www.advancedcustomfields.com/resources/how-to-get-values-from-another-post/#related)

## Related

Link copied

- Guides: [Get Values From a User](https://www.advancedcustomfields.com/resources/how-to-get-values-from-a-user/)
- Guides: [Get values from an options page](https://www.advancedcustomfields.com/resources/get-values-from-an-options-page/)
- Functions: [have\_rows()](https://www.advancedcustomfields.com/resources/have_rows/)
- Functions: [the\_sub\_field()](https://www.advancedcustomfields.com/resources/the_sub_field/)
- Getting Started: [Code Examples](https://www.advancedcustomfields.com/resources/code-examples/)

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

[Got it](https://www.advancedcustomfields.com/resources/how-to-get-values-from-another-post/#)