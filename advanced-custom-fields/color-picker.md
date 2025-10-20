---
url: https://www.advancedcustomfields.com/resources/color-picker
scraped_at: 2025-10-20T02:34:02.053Z
---

# Color Picker

Last updated Oct 7, 2025

[Link to heading#](https://www.advancedcustomfields.com/resources/color-picker/#description)

## Description

Link copied

The Color Picker field provides an interactive way to select a hex color string using [Iris](https://automattic.github.io/Iris/).

[Link to heading#](https://www.advancedcustomfields.com/resources/color-picker/#screenshots)

## Screenshots

Link copied

[![acf-user-field-interface](https://www.advancedcustomfields.com/wp-content/uploads/2013/02/acf-color-picker-interface.png)](https://www.advancedcustomfields.com/wp-content/uploads/2013/02/acf-color-picker-interface.png) The Color Picker editor field interface[![acf-user-field-settings](https://www.advancedcustomfields.com/wp-content/uploads/2013/02/acf-color-picker-settings.png)](https://www.advancedcustomfields.com/wp-content/uploads/2013/02/acf-color-picker-settings.png) The Color Picker editor field settings

[Link to heading#](https://www.advancedcustomfields.com/resources/color-picker/#settings)

## Settings

Link copied

- **Default Value**
The default value initially loaded into the Color Picker when first editing the field’s value.
- **Enable Transparency**


Enable transparency control on the color picker. If enabled the Return format options switch to RGBA string or RGBA array.
- **Custom Palette**
Define the available colors shown with the field. It accepts a comma-separated list of hex codes. Each hex code will be a default color shown in the palette. This setting can be found under the “Presentation” tab for the field settings.
- **Use colors from theme.json**
If your theme contains a theme.json file, the colors defined there can be used as the color palette. To use this option, enable “Custom Palette”, ensure you have a supported theme, and choose “Use colors from theme.json”
- **Show Color Wheel**
Set whether the Color Wheel should be shown or hidden. When hidden, only the color palette will be shown, along with the text field where the actual value is defined. This setting can be found under the “Presentation” tab for the field settings.

[Link to heading#](https://www.advancedcustomfields.com/resources/color-picker/#template-usage)

## Template usage

Link copied

The Color Picker field will return a string value containing the HEX color value including the prefix ‘#’. Below are examples using a Color Picker field named “color”.

[Link to heading#](https://www.advancedcustomfields.com/resources/color-picker/#display-value-within-inline-styles)

### Display value within inline styles

Link copied

This example demonstrates how to generate an inline style using a Color Picker value.

```php
<div style="background-color:<?php the_field('color'); ?>">

</div>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/color-picker/#display-value-within-style-tags)

### Display value within style tags

Link copied

This example demonstrates how to generate a CSS class using a Color Picker value.

```php
<style type="text/css">
.primary-background {
    background-color: <?php the_field('primary_background_color'); ?>;
}
</style>

<div class="primary-background">

</div>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/color-picker/#notes)

## Notes

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/color-picker/#customization)

### Customization

Link copied

The Color picker field modal can be customized via the JS filter [color\_picker\_args](https://www.advancedcustomfields.com/resources/javascript-api/#filters-color_picker_args).

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

[Link to heading#](https://www.advancedcustomfields.com/resources/color-picker/#related)

## Related

Link copied

- Choice: [Radio Button](https://www.advancedcustomfields.com/resources/radio-button/)
- Choice: [Checkbox](https://www.advancedcustomfields.com/resources/checkbox/)
- Choice: [Button Group](https://www.advancedcustomfields.com/resources/button-group/)
- Field Types: [Time Picker](https://www.advancedcustomfields.com/resources/time-picker/)
- Field Types: [Date Picker](https://www.advancedcustomfields.com/resources/date-picker/)

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

[Got it](https://www.advancedcustomfields.com/resources/color-picker/#)