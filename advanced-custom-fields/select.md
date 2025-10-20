---
url: https://www.advancedcustomfields.com/resources/select
scraped_at: 2025-10-20T02:33:36.227Z
---

# Select

Last updated May 8, 2025

[Link to heading#](https://www.advancedcustomfields.com/resources/select/#description)

## Description

Link copied

The Select field creates a dropdown list with selectable choices.

[Link to heading#](https://www.advancedcustomfields.com/resources/select/#screenshots)

## Screenshots

Link copied

![Creating a Select field in an ACF field group. ](https://www.advancedcustomfields.com/wp-content/uploads/2023/06/ACF-Select-Field-Settings.png)

Creating a Select field in an ACF field group.

![Settings on the Presentation tab impact how the field will appear to content editors. ](https://www.advancedcustomfields.com/wp-content/uploads/2023/06/ACF-Select-Field-Presentation-Tab.png)

Settings on the Presentation tab impact how the field will appear to content editors.

![An example of how the Select field might appear to content editors.](https://www.advancedcustomfields.com/wp-content/uploads/2013/02/ACF-Select-Field-Content-Editors-2.png)

An example of how the Select field might appear to content editors.

[Link to heading#](https://www.advancedcustomfields.com/resources/select/#changelog)

## Changelog

Link copied

- Added `Return Format` setting in version 5.4.0.
- Added `Stylized UI` (Select2) setting in version 5.0.0.
- Added `Create Options` and `Save Options` settings in version 6.4.1

[Link to heading#](https://www.advancedcustomfields.com/resources/select/#settings)

## Settings

Link copied

- **Choices**


The choices displayed by the Select field. Enter each choice on a new line using the field’s label (eg. `Red`). For more control, you may specify both a value and a label like this: ‘red : Red’.

- **Default Value**


The default value(s) selected when first editing the field’s value. Enter only values, not labels.

- **Return Format**


Specifies the value format returned by ACF functions. Choose from “Value,” “Label”, or “Both (Array)”.

- **Select Multiple Values?**


Allows more than one choice to be selected. If using the “Stylized UI” setting, you may also drag and drop to reorder the selected choices.

- **Required**


Found on the Validation tab, this prevents the field from accepting empty values. Defaults to off.

- **Allow Null**


If selected, the list will begin with an empty choice labeled “- Select -”. If using the “Stylized UI” setting, this choice will be replaced by an ‘x’ icon allowing you to remove the selected value(s).

- **Instructions**


Shows instructions to content editors when submitting data.

- **Stylized UI**


This setting uses the Select2 JavaScript library to enhance your Select field with more functionality, such as search, AJAX, and reordering.

- **AJAX**


This setting appears if using the “Stylized UI” setting. It uses AJAX to [dynamically populate the Select field’s choices](https://www.advancedcustomfields.com/resources/dynamically-populate-a-select-fields-choices/), helping to speed up page loading when using the [acf/load\_field](https://www.advancedcustomfields.com/resources/acf-load_field/) filter.

- **Create Options**


Allow content editors to create new options by typing in the Select input. Multiple options can be created from a comma separated string. Requires the “Select Multiple” and “Stylized UI” settings to be enabled.

- **Save Options**


Save created options back to the “Choices” setting in the field definition. Requires the “Create Options” setting to be enabled.

- **Conditional Logic**


Enabling this setting allows you to customize the logic which determines if the current field should be visible. Groups of conditional logic rules can be created to allow for multiple and/or statements.


[Link to heading#](https://www.advancedcustomfields.com/resources/select/#template-usage)

## Template usage

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/select/#display-single-selected-value)

### Display single selected value

Link copied

This example demonstrates how to load and display a single selected value.

```php
<p>Color: <?php echo esc_html ( get_field('color') ); ?></p>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/select/#display-multiple-values)

### Display multiple values

Link copied

This example demonstrates how to load and display multiple selected values.

```php
<?php
$colors = get_field( 'color' );

// Create a comma-separated list from selected values.
if( $colors ): ?>
<p>Color: <?php echo implode( ', ', $colors ); ?></p>
<?php endif; ?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/select/#display-value-and-label)

### Display value and label

Link copied

This example demonstrates how to load a selected value and label without using the “Return Format” setting.

```php
<?php
$field = get_field_object( 'color' );
$value = $field['value'];
$label = $field['choices'][ $value ];
?>
<p>Color: <span class="color-<?php echo esc_attr($value); ?>"><?php echo esc_html($label); ?></span></p>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/select/#load-value-and-label-with-return-format)

### Load value and label with Return Format

Link copied

This example demonstrates how to load a selected value and label using the “Return Format” setting, in this case set to “Both (Array)”.

```php
<?php
$color = get_field( 'color' );
?>
<p>Color: <span class="color-<?php echo esc_attr($color['value']); ?>"><?php echo esc_html($color['label']); ?></span></p>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/select/#conditional)

### Conditional

Link copied

This example demonstrates how to use a selected value to conditionally perform a task. In this case, the conditional is checking to see if `red` matches the selected option.

```php
<?php

if( get_field('color') == 'red' ) {
    // Do something.
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

[Link to heading#](https://www.advancedcustomfields.com/resources/select/#related)

## Related

Link copied

- Basic: [Text](https://www.advancedcustomfields.com/resources/text/)
- Choice: [Radio Button](https://www.advancedcustomfields.com/resources/radio-button/)
- Choice: [Button Group](https://www.advancedcustomfields.com/resources/button-group/)
- Choice: [Checkbox](https://www.advancedcustomfields.com/resources/checkbox/)
- Field Types: [Post Object](https://www.advancedcustomfields.com/resources/post-object/)

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

[Got it](https://www.advancedcustomfields.com/resources/select/#)