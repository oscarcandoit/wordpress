---
url: https://www.advancedcustomfields.com/resources/get-values-from-an-options-page
scraped_at: 2025-10-20T02:23:31.838Z
---

# Get values from an options page

Last updated Jun 30, 2022

[Link to heading#](https://www.advancedcustomfields.com/resources/get-values-from-an-options-page/#overview)

## Overview

Link copied

All the template functions ( [get\_field](https://www.advancedcustomfields.com/resources/get_field/ "get_field()"), [the\_field](https://www.advancedcustomfields.com/resources/the_field/ "the_field()"), [etc](https://www.advancedcustomfields.com/resources/#functions)) can be used to load values from an options page, however, a second parameter is required to target the options page. This is similar to passing through a `$post_id` parameter to target a specific post object.

The `$post_id` parameter needed is a string containing the word ‘option’ or ‘options’.

Please note that although it is possible to create multiple options pages, all values are saved and loaded using ‘option’ as the `$post_id`.

[Link to heading#](https://www.advancedcustomfields.com/resources/get-values-from-an-options-page/#examples)

## Examples

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/get-values-from-an-options-page/#display-a-field)

### Display a field

Link copied

```php
<p><?php the_field('field_name', 'option'); ?></p>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/get-values-from-an-options-page/#retrieve-a-field)

### Retrieve a field

Link copied

```php
<?php

$variable = get_field('field_name', 'option');

// do something with $variable

?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/get-values-from-an-options-page/#display-a-sub-field)

### Display a sub field

Link copied

Note that when inside of a `have_rows` loop, you do not need to use the `$post_id` parameter for any sub field functions ( [get\_sub\_field](https://www.advancedcustomfields.com/resources/get_sub_field/ "get_sub_field()"), [the\_sub\_field](https://www.advancedcustomfields.com/resources/the_sub_field/ "the_sub_field()"))

```php
<?php if( have_rows('repeater_field_name', 'option') ): ?>

    <ul>

    <?php while( have_rows('repeater_field_name', 'option') ) : the_row(); ?>

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

[Link to heading#](https://www.advancedcustomfields.com/resources/get-values-from-an-options-page/#related)

## Related

Link copied

- Guides: [Get Values From a User](https://www.advancedcustomfields.com/resources/how-to-get-values-from-a-user/)
- Guides: [Get values from another post](https://www.advancedcustomfields.com/resources/how-to-get-values-from-another-post/)
- Guides: [Get values from a widget](https://www.advancedcustomfields.com/resources/get-values-widget/)
- Deprecated: [has\_sub\_field()](https://www.advancedcustomfields.com/resources/has_sub_field/)
- Guides: [Sort a Repeater Field](https://www.advancedcustomfields.com/resources/how-to-sorting-a-repeater-field/)

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

[Got it](https://www.advancedcustomfields.com/resources/get-values-from-an-options-page/#)