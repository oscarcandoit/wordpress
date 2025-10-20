---
url: https://www.advancedcustomfields.com/resources/hiding-empty-fields
scraped_at: 2025-10-20T02:16:16.682Z
---

# Hiding empty fields

Last updated Sep 10, 2013

[Link to heading#](https://www.advancedcustomfields.com/resources/hiding-empty-fields/#overview)

## Overview

Link copied

It is a common task to hide empty field values from your template. This can be achieved by using conditional statements to check the value before rending it.

The basics to conditional a statement is to use an _if_ statement. You can read more about this core PHP function here: [http://php.net/manual/en/control-structures.if.php](http://php.net/manual/en/control-structures.if.php)

[Link to heading#](https://www.advancedcustomfields.com/resources/hiding-empty-fields/#examples)

## Examples

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/hiding-empty-fields/#example-1-basic)

### Example 1: Basic

Link copied

This example shows how to check for a value before displaying it. Please note the use of both [get\_field()](https://www.advancedcustomfields.com/resources/functions/get_field/ "get_field()") and [the\_field()](https://www.advancedcustomfields.com/resources/functions/the_field/ "the_field()").

```php
<?php if( get_field('field_name') ): ?>
    <p>My field value: <?php the_field('field_name'); ?></p>
<?php endif; ?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/hiding-empty-fields/#example-2-loop)

### Example 2: Loop

Link copied

This example shows how the above methodology can be used within a loop. Please note the use of [get\_field\_objects()](https://www.advancedcustomfields.com/resources/functions/get_field_objects/ "get_field_objects()") to load the array.

```php
<?php

$fields = get_field_objects();

<?php if( $fields ): ?>
    <ul>
    <?php foreach( $fields as $field ): ?>

        <?php if( $field['value'] ): ?>
            <li><?php echo $field['label']; ?>: <?php echo $field['value']; ?></li>
        <?php endif; ?>

    <?php endforeach; ?>
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

[Link to heading#](https://www.advancedcustomfields.com/resources/hiding-empty-fields/#related)

## Related

Link copied

- Getting Started: [Code Examples](https://www.advancedcustomfields.com/resources/code-examples/)
- Functions: [the\_sub\_field()](https://www.advancedcustomfields.com/resources/the_sub_field/)
- Guides: [Get Values From a User](https://www.advancedcustomfields.com/resources/how-to-get-values-from-a-user/)
- Choice: [Checkbox](https://www.advancedcustomfields.com/resources/checkbox/)
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

[Got it](https://www.advancedcustomfields.com/resources/hiding-empty-fields/#)