---
url: https://www.advancedcustomfields.com/resources/block-api-v2
scraped_at: 2025-10-20T02:26:24.228Z
---

# Block API v2

Last updated Aug 17, 2023

[Link to heading#](https://www.advancedcustomfields.com/resources/block-api-v2/#introduction)

## Introduction

Link copied

Since WordPress 5.6, the block editor has a new version of the [Block API](https://make.wordpress.org/core/2020/11/18/block-api-version-2/). The ACF 5.10 release introduced support for the Block API v2. This is only available when ACF is installed on sites using WordPress 5.6 and above.

[Link to heading#](https://www.advancedcustomfields.com/resources/block-api-v2/#changes)

## Changes

Link copied

The block wrapper element for ACF Blocks with Block API v2 support now have a predefined class of `wp-block-{name}`, where `name` is generated from the name of the block. This is in line with the changes to how the block editor defines the default wrapper element.

```php
<div id="testimonial-block_6126540e5e5e2" class="testimonial wp-block-acf-testimonial">
```

[Link to heading#](https://www.advancedcustomfields.com/resources/block-api-v2/#block-filters)

## Block Filters

Link copied

In ACF 5.10 we moved to support version 2 of the WordPress Blocks API. The goal was to support more advanced functionality such as the ability to use the Block Editor’s `extraProps` filter. Unfortunately, our implementation of this triggered re-rendering of ACF blocks anytime a property changed, which caused issues with other block editor features such as block styles and the built-in spacing/padding support.

ACF 5.11 removed support of the extraProps functionality to prevent these re-renders which will improve performance and solve issues with block styles. We want ACF blocks to function as closely as possible to core or custom-built WordPress blocks. Therefore, we’re working on re-introducing support for this in an upcoming release.

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

[Link to heading#](https://www.advancedcustomfields.com/resources/block-api-v2/#related)

## Related

Link copied

- ACF Blocks: [How To Upgrade a Legacy Block to block.json With ACF 6](https://www.advancedcustomfields.com/resources/how-to-upgrade-a-legacy-block-to-block-json-with-acf-6/)
- Functions: [acf\_register\_block\_type()](https://www.advancedcustomfields.com/resources/acf_register_block_type/)
- ACF Blocks: [Create Your First ACF Block](https://www.advancedcustomfields.com/resources/create-your-first-acf-block/)
- ACF Blocks: [ACF Blocks V3](https://www.advancedcustomfields.com/resources/acf-blocks-v3/)
- ACF Blocks: [ACF Blocks: Using get\_block\_wrapper\_attributes()](https://www.advancedcustomfields.com/resources/acf-blocks-using-get_block_wrapper_attributes/)

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

[Got it](https://www.advancedcustomfields.com/resources/block-api-v2/#)