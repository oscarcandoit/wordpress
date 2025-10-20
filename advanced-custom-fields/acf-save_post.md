---
url: https://www.advancedcustomfields.com/resources/acf-save_post
scraped_at: 2025-10-20T02:18:21.750Z
---

# acf/save\_post

Last updated Feb 17, 2022

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-save_post/#description)

## Description

Link copied

Fires when saving the submitted `$_POST` data.

This action allows you to hook in before or after the `$_POST` data has been saved, making it useful to perform additional functionality when updating a post or other WP object.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-save_post/#parameters)

## Parameters

Link copied

```php
do_action( 'acf/save_post', $post_id );
```

- `$post_id` _(int\|string)_ The ID of the post being edited.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-save_post/#changelog)

## Changelog

Link copied

- Changed namespace from `$_POST['fields']` to `$_POST['acf']` in version 5.0.0
- Added in version 4.0.0

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-save_post/#examples)

## Examples

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-save_post/#applied-after-save)

### Applied after save

Link copied

This example demonstrates how to perform additional functionality after ACF has saved the `$_POST` data.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-save_post/#functionsphp)

#### functions.php

Link copied

```php
add_action('acf/save_post', 'my_acf_save_post');
function my_acf_save_post( $post_id ) {

    // Get newly saved values.
    $values = get_fields( $post_id );

    // Check the new value of a specific field.
    $hero_image = get_field('hero_image', $post_id);
    if( $hero_image ) {
        // Do something...
    }
}
```

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-save_post/#applied-before-save)

### Applied before save

Link copied

This example demonstrates how to perform additional functionality before ACF has saved the `$_POST` data by using a priority less than 10.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-save_post/#functionsphp)

#### functions.php

Link copied

```php
add_action('acf/save_post', 'my_acf_save_post', 5);
function my_acf_save_post( $post_id ) {

    // Get previous values.
    $prev_values = get_fields( $post_id );

    // Get submitted values.
    $values = $_POST['acf'];

    // Check if a specific value was updated.
    if( isset($_POST['acf']['field_abc123']) ) {
        // Do something.
    }
}
```

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-save_post/#notes)

## Notes

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-save_post/#parameters)

### Parameters

Link copied

Unlike the WordPress [save\_post](https://codex.wordpress.org/Plugin_API/Action_Reference/save_post) action, this action does not contain the `$post` and `$updated` parameters. If you require access to these parameters, consider using an alternative action instead.

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

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-save_post/#related)

## Related

Link copied

- Actions: [acf/options\_page/save](https://www.advancedcustomfields.com/resources/acf-options_page-save/)
- Actions: [acf/validate\_save\_post](https://www.advancedcustomfields.com/resources/acf-validate_save_post/)
- Filters: [acf/update\_value](https://www.advancedcustomfields.com/resources/acf-update_value/)
- Actions: [acf/init](https://www.advancedcustomfields.com/resources/acf-init/)
- Actions: [acf/render\_field](https://www.advancedcustomfields.com/resources/acf-render_field/)

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

[Got it](https://www.advancedcustomfields.com/resources/acf-save_post/#)