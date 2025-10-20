---
url: https://www.advancedcustomfields.com/resources/number
scraped_at: 2025-10-20T02:24:32.635Z
---

# Number

Last updated Mar 31, 2023

[Link to heading#](https://www.advancedcustomfields.com/resources/number/#description)

## Description

Link copied

The Number field creates an input limited to numerical values.

[Link to heading#](https://www.advancedcustomfields.com/resources/number/#screenshots)

## Screenshots

Link copied

![Creating a Number field. ](https://www.advancedcustomfields.com/wp-content/uploads/2023/03/Creating-a-Number-Field.png)

Creating a Number field.

![The Presentation tab of the Number field allows you to provide instructions to content editors, show placeholder text, set step size (increments), add characters before and after the input, and define wrapper attributes. ](https://www.advancedcustomfields.com/wp-content/uploads/2023/03/Number-Field-Presentation-Layer.png)

The Presentation tab of the Number field allows you to provide instructions to content editors, show placeholder text, set step size (increments), add characters before and after the input, and define wrapper attributes.

![How the Number field is displayed to content editors in WP Admin.](https://www.advancedcustomfields.com/wp-content/uploads/2023/03/Number-Field-for-Content-Editors.png)

How the Number field is displayed to content editors in WP Admin.

[Link to heading#](https://www.advancedcustomfields.com/resources/number/#settings)

## Settings

Link copied

- **Default Value**


The default value shown when creating a new post.

- **Required**


Found on the Validation tab, this requires a numeric value be provided as the input and prevents the field from accepting empty values. Defaults to off.

- **Minimum Value**


The minimum value allowed.

- **Maximum Value**


The maximum value allowed.

- **Instructions**


Shows instructions when submitting data.

- **Placeholder Text**


Appears within input when no value exists.

- **Step Size**


The increment at which a numeric value can be set. Defaults to 1.

- **Prepend**


Adds a visual text element before the input.

- **Append**


Adds a visual text element after the input.


[Link to heading#](https://www.advancedcustomfields.com/resources/number/#template-usage)

## Template usage

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/number/#display-value-as-text)

### Display value as text

Link copied

This example demonstrates how to display a Number field value as text. We don’t recommend outputting any ACF value without any sort of protection or escaping.

```php
<p>To date, your efforts have raised $<?php echo esc_html( get_field('latest_total') ); ?>!</p>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/number/#display-value-within-css)

### Display value within CSS

Link copied

This example demonstrates how a Number field value named “h2\_font\_size” can be used to control the font size of all `<h2>` elements.

```php
<?php

$h2_font_size = get_field('h2_font_size');
if( $h2_font_size ): ?>
<style type="text/css">
    h2 {
        font-size: <?php echo esc_html( $h2_font_size ); ?>px;
    }
</style>
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

[Link to heading#](https://www.advancedcustomfields.com/resources/number/#related)

## Related

Link copied

- Basic: [Email](https://www.advancedcustomfields.com/resources/email/)
- Basic: [Text](https://www.advancedcustomfields.com/resources/text/)
- Basic: [URL](https://www.advancedcustomfields.com/resources/url/)
- Basic: [Text Area](https://www.advancedcustomfields.com/resources/textarea/)
- Basic: [Range](https://www.advancedcustomfields.com/resources/range/)

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

[Got it](https://www.advancedcustomfields.com/resources/number/#)