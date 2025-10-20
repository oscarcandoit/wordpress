---
url: https://www.advancedcustomfields.com/resources/range
scraped_at: 2025-10-20T02:24:23.025Z
---

# Range

Last updated Mar 30, 2023

[Link to heading#](https://www.advancedcustomfields.com/resources/range/#description)

## Description

Link copied

The Range field provides an interactive experience for selecting a numerical value between specific endpoints.

[Link to heading#](https://www.advancedcustomfields.com/resources/range/#screenshots)

## Screenshots

Link copied

[![Range field that allows you to select a numerical value between two points](https://www.advancedcustomfields.com/wp-content/uploads/2017/09/acf-range-field-interface.png)](https://www.advancedcustomfields.com/wp-content/uploads/2017/09/acf-range-field-interface.png) The Range field interface[![List of settings shown when creating a Range field](https://www.advancedcustomfields.com/wp-content/uploads/2017/09/acf-range-field-settings-1.png)](https://www.advancedcustomfields.com/wp-content/uploads/2017/09/acf-range-field-settings-1.png) The Range field settings

[Link to heading#](https://www.advancedcustomfields.com/resources/range/#changelog)

## Changelog

Link copied

- Added in version 5.6.2.

[Link to heading#](https://www.advancedcustomfields.com/resources/range/#settings)

## Settings

Link copied

- **Default Value**
The default value loaded when editing a new post (when no value exists).

- **Minimum Value**
The minimum (numeric) value allowed. Defaults to 0.

- **Maximum Value**
The maximum (numeric) value allowed. Defaults to 100.

- **Step Size**
The increment at which a numeric value can be set. Defaults to 1.

- **Prepend**
HTML displayed before (to the left) of the range input.

- **Append**
HTML displayed after (to the right) of the range input.


[Link to heading#](https://www.advancedcustomfields.com/resources/range/#template-usage)

## Template usage

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/range/#display-value-within-css)

### Display value within CSS

Link copied

This example demonstrates how a Range field value can be used to control the font-size of all `<h2>` elements.

```php
<?php

$h2_font_size = get_field('h2_font_size');
if( $h2_font_size ): ?>
<style type="text/css">
    h2 {
        font-size: <?php echo $h2_font_size; ?>px;
    }
</style>
<?php endif; ?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/range/#display-value-as-text)

### Display value as text.

Link copied

This example demonstrates how to display a Range field value as text.

```php
<p>Searching for houses within a <?php the_field('search_radius'); ?>km radius.</p>
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

[Link to heading#](https://www.advancedcustomfields.com/resources/range/#related)

## Related

Link copied

- Basic: [Number](https://www.advancedcustomfields.com/resources/number/)
- Content: [Image](https://www.advancedcustomfields.com/resources/image/)
- Choice: [Button Group](https://www.advancedcustomfields.com/resources/button-group/)
- Choice: [Radio Button](https://www.advancedcustomfields.com/resources/radio-button/)
- Field Types: [Page Link](https://www.advancedcustomfields.com/resources/page-link/)

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

[Got it](https://www.advancedcustomfields.com/resources/range/#)