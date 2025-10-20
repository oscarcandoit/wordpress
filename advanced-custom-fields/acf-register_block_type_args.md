---
url: https://www.advancedcustomfields.com/resources/acf-register_block_type_args
scraped_at: 2025-10-20T03:54:59.476Z
attempt: 1
---

# acf/register\_block\_type\_args

Last updated Feb 17, 2022

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-register_block_type_args/#description)

## Description

Link copied

Filters the arguments for registering a block type.

This filter is applied during the [acf\_register\_block\_type()](https://www.advancedcustomfields.com/resources/acf_register_block_type/) function after defaults have been merged and before the block type has been registered.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-register_block_type_args/#changelog)

## Changelog

Link copied

- Added in version 5.8.9

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-register_block_type_args/#parameters)

## Parameters

Link copied

```php
apply_filters( 'acf/register_block_type_args', $args );
```

- `$args` _(array)_ The array of arguments for registering a block type.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-register_block_type_args/#example)

## Example

Link copied

This example demonstrates how to apply a custom render callback for all block types.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-register_block_type_args/#functionsphp)

#### functions.php

Link copied

```php
<?php
add_filter('acf/register_block_type_args', 'my_acf_register_block_type_args');
function my_acf_register_block_type_args( $args ){
    $args['render_template'] = '';
    $args['render_callback'] = 'my_render_callback';
    return $args;
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

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-register_block_type_args/#related)

## Related

Link copied

- Functions: [acf\_register\_block\_type()](https://www.advancedcustomfields.com/resources/acf_register_block_type/)
- Filters: [acf/load\_field](https://www.advancedcustomfields.com/resources/acf-load_field/)
- Filters: [acf/format\_value](https://www.advancedcustomfields.com/resources/acf-format_value/)
- Filters: [acf/shortcode/prevent\_access](https://www.advancedcustomfields.com/resources/acf-shortcode-prevent_access/)
- Filters: [acf/prepare\_field](https://www.advancedcustomfields.com/resources/acf-prepare_field/)

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

[Got it](https://www.advancedcustomfields.com/resources/acf-register_block_type_args/#)