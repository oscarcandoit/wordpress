---
url: https://www.advancedcustomfields.com/resources/acf-block-configuration-via-block-json
scraped_at: 2025-10-20T02:16:07.001Z
---

# ACF Blocks Configuration via block.json

Last updated May 22, 2024

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-block-configuration-via-block-json/#description)

## Description

Link copied

Since ACF 6.0, ACF has recommended using `block.json` to handle your block registration.

A mirror of the WordPress JSON Schema for `block.json`, with ACF’s additions, is available at [https://github.com/AdvancedCustomFields/schemas/blob/main/json/block.json](https://github.com/AdvancedCustomFields/schemas/blob/main/json/block.json).

The WordPress documentation for `block.json`, describing all the core properties, is [available here](https://developer.wordpress.org/block-editor/reference-guides/block-api/block-metadata/).

If your `block.json` contains an ACF key, it will be loaded by ACF as an ACF Block.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-block-configuration-via-block-json/#blockjson-acf-key)

## Block.json ACF Key

Link copied

The ACF key supports the following properties:

- **renderTemplate**


(String) The path to a template file used to render the block HTML. This can either be a relative path from the `block.json` file or a full path to any file.


```php
// Specifying a relative path to the block.json file
"acf": {
"renderTemplate": "testimonial.php"
}
```

- **renderCallback**


(Callable) (Optional) Instead of providing a render template, a callback function name may be specified to output the block’s HTML.


```php
// Specifying a function
"acf": {
"renderCallback": "my_acf_block_render_callback"
}
```

- **mode**


(String) (Optional) The display mode for your block. Available settings are “auto”, “preview” and “edit”. Defaults to “preview”.


  - **auto**: Preview is shown by default, but changes to edit form when block is selected.
  - **preview**: Preview is always shown. Edit form appears in sidebar when block is selected.
  - **edit**: Edit form is always shown.

Note: When in “preview” or “edit” modes, an icon will appear in the block toolbar to toggle between modes.

```php
"acf": {
"mode": "auto"
}
```

- **blockVersion**


(Integer) The version of ACF Blocks to use. Version 1 of ACF Blocks is deprecated and not recommended for use with `block.json`. Default is `2`.

- **postTypes**


(Array) (Optional) An array of post types to which this block type is restricted.


```php
"acf": {
"postTypes": ["post", "page"]
}
```

- **validate**
(Boolean) (Since 6.3.0) Should the fields in the block be validated as per the field group configuration. Default is `true`.


```php
"acf": {
"validate": false
}
```

- **usePostMeta**
(Boolean) (Since 6.3.0) Should this block store its field values directly in post meta, rather than the block comment. When enabled, this block will be limited to once per page, and only as a top level block. These blocks will also not be supported as widgets or in the site editor/templates. Default is `false`.


```php
"acf": {
"usePostMeta": true
}
```


[Link to heading#](https://www.advancedcustomfields.com/resources/acf-block-configuration-via-block-json/#blockjson-example)

## Block.json Example

Link copied

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
        "validate": "false"
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

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-block-configuration-via-block-json/#related)

## Related

Link copied

- Functions: [acf\_register\_block\_type()](https://www.advancedcustomfields.com/resources/acf_register_block_type/)
- ACF Blocks: [ACF Blocks V3](https://www.advancedcustomfields.com/resources/acf-blocks-v3/)
- ACF Blocks: [How To Upgrade a Legacy Block to block.json With ACF 6](https://www.advancedcustomfields.com/resources/how-to-upgrade-a-legacy-block-to-block-json-with-acf-6/)
- ACF Blocks: [Extending ACF Blocks With Block Supports](https://www.advancedcustomfields.com/resources/extending-acf-blocks-with-block-supports/)
- ACF Blocks: [ACF Blocks](https://www.advancedcustomfields.com/resources/blocks/)

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

[Got it](https://www.advancedcustomfields.com/resources/acf-block-configuration-via-block-json/#)