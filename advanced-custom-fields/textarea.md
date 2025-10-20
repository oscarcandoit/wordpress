---
url: https://www.advancedcustomfields.com/resources/textarea
scraped_at: 2025-10-20T02:26:01.669Z
---

# Text Area

Last updated Jul 31, 2023

[Link to heading#](https://www.advancedcustomfields.com/resources/textarea/#description)

## Description

Link copied

The Text Area field creates a basic textarea input, useful to store simple (i.e., unstyled) paragraphs of text to use in your theme.

[Link to heading#](https://www.advancedcustomfields.com/resources/textarea/#screenshots)

## Screenshots

Link copied

![Creating a Text Area field in ACF. ](https://www.advancedcustomfields.com/wp-content/uploads/2023/05/Text-Area-General-Settings-1.png)

Creating a Text Area field in ACF.

![The Presentation tab controls how the field will display. ](https://www.advancedcustomfields.com/wp-content/uploads/2023/05/Text-Area-Presentation-Settings-1.png)

The Presentation tab controls how the field will display.

![How the Text Area field appears when editing content. You can see how changes made on the Presentation tab are reflected here. ](https://www.advancedcustomfields.com/wp-content/uploads/2023/05/Text-Area-What-Content-Editors-See-1.png)

How the Text Area field appears when editing content. You can see how changes made on the Presentation tab are reflected here.

[Link to heading#](https://www.advancedcustomfields.com/resources/textarea/#changelog)

## Changelog

Link copied

- Formatting setting removed in version 5.0.0.
- Rows setting added in 4.3.5.

[Link to heading#](https://www.advancedcustomfields.com/resources/textarea/#settings)

## Settings

Link copied

- **Default Value**


The default value shown when creating a new post.

- **Required**


Found on the Validation tab, this prevents the field from accepting empty values. Defaults to off.

- **Character Limit**


Limits the number of characters allowed.

- **Instructions**


Shows instructions when submitting data.

- **Rows**


Sets the height of this field. Defaults to 8.

- **Placeholder Text**


Appears within input when no value exists.

- **New Lines**


Changes the way new lines are formatted. Selecting “Automatically add paragraphs” will add paragraph tags around the value. Selecting “Automatically add `<br>`” will convert any new lines to HTML line breaks. Selecting “No Formatting” will not convert
_any_ tags, and you will see any HTML displayed as normal text similar to regular content.


[Link to heading#](https://www.advancedcustomfields.com/resources/textarea/#template-usage)

## Template usage

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/textarea/#display-value-with-paragraphs-automatically-added)

### Display value with paragraphs automatically added

Link copied

This example demonstrates how to display a Text Area field named `product_description` when the “Automatically add paragraphs” setting is enabled.

```php
<h3>Product Description</h3>
<?php echo wp_kses_post ( get_field('product_description') ); ?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/textarea/#display-value-without-formatting)

### Display value without formatting

Link copied

This example demonstrates how to display a Text Area field named `product_description` when the “No Formatting” setting is enabled. In this case, we have to indicate a paragraph manually with the `<p>` tag.

```php
<h3>Product Description</h3>
<p><?php echo wp_kses_post ( get_field('product_description') ); ?></p>
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

[Link to heading#](https://www.advancedcustomfields.com/resources/textarea/#related)

## Related

Link copied

- Basic: [Text](https://www.advancedcustomfields.com/resources/text/)
- Basic: [Email](https://www.advancedcustomfields.com/resources/email/)
- Basic: [Number](https://www.advancedcustomfields.com/resources/number/)
- Basic: [URL](https://www.advancedcustomfields.com/resources/url/)
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

[Got it](https://www.advancedcustomfields.com/resources/textarea/#)