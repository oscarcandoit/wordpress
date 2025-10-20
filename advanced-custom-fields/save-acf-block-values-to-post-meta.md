---
url: https://www.advancedcustomfields.com/resources/save-acf-block-values-to-post-meta
scraped_at: 2025-10-20T02:30:43.747Z
---

# Save ACF Block Field Values to Post Meta

Last updated May 22, 2024

[Link to heading#](https://www.advancedcustomfields.com/resources/save-acf-block-values-to-post-meta/#overview)

## Overview

Link copied

By default, WordPress stores a block’s field data inside the block’s HTML comment in `post_content`. This is usually fine, but you may also want to create an ACF Block that saves and reads its data from post meta instead, thus making it easier to query. This doc outlines how to save the content of an ACF Block in post meta instead of `post_content`.

The ability to save field data from ACF Blocks in post meta was introduced in [ACF PRO 6.3](https://www.advancedcustomfields.com/blog/acf-6-3-0-released/). This enables you to, for example, create a custom post type with a locked block template. This lets you replicate an experience similar to the classic editor, where only your block exists to enter specific structured data. This data would then be stored in post meta and allow you to query it easily.

[Link to heading#](https://www.advancedcustomfields.com/resources/save-acf-block-values-to-post-meta/#usage)

## Usage

Link copied

ACF Blocks default to the WordPress method of storing the block’s data, so you will have to make adjustments to the `block.json` file to enable storing in post meta.

The `usePostMeta: true` attribute is added to the [ACF key](https://www.advancedcustomfields.com/resources/acf-block-configuration-via-block-json/#blockjson-acf-key) section of your `block.json` file:

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
        "usePostMeta": "true"
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

[Link to heading#](https://www.advancedcustomfields.com/resources/save-acf-block-values-to-post-meta/#related)

## Related

Link copied

- ACF Blocks: [Disable Field Validation in ACF Blocks](https://www.advancedcustomfields.com/resources/disable-field-validation-in-acf-blocks/)
- ACF Blocks: [How To Upgrade a Legacy Block to block.json With ACF 6](https://www.advancedcustomfields.com/resources/how-to-upgrade-a-legacy-block-to-block-json-with-acf-6/)
- Functions: [acf\_register\_block\_type()](https://www.advancedcustomfields.com/resources/acf_register_block_type/)
- ACF Blocks: [ACF Blocks FAQ](https://www.advancedcustomfields.com/resources/acf-blocks-faq/)
- ACF Blocks: [Create Your First ACF Block](https://www.advancedcustomfields.com/resources/create-your-first-acf-block/)

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

[Got it](https://www.advancedcustomfields.com/resources/save-acf-block-values-to-post-meta/#)