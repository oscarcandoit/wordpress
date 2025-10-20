---
url: https://www.advancedcustomfields.com/resources/button-group
scraped_at: 2025-10-20T02:18:30.815Z
---

# Button Group

Last updated Feb 17, 2022

[Link to heading#](https://www.advancedcustomfields.com/resources/button-group/#description)

## Description

Link copied

The Button Group field provides a neat UI for selecting a value.

[Link to heading#](https://www.advancedcustomfields.com/resources/button-group/#screenshots)

## Screenshots

Link copied

[![Three examples of button group field controlling alignment, and colors of buttons](https://www.advancedcustomfields.com/wp-content/uploads/2017/10/acf-button-group-field-interface.png)](https://www.advancedcustomfields.com/wp-content/uploads/2017/10/acf-button-group-field-interface.png) The Button Group field interface[![List of field settings shown when setting up a Button Group field](https://www.advancedcustomfields.com/wp-content/uploads/2017/10/acf-button-group-field-settings-1.png)](https://www.advancedcustomfields.com/wp-content/uploads/2017/10/acf-button-group-field-settings-1.png) The Button Group field settings

[Link to heading#](https://www.advancedcustomfields.com/resources/button-group/#changelog)

## Changelog

Link copied

- Added in version 5.6.3.

[Link to heading#](https://www.advancedcustomfields.com/resources/button-group/#settings)

## Settings

Link copied

- **Choices**


The choices displayed when selecting a value. Enter each choice on a new line (eg. `Red`). For more control over the value and label, you may use a colon to specify both (eg. `red : Red`). You may also enter HTML as a choice as shown in the above screenshots.

- **Allow Null**


Allows no value to be selected.

- **Default Value**


The default values selected when first editing the field’s value. Enter only values, not labels.

- **Layout**


The layout orientation of the inputs. Select from "Vertical" or "Horizontal".

- **Return Format**


Specifies the value format returned by ACF functions. Select from "Value", "Label" or "Both".


[Link to heading#](https://www.advancedcustomfields.com/resources/button-group/#template-usage)

## Template usage

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/button-group/#display-value)

### Display value

Link copied

This example demonstrates how to display the selected value using the _Return Format_ setting `Value`.

```php
<p>Color: <?php the_field('color'); ?></p>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/button-group/#display-value-and-label)

### Display value and label

Link copied

This example demonstrates how to display the selected value and label using the _Return Format_ setting `Both`.

```php
<?php
$color = get_field('color');
?>
<p>Color: <span class="color-<?php echo esc_attr($color['value']); ?>"><?php echo esc_html($color['label']); ?></span></p>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/button-group/#conditional)

### Conditional

Link copied

This example demonstrates how to use a selected value to conditionally perform a task.

```php
<?php

if( get_field('color') == 'red' ) {
    // Do something.
}
```

[Link to heading#](https://www.advancedcustomfields.com/resources/button-group/#query-posts)

### Query Posts

Link copied

This example demonstrates how to query posts that have a ‘red’ value for the field ‘color’.

```php
<?php

$posts = get_posts( array(
    'meta_query' => array(
        array(
            'key'   => 'color',
            'value' => 'red',
        )
    )
) );

if( $posts ) {
    foreach( $posts as $post ) {
        // Do something.
    }
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

[Link to heading#](https://www.advancedcustomfields.com/resources/button-group/#related)

## Related

Link copied

- Choice: [Radio Button](https://www.advancedcustomfields.com/resources/radio-button/)
- Choice: [Checkbox](https://www.advancedcustomfields.com/resources/checkbox/)
- Field Types: [User](https://www.advancedcustomfields.com/resources/user/)
- Field Types: [Taxonomy](https://www.advancedcustomfields.com/resources/taxonomy/)
- Choice: [Select](https://www.advancedcustomfields.com/resources/select/)

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

[Got it](https://www.advancedcustomfields.com/resources/button-group/#)