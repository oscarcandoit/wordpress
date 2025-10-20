---
url: https://www.advancedcustomfields.com/resources/text
scraped_at: 2025-10-20T02:25:31.348Z
---

# Text

Last updated May 22, 2023

[Link to heading#](https://www.advancedcustomfields.com/resources/text/#description)

## Description

Link copied

The Text field creates a basic text input, useful for storing single string values.

[Link to heading#](https://www.advancedcustomfields.com/resources/text/#screenshots)

## Screenshots

Link copied

![Creating a Text field within an ACF field group. ](https://www.advancedcustomfields.com/wp-content/uploads/2023/05/Text-field-General-Settings.png)

Creating a Text field within an ACF field group.

![The Presentation tab lets you control how the Text field will appear. ](https://www.advancedcustomfields.com/wp-content/uploads/2023/05/Text-Field-Presentation-Settings.png)

The Presentation tab lets you control how the Text field will appear to content editors.

![How the Text field appears to content editors. Changes made on the Presentation tab, such as placeholder text, are reflected here.  ](https://www.advancedcustomfields.com/wp-content/uploads/2023/05/Text-Field-ACF-What-Content-Editors-See-1.png)

How the Text field appears to content editors. Changes made on the Presentation tab are reflected here.

[Link to heading#](https://www.advancedcustomfields.com/resources/text/#changelog)

## Changelog

Link copied

- Formatting setting removed in version 5.0.0.

[Link to heading#](https://www.advancedcustomfields.com/resources/text/#settings)

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

- **Placeholder Text**


Appears within input when no value exists.

- **Prepend**


Adds a visual text element before the input.

- **Append**


Adds a visual text element after the input.


[Link to heading#](https://www.advancedcustomfields.com/resources/text/#template-usage)

## Template usage

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/text/#display-value)

### Display value

Link copied

This example demonstrates how to display a Text field named “heading” within a `<h2>` tag. We don’t recommend outputting any ACF value without any sort of protection or escaping.

```php
<h2><?php echo esc_html( get_field('heading') ); ?></h2>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/text/#load-value)

### Load value

Link copied

This example demonstrates how to load the value of a Text field named “confirm” and perform an action based on its value.

```php
$confirm = get_field('confirm');
if( $confirm === 'SEND_EMAIL' ) {
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

[Link to heading#](https://www.advancedcustomfields.com/resources/text/#related)

## Related

Link copied

- Basic: [Email](https://www.advancedcustomfields.com/resources/email/)
- Basic: [URL](https://www.advancedcustomfields.com/resources/url/)
- Basic: [Text Area](https://www.advancedcustomfields.com/resources/textarea/)
- Basic: [Number](https://www.advancedcustomfields.com/resources/number/)
- Basic: [Password](https://www.advancedcustomfields.com/resources/password/)

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

[Got it](https://www.advancedcustomfields.com/resources/text/#)