---
url: https://www.advancedcustomfields.com/resources/disable-field-validation-in-acf-blocks
scraped_at: 2025-10-20T02:30:48.746Z
---

# Disable Field Validation in ACF Blocks

Last updated Jun 10, 2024

[Link to heading#](https://www.advancedcustomfields.com/resources/disable-field-validation-in-acf-blocks/#overview)

## Overview

Link copied

Field validation is enabled by default for all ACF Blocks. Existing posts with ACF Blocks are validated the next time the post is edited. If any fields fail validation, the post cannot be saved until those issues are resolved. In some cases, you may wish to disable field validation for a particular ACF Block. This doc shows how to disable field validation by adding the `validate: false` attribute to the ACF key section of the `block.json` file.

Validation for fields contained in ACF Blocks was introduced in [ACF PRO 6.3](https://www.advancedcustomfields.com/blog/acf-6-3-0-released/). The fields in ACF Blocks can have any of the same validation rules applied to them as any custom field, such as being required, minimum and maximum values, and so on. This works the same way as validation for field groups assigned to posts, pages, or other data objects.

[Link to heading#](https://www.advancedcustomfields.com/resources/disable-field-validation-in-acf-blocks/#usage)

## Usage

Link copied

The validation attribute for ACF Blocks defaults to `true`, so you will have to make adjustments to the `block.json` file to prevent this behavior for an individual block. The `validate: false` attribute is added to the [ACF key](https://www.advancedcustomfields.com/resources/acf-block-configuration-via-block-json/#blockjson-acf-key) section of your `block.json` file:

```json php
{
    "name": "acf/testimonial",
    "title": "Testimonial",
    "description": "A custom testimonial block that uses ACF fields.",
    "style": [ "file:./testimonial.css" ],
    "category": "formatting",
    "icon": "admin-comments",
    "keywords": ["testimonial", "quote"],
    "acf": {
        "mode": "preview",
        "renderTemplate": "testimonial.php",
        "validate": false
    },
    "supports": {
        "anchor": true
    }
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

[Link to heading#](https://www.advancedcustomfields.com/resources/disable-field-validation-in-acf-blocks/#related)

## Related

Link copied

- ACF Blocks: [Save ACF Block Field Values to Post Meta](https://www.advancedcustomfields.com/resources/save-acf-block-values-to-post-meta/)
- ACF Blocks: [ACF Blocks V3](https://www.advancedcustomfields.com/resources/acf-blocks-v3/)
- ACF Blocks: [How To Upgrade a Legacy Block to block.json With ACF 6](https://www.advancedcustomfields.com/resources/how-to-upgrade-a-legacy-block-to-block-json-with-acf-6/)
- Functions: [acf\_register\_block\_type()](https://www.advancedcustomfields.com/resources/acf_register_block_type/)
- ACF Blocks: [ACF Blocks FAQ](https://www.advancedcustomfields.com/resources/acf-blocks-faq/)

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

[Got it](https://www.advancedcustomfields.com/resources/disable-field-validation-in-acf-blocks/#)