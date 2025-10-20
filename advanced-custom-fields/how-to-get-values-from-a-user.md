---
url: https://www.advancedcustomfields.com/resources/how-to-get-values-from-a-user
scraped_at: 2025-10-20T02:26:41.504Z
---

# Get Values From a User

Last updated Aug 25, 2023

[Link to heading#](https://www.advancedcustomfields.com/resources/how-to-get-values-from-a-user/#overview)

## Overview

Link copied

All the template functions ( [get\_field](https://www.advancedcustomfields.com/resources/get_field/ "get_field()"), [the\_field](https://www.advancedcustomfields.com/resources/the_field/ "the_field()"), [etc](https://www.advancedcustomfields.com/resources/#functions)) can be used to load values from a user, with a second parameter required to target the user. This is similar to passing through a `$post_id` parameter to target a specific post object.

The `$post_id` parameter needed is a string containing the word ‘user\_’ and the user’s ID in the format; `"user_{$user_id}"`.

[Link to heading#](https://www.advancedcustomfields.com/resources/how-to-get-values-from-a-user/#examples)

## Examples

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/how-to-get-values-from-a-user/#display-a-field)

### Display a field

Link copied

This example will display a field value from a user with an ID of 1.

```php
<p><?php the_field('field_name', 'user_1'); ?></p>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/how-to-get-values-from-a-user/#retrieving-a-field)

### Retrieving a field

Link copied

This example will retrieve a field value from a user with an ID of 1.

```php
<?php

$variable = get_field('field_name', 'user_1');

// Do something with $variable

?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/how-to-get-values-from-a-user/#working-with-the-repeater-field)

### Working with the Repeater Field

Link copied

Note that when inside of a `have_rows` loop, you do not need to use the `$post_id` parameter for any sub field functions ( [get\_sub\_field](https://www.advancedcustomfields.com/resources/get_sub_field/ "get_sub_field()"), [the\_sub\_field](https://www.advancedcustomfields.com/resources/the_sub_field/ "the_sub_field()"))

```php
<?php if( have_rows('repeater', 'user_1') ): ?>

    <ul>

    <?php while( have_rows('repeater', 'user_1') ): the_row(); ?>

        <li><?php the_sub_field('title'); ?></li>

    <?php endwhile; ?>

    </ul>

<?php endif; ?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/how-to-get-values-from-a-user/#author)

### Author

Link copied

This example will find the author for the current post, and display custom field data from that user.

```php
<?php

$author_id = get_the_author_meta('ID');
$author_badge = get_field('author_badge', 'user_'. $author_id );

?>
<img src="<?php echo esc_url( $author_badge['url'] ); ?>" alt="<?php echo esc_attr( $author_badge['alt'] ); ?>" />
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

[Link to heading#](https://www.advancedcustomfields.com/resources/how-to-get-values-from-a-user/#related)

## Related

Link copied

- Guides: [Get values from an options page](https://www.advancedcustomfields.com/resources/get-values-from-an-options-page/)
- Guides: [Get values from another post](https://www.advancedcustomfields.com/resources/how-to-get-values-from-another-post/)
- Guides: [Get values from a widget](https://www.advancedcustomfields.com/resources/get-values-widget/)
- Deprecated: [has\_sub\_field()](https://www.advancedcustomfields.com/resources/has_sub_field/)
- Getting Started: [Displaying Values in Your Theme](https://www.advancedcustomfields.com/resources/displaying-custom-field-values-in-your-theme/)

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

[Got it](https://www.advancedcustomfields.com/resources/how-to-get-values-from-a-user/#)