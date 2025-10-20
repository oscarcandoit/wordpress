---
url: https://www.advancedcustomfields.com/resources/email
scraped_at: 2025-10-20T02:25:48.557Z
---

# Email

Last updated Jun 27, 2023

[Link to heading#](https://www.advancedcustomfields.com/resources/email/#description)

## Description

Link copied

The Email field creates an email input, used for storing email address values.

[Link to heading#](https://www.advancedcustomfields.com/resources/email/#screenshots)

## Screenshots

Link copied

![Creating an Email field.](https://www.advancedcustomfields.com/wp-content/uploads/2023/03/Creating-an-Email-Field-1.png)

Creating an Email field within an ACF field group.

![The Presentation tab allows you to control how your Email field will appear.](https://www.advancedcustomfields.com/wp-content/uploads/2023/03/Email-Field-Presentation-Layer-ACF.png)

The Presentation tab allows you to control how your Email field will appear.

![How the email field appears to content editors. ](https://www.advancedcustomfields.com/wp-content/uploads/2023/03/Email-Field-Displayed-to-Editors-ACF.png)

How the email field appears to content editors. You can see how settings in the Presentation layer control what is displayed to editors.

[Link to heading#](https://www.advancedcustomfields.com/resources/email/#settings)

## Settings

Link copied

- **Default Value**


The default value shown when creating a new post.

- **Required**


Found on the Validation tab, this requires a valid email be provided as the input and prevents the field from accepting empty values. Defaults to off.

- **Instructions**


Shows instructions when submitting data.

- **Placeholder Text**


Appears within input when no value exists.

- **Prepend**


Adds a visual text element before the input.

- **Append**


Adds a visual text element after the input.

- **Character Limit**


Limits the number of characters allowed.


[Link to heading#](https://www.advancedcustomfields.com/resources/email/#template-usage)

## Template usage

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/email/#display-value)

### Display value

Link copied

This example demonstrates how to display an Email field named “contact\_email” within a `<h2>` tag.

```php
<h2><?php the_field("contact_email"); ?></h2>
```

However, we don’t recommend outputting any ACF value without any sort of protection or escaping. We’ll cover how to protect the address from spam bots in the section below.

[Link to heading#](https://www.advancedcustomfields.com/resources/email/#load-value)

### Load value

Link copied

This example demonstrates how to load the value of an Email field named “contact\_email” and use it in a `mailto:` contact link, where the email is protected from spam bots using the WordPress [`antispambot()`](https://developer.wordpress.org/reference/functions/antispambot/) function.

```php
email us at <a href="<?php echo esc_url( 'mailto:' . antispambot( get_field(‘contact_email’ ) ) ); ?>"><?php echo esc_html( antispambot( get_field('contact_email' ) ) ); ?></a>
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

[Link to heading#](https://www.advancedcustomfields.com/resources/email/#related)

## Related

Link copied

- Basic: [Text](https://www.advancedcustomfields.com/resources/text/)
- Basic: [URL](https://www.advancedcustomfields.com/resources/url/)
- Basic: [Number](https://www.advancedcustomfields.com/resources/number/)
- Basic: [Text Area](https://www.advancedcustomfields.com/resources/textarea/)
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

[Got it](https://www.advancedcustomfields.com/resources/email/#)