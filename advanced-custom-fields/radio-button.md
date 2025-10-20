---
url: https://www.advancedcustomfields.com/resources/radio-button
scraped_at: 2025-10-20T02:18:50.270Z
---

# Radio Button

Last updated Feb 17, 2022

[Link to heading#](https://www.advancedcustomfields.com/resources/radio-button/#description)

## Description

Link copied

The Radio Button field creates a list of select-able inputs.

[Link to heading#](https://www.advancedcustomfields.com/resources/radio-button/#screenshots)

## Screenshots

Link copied

[![Radio button field that allows you to select option(s)](https://www.advancedcustomfields.com/wp-content/uploads/2016/09/acf-radio-button-field-interface.png)](https://www.advancedcustomfields.com/wp-content/uploads/2016/09/acf-radio-button-field-interface.png) The Radio Button field interface[![List of settings shown when creating a Radio button field](https://www.advancedcustomfields.com/wp-content/uploads/2016/09/acf-radio-button-field-settings-1.png)](https://www.advancedcustomfields.com/wp-content/uploads/2016/09/acf-radio-button-field-settings-1.png) The Radio Button field settings

[Link to heading#](https://www.advancedcustomfields.com/resources/radio-button/#changelog)

## Changelog

Link copied

- Added `Return Format` setting in version 5.4.0.
- Added `Allow Null` setting in version 5.3.8.
- Added `Other` and ‘Save Other’ settings in version 4.1.7.

[Link to heading#](https://www.advancedcustomfields.com/resources/radio-button/#settings)

## Settings

Link copied

- **Choices**


The choices displayed when selecting a value. Enter each choice on a new line (eg. `Red`). For more control over the value and label, you may use a colon to specify both (eg. `red : Red`).

- **Allow Null**


Allows the ability to ‘un-select’ a selected value.

- **Other**


Adds a text input allowing for a custom value to be entered.

- **Save Other**


Allows custom values to be appended to the field’s choices. See Notes for more information.

- **Default Value**


Specifies the default value selected when first editing the field’s value. Enter only value (not label).

- **Layout**


The layout orientation of radio inputs. Select from "Vertical" to "Horizontal".

- **Return Format**


Specifies the value format returned by ACF functions. Select from Value, Label or Both (array).


[Link to heading#](https://www.advancedcustomfields.com/resources/radio-button/#template-usage)

## Template usage

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/radio-button/#display-a-single-selected-value)

### Display a single selected value

Link copied

This example demonstrates how to display the selected value.

```php
<p>Color: <?php the_field('color'); ?></p>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/radio-button/#display-value-and-label)

### Display value and label

Link copied

This example demonstrates how to load a selected value and label without using the _Format value_ setting.

```php
<?php
$field = get_field_object('color');
$value = $field['value'];
$label = $field['choices'][ $value ];

?>
<p>Color: <span class="color-<?php echo esc_attr($value); ?>"><?php echo esc_html($label); ?></span></p>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/radio-button/#format-value-setting)

### Format value setting

Link copied

This example demonstrates how to load a selected value and label using the _Format value_ setting (set to `Both`).

```php
<?php
$color = get_field('color');
?>
<p>Color: <span class="color-<?php echo esc_attr($color['value']); ?>"><?php echo esc_html($color['label']); ?></span></p>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/radio-button/#conditional)

### Conditional

Link copied

This example demonstrates how to use a selected value to conditionally perform a task.

```php
<?php

if( get_field('color') == 'red' ) {
    // Do something.
}
```

[Link to heading#](https://www.advancedcustomfields.com/resources/radio-button/#query-posts)

### Query posts

Link copied

This example demonstrates how to query posts that have the value ‘red’ selected for a radio button field named ‘color’.

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
    // Do something.
}
```

[Link to heading#](https://www.advancedcustomfields.com/resources/radio-button/#notes)

## Notes

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/radio-button/#save-other)

### Save other

Link copied

If using the [local JSON](https://www.advancedcustomfields.com/resources/local-json/) feature, any custom values saved to the field’s choices will not appear on page reload. This is because the JSON file will not be updated and will override any field settings found in the DB.

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

[Link to heading#](https://www.advancedcustomfields.com/resources/radio-button/#related)

## Related

Link copied

- Choice: [Button Group](https://www.advancedcustomfields.com/resources/button-group/)
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

[Got it](https://www.advancedcustomfields.com/resources/radio-button/#)