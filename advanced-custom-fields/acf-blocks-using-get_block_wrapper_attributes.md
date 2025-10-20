---
url: https://www.advancedcustomfields.com/resources/acf-blocks-using-get_block_wrapper_attributes
scraped_at: 2025-10-20T02:27:09.907Z
---

# ACF Blocks: Using get\_block\_wrapper\_attributes()

Last updated Oct 3, 2023

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-blocks-using-get_block_wrapper_attributes/#overview)

## Overview

Link copied

The [get\_block\_wrapper\_attributes()](https://developer.wordpress.org/reference/functions/get_block_wrapper_attributes/) function allows you to use the styles built by WordPress’ native `supports` for a block, such as background and text colors, padding, margin, etc.

In the block editor, this is automatically output for you, on the wrapper WordPress adds around your block:

![An example of the wrapper WordPress adds around your block in the block editor when using get_block_wrapper_attributes(). ](https://www.advancedcustomfields.com/wp-content/uploads/2023/09/ACF-Blocks-WordPress-Block-Wrapper-Example.jpeg)

For this reason, you shouldn’t try to _always_ apply `get_block_wrapper_attributes` in your ACF Block PHP template. If you try to use that function when your block is rendered in the editor, you’ll get a PHP warning when your block is rendered there and no output due to the way ACF blocks are rendered, isolated from the rest of the page.

Instead, use ACF’s `$is_preview` variable to know when your block is being output on the frontend, and _then_ use `get_block_wrapper_attributes()` to add all the styles selected for your block.

![An example of get_block_wrapper_attributes() applied at the correct point. ](https://www.advancedcustomfields.com/wp-content/uploads/2023/09/ACF-Blocks-Outer-Wrapper-Template.jpeg)

The following code makes sure we’re not in preview mode before outputting the wrapper attributes.

```php
<?php $attrs = $is_preview ? ' ' : get_block_wrapper_attributes(); ?>
<div
    data-demo-hint="This is the outer wrapper in my template"
    id="<?php echo esc_attr( $id ); ?>"
    <?php echo $attrs; ?>
>
   // Block output goes here.
</div>
```

This does mean your DOM structures are slightly different on the backend and the frontend, as your styles are applied one layer deeper. If that’s an issue, you can get around it by adding a new wrapper element to contain your styles, and apply it only to the frontend view:

```php
<?php if ( ! $is_preview ) { ?>
    <div id="<?php echo esc_attr( $id ); ?>" <?php echo get_block_wrapper_attributes(); ?>>
<?php } ?>
    // Standard block template goes here
<?php if ( ! $is_preview ) { ?>
    </div>
<?php } ?>
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

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-blocks-using-get_block_wrapper_attributes/#related)

## Related

Link copied

- ACF Blocks: [Extending ACF Blocks With Block Supports](https://www.advancedcustomfields.com/resources/extending-acf-blocks-with-block-supports/)
- Getting Started: [Displaying Values in Your Theme](https://www.advancedcustomfields.com/resources/displaying-custom-field-values-in-your-theme/)
- Guides: [Adding fields to Posts](https://www.advancedcustomfields.com/resources/adding-fields-posts/)
- ACF Blocks: [ACF Blocks V3](https://www.advancedcustomfields.com/resources/acf-blocks-v3/)
- Functions: [acf\_register\_block\_type()](https://www.advancedcustomfields.com/resources/acf_register_block_type/)

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

[Got it](https://www.advancedcustomfields.com/resources/acf-blocks-using-get_block_wrapper_attributes/#)