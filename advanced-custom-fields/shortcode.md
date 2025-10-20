---
url: https://www.advancedcustomfields.com/resources/shortcode
scraped_at: 2025-10-20T02:30:39.285Z
---

# Shortcode

Last updated May 22, 2024

[Link to heading#](https://www.advancedcustomfields.com/resources/shortcode/#overview)

## Overview

Link copied

Shortcodes can be used within a WYGIWYG to display another field’s value. To learn more about shortcodes, [click here](http://codex.wordpress.org/Shortcode_API).

**From ACF 6.3.0, the ACF shortcode is disabled by default for new installs of ACF. If you need to enable it, see [enabling the ACF shortcode](https://www.advancedcustomfields.com/resources/shortcode/#enabling).**

**For security, we recommend [disabling the ACF shortcode](https://www.advancedcustomfields.com/resources/shortcode/#disabling) if you are not using it.**

[Link to heading#](https://www.advancedcustomfields.com/resources/shortcode/#usage)

## Usage

Link copied

Place the shortcode marker with the desired field within your wysiwyg content. This shortcode runs the same as the [the\_field()](https://www.advancedcustomfields.com/docs/functions/the_field/ "the_field()") function.

```php
[acf field="field_name" post_id="123"]
```

[Link to heading#](https://www.advancedcustomfields.com/resources/shortcode/#example)

## Example

Link copied

```php
This is a story about a boy named [acf field="name"]. He is [acf field="age"] years old.
```

[Link to heading#](https://www.advancedcustomfields.com/resources/shortcode/#limitations)

## Limitations

Link copied

- Only works for simple text based values

[Link to heading#](https://www.advancedcustomfields.com/resources/shortcode/#disabling)

## Disabling the Shortcode

Link copied

The ACF shortcode allows access to any field on any post type as was enabled by default any install of ACF created before the release of ACF 6.3. This means any user who has permission to publish posts on your site can view any ACF data if they know the field name or key. For this reason, we recommend you disable the shortcode if your site is not using it. You can use the following setting to disable it:

```php
add_action( 'acf/init', 'set_acf_settings' );
function set_acf_settings() {
    acf_update_setting( 'enable_shortcode', false );
}
```

[Link to heading#](https://www.advancedcustomfields.com/resources/shortcode/#enabling)

## Enabling the Shortcode

Link copied

When enabled, the ACF shortcode allows access to any field on any post type. This means any user who has permission to publish posts on your site can view any ACF data if they know the field name or key. For this reason, from ACF 6.3 the shortcode is disabled by default for new installs. If you do need to use it, for example for a page builder, you can use the following setting to enable it:

```php
add_action( 'acf/init', 'set_acf_settings' );
function set_acf_settings() {
    acf_update_setting( 'enable_shortcode', true );
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

[Link to heading#](https://www.advancedcustomfields.com/resources/shortcode/#related)

## Related

Link copied

- Features: [Updates to ACF Field Functions in 5.11](https://www.advancedcustomfields.com/resources/acf-field-functions/)
- Filters: [acf/shortcode/prevent\_access](https://www.advancedcustomfields.com/resources/acf-shortcode-prevent_access/)
- Getting Started: [Displaying Values in Your Theme](https://www.advancedcustomfields.com/resources/displaying-custom-field-values-in-your-theme/)
- Field Types: [User](https://www.advancedcustomfields.com/resources/user/)
- Functions: [acf\_form()](https://www.advancedcustomfields.com/resources/acf_form/)

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

[Got it](https://www.advancedcustomfields.com/resources/shortcode/#)