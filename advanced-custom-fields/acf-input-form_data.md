---
url: https://www.advancedcustomfields.com/resources/acf-input-form_data
scraped_at: 2025-10-20T02:18:16.668Z
---

# acf/input/form\_data

Last updated Feb 17, 2022

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-input-form_data/#description)

## Description

Link copied

Used to output additional HTML within the hidden `<div id="acf-form-data">` element.

This element is output within each form, and includes hidden inputs used to process the form data.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-input-form_data/#parameters)

## Parameters

Link copied

```php
do_action( 'acf/form_data', $data );
```

- `$data` _(array)_ The current form data including "screen", "post\_id" and "nonce".

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-input-form_data/#changelog)

## Changelog

Link copied

- Added in version 5.0.0

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-input-form_data/#example)

## Example

Link copied

This example demonstrates how to output a hidden input, and then later perform an action depending on that value.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-input-form_data/#functionsphp)

#### functions.php

Link copied

```php
<?php
add_action('acf/input/form_data', 'my_acf_input_form_data');
function my_acf_input_form_data( $data ) {
    echo '<input type="hidden" name="_my_hidden_input" value="123" />';
}

add_action('acf/save_post', 'my_acf_save_post');
function my_acf_save_post( $post_id ) {
    if( isset($_POST['_my_hidden_input']) ) {
        // Do something.
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

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-input-form_data/#related)

## Related

Link copied

- Actions: [acf/render\_field](https://www.advancedcustomfields.com/resources/acf-render_field/)
- Actions: [acf/input/admin\_footer](https://www.advancedcustomfields.com/resources/acf-input-admin_footer/)
- Actions: [acf/input/admin\_head](https://www.advancedcustomfields.com/resources/acf-input-admin_head/)
- Functions: [acf\_form\_head()](https://www.advancedcustomfields.com/resources/acf_form_head/)
- Actions: [acf/save\_post](https://www.advancedcustomfields.com/resources/acf-save_post/)

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

[Got it](https://www.advancedcustomfields.com/resources/acf-input-form_data/#)