---
url: https://www.advancedcustomfields.com/resources/wysiwyg-editor
scraped_at: 2025-10-20T02:19:04.795Z
---

# Wysiwyg Editor

Last updated Feb 17, 2022

[Link to heading#](https://www.advancedcustomfields.com/resources/wysiwyg-editor/#description)

## Description

Link copied

The Wysiwyg field creates a WordPress content editor as seen in Posts and Pages. Wysiwyg is an acronym for "what you see is what you get".

This is one of the most useful fields for editing content as it allows for both text and multimedia to be edited and styled within a single area.

[Link to heading#](https://www.advancedcustomfields.com/resources/wysiwyg-editor/#screenshots)

## Screenshots

Link copied

[![A Wysiwyg field with sample lorem ipsum content](https://www.advancedcustomfields.com/wp-content/uploads/2013/02/acf-wysiwyg-field-interface.png)](https://www.advancedcustomfields.com/wp-content/uploads/2013/02/acf-wysiwyg-field-interface.png) The Wysiwyg editor field interface[![List of settings available when creating a Wysiwyg field](https://www.advancedcustomfields.com/wp-content/uploads/2013/02/acf-wysiwyg-field-settings-1.png)](https://www.advancedcustomfields.com/wp-content/uploads/2013/02/acf-wysiwyg-field-settings-1.png) The Wysiwyg editor field settings

[Link to heading#](https://www.advancedcustomfields.com/resources/wysiwyg-editor/#changelog)

## Changelog

Link copied

- Added Visual / Text options for `Tabs` in version 5.0.0

[Link to heading#](https://www.advancedcustomfields.com/resources/wysiwyg-editor/#settings)

## Settings

Link copied

- **Default Value**


The default value shown when creating a new post.

- **Tabs**


Selects which modes are shown to the user. Each Wysiwyg editor contains a visual and text mode. Choose from Visual and Text, Visual Only, or Text Only.

- **Toolbar**


Specifies which toolbar to show. Choose from Full or Basic. The Full toolbar reflects the typical WordPress editor toolbar with 2 rows of buttons. The Basic toolbar is a minified single row of buttons useful for a more trimmed experience.

- **Show Media Upload Buttons**


Provides the ability to upload inline media to the Wysiwyg field.

- **Delay initialization?**


Defers initialization of editor until editor is clicked instead of on page load. This is useful to speed up load times.


[Link to heading#](https://www.advancedcustomfields.com/resources/wysiwyg-editor/#template-usage)

## Template usage

Link copied

The Wysiwyg editor field will return your content formatted for HTML in the same manner that [the\_content()](https://developer.wordpress.org/reference/functions/the_content/) does.

[Link to heading#](https://www.advancedcustomfields.com/resources/wysiwyg-editor/#basic-display)

### Basic display

Link copied

This example demonstrates how to display a Wysiwyg field’s content.

```php
<?php the_field('product_summary'); ?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/wysiwyg-editor/#notes)

## Notes

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/wysiwyg-editor/#the-acfthecontent-filter)

### The acf\_the\_content filter

Link copied

When loading a Wysiwyg field value, the value is passed through a filter `acf_the_content` to apply HTML formatting. This filter, closely based on the WordPress [the\_content](https://codex.wordpress.org/Plugin_API/Filter_Reference/the_content) filter, is used instead to avoid unwanted recursion issues.

If you are using the `the_content` filter to modify content, please be sure to also filter `acf_the_content` as well.

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

[Link to heading#](https://www.advancedcustomfields.com/resources/wysiwyg-editor/#related)

## Related

Link copied

- Guides: [Customize the WYSIWYG toolbars](https://www.advancedcustomfields.com/resources/customize-the-wysiwyg-toolbars/)
- Field Types: [User](https://www.advancedcustomfields.com/resources/user/)
- Basic: [Text](https://www.advancedcustomfields.com/resources/text/)
- Basic: [Email](https://www.advancedcustomfields.com/resources/email/)
- Choice: [Button Group](https://www.advancedcustomfields.com/resources/button-group/)

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

[Got it](https://www.advancedcustomfields.com/resources/wysiwyg-editor/#)