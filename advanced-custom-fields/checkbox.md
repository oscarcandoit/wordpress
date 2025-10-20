---
url: https://www.advancedcustomfields.com/resources/checkbox
scraped_at: 2025-10-20T02:25:44.087Z
---

# Checkbox

Last updated Jun 5, 2023

[Link to heading#](https://www.advancedcustomfields.com/resources/checkbox/#description)

## Description

Link copied

The Checkbox field creates a list of check-able inputs.

[Link to heading#](https://www.advancedcustomfields.com/resources/checkbox/#screenshots)

## Screenshots

Link copied

[![A Checkbox field with a list of options that allows you to check off one or multiple choices](https://www.advancedcustomfields.com/wp-content/uploads/2013/02/acf-checkbox-field-interface.png)](https://www.advancedcustomfields.com/wp-content/uploads/2013/02/acf-checkbox-field-interface.png) The Checkbox field interface[![List of checkbox field settings shown when setting up a Checkbox field](https://www.advancedcustomfields.com/wp-content/uploads/2013/02/acf-checkbox-field-settings-1.png)](https://www.advancedcustomfields.com/wp-content/uploads/2013/02/acf-checkbox-field-settings-1.png) The Checkbox field settings

[Link to heading#](https://www.advancedcustomfields.com/resources/checkbox/#changelog)

## Changelog

Link copied

- Added `Return Format` setting in version 5.4.0.
- Added `Toggle All` setting in version 5.2.7.

[Link to heading#](https://www.advancedcustomfields.com/resources/checkbox/#settings)

## Settings

Link copied

- **Choices**


The choices displayed when selecting a value. Enter each choice on a new line (eg. `Red`). For more control over the value and label, you may use a colon to specify both (eg. `red : Red`).

- **Default Value**


The default values selected when first editing the field’s value. Enter only values, not labels.

- **Layout**


The layout orientation of checkbox inputs. Select from “Vertical” or “Horizontal”.

- **Toggle**


Prepends an extra checkbox to toggle on/off all inputs.

- **Return Format**


Specifies the value format returned by ACF functions. Select from “Value”, “Label” or “Both”.

- **Allow Custom**


Appends a button that allows custom values to be added when editing the field’s value.

- **Save Custom**


Allows custom values to be saved back into the field’s choices. See Notes for more information.


[Link to heading#](https://www.advancedcustomfields.com/resources/checkbox/#template-usage)

## Template usage

Link copied

The checkbox field returns an array of selected choices.

[Link to heading#](https://www.advancedcustomfields.com/resources/checkbox/#display-value)

### Display value

Link copied

This example demonstrates how to display the selected values in a comma-delimited list.

```php
<p>Colors: <?php the_field('colors'); ?></p>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/checkbox/#display-values-in-a-list)

### Display values in a list

Link copied

This example demonstrates how to display the selected values in an unordered list.

```php
<?php
$colors = get_field('colors');
if( $colors ): ?>
<ul>
    <?php foreach( $colors as $color ): ?>
        <li><?php echo $color; ?></li>
    <?php endforeach; ?>
</ul>
<?php endif; ?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/checkbox/#display-labels-in-a-list)

### Display labels in a list

Link copied

This example demonstrates how to display the selected labels in an unordered list when _Return Format_ is set to `Value`.

```php
<?php

// Load field settings and values.
$field = get_field_object('colors');
$colors = $field['value'];

// Display labels.
if( $colors ): ?>
<ul>
    <?php foreach( $colors as $color ): ?>
        <li><?php echo $field['choices'][ $color ]; ?></li>
    <?php endforeach; ?>
</ul>
<?php endif; ?>
```

This example demonstrates how to display the selected labels in an unordered list when _Return Format_ is set to `Both`.

```php
<?php
$colors = get_field('colors');
if( $colors ): ?>
<ul>
    <?php foreach( $colors as $color ): ?>
        <li><span class="color-<?php echo $color['value']; ?>"><?php echo $color['label']; ?></span></li>
    <?php endforeach; ?>
</ul>
<?php endif; ?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/checkbox/#conditional-logic)

### Conditional logic

Link copied

This example demonstrates how to check if the choice “red” was selected in the field’s value.

```php
$colors = get_field('colors');
if( $colors && in_array('red', $colors) ) {
    // Do something.
}
```

[Link to heading#](https://www.advancedcustomfields.com/resources/checkbox/#query-posts)

### Query posts

Link copied

This example demonstrates how to query posts that contain a checkbox field named “colors” with the value “red” selected. Because the checkbox field saves its value as a serialized array, it is important to use the meta\_query “LIKE” comparison.

```php
$posts = get_posts(array(
    'meta_query' => array(
        array(
            'key'     => 'colors',
            'value'   => '"red"',
            'compare' => 'LIKE'
        )
    )
));

if( $posts ) {
    // Do something.
}
```

[Link to heading#](https://www.advancedcustomfields.com/resources/checkbox/#notes)

## Notes

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/checkbox/#save-custom)

### Save custom

Link copied

If using the [local JSON](https://www.advancedcustomfields.com/resources/local-json/) feature, any custom values saved to the field’s choices will not appear on page reload. This is because the JSON file will not be updated and will override any field settings found in the database.

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

[Link to heading#](https://www.advancedcustomfields.com/resources/checkbox/#related)

## Related

Link copied

- Choice: [Radio Button](https://www.advancedcustomfields.com/resources/radio-button/)
- Choice: [Button Group](https://www.advancedcustomfields.com/resources/button-group/)
- Choice: [Select](https://www.advancedcustomfields.com/resources/select/)
- Choice: [True / False](https://www.advancedcustomfields.com/resources/true-false/)
- Field Types: [Taxonomy](https://www.advancedcustomfields.com/resources/taxonomy/)

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

[Got it](https://www.advancedcustomfields.com/resources/checkbox/#)