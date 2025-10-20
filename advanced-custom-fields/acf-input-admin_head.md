---
url: https://www.advancedcustomfields.com/resources/acf-input-admin_head
scraped_at: 2025-10-20T02:33:13.258Z
---

# acf/input/admin\_head

Last updated Mar 10, 2025

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-input-admin_head/#description)

## Description

Link copied

Used to output additional `<head>` HTML to pages where ACF fields appear.

This action is similar to the WordPress [admin\_head](https://codex.wordpress.org/Plugin_API/Action_Reference/admin_head), except that it is only fired on pages where ACF fields appear – such as when editing posts, users, taxonomy terms, options pages and [front-end forms](https://www.advancedcustomfields.com/blog/wordpress-frontend-form/).

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-input-admin_head/#changelog)

## Changelog

Link copied

- Added in version 4.0.0

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-input-admin_head/#example)

## Example

Link copied

This example demonstrates how to output additional inline style and script tags to customize fields.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-input-admin_head/#functionsphp)

#### functions.php

Link copied

```php
<?php
add_action('acf/input/admin_head', 'my_acf_admin_head');
function my_acf_admin_head() {
    ?>
    <style type="text/css">
        /* CSS here. */
    </style>
    <script type="text/javascript">
    (function( $ ){
        // Javascript here.
    })(jQuery);
    </script>
    <?php
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

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-input-admin_head/#related)

## Related

Link copied

- Actions: [acf/input/admin\_footer](https://www.advancedcustomfields.com/resources/acf-input-admin_footer/)
- Actions: [acf/field\_group/admin\_head](https://www.advancedcustomfields.com/resources/acf-field_group-admin_head/)
- Actions: [acf/field\_group/admin\_footer](https://www.advancedcustomfields.com/resources/acf-field_group-admin_footer/)
- Actions: [acf/input/admin\_enqueue\_scripts](https://www.advancedcustomfields.com/resources/acf-input-admin_enqueue_scripts/)
- Guides: [Adding custom javascript to fields](https://www.advancedcustomfields.com/resources/adding-custom-javascript-fields/)

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

[Got it](https://www.advancedcustomfields.com/resources/acf-input-admin_head/#)