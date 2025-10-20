---
url: https://www.advancedcustomfields.com/resources/acf-field_group-admin_footer
scraped_at: 2025-10-20T02:17:52.948Z
---

# acf/field\_group/admin\_footer

Last updated Feb 17, 2022

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-field_group-admin_footer/#description)

## Description

Link copied

Used to output additional `<body>` HTML to the field group admin edit page.

This action is similar to the WordPress [admin\_footer](https://codex.wordpress.org/Plugin_API/Action_Reference/admin_footer), except that it is only fired on the field group admin edit page.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-field_group-admin_footer/#changelog)

## Changelog

Link copied

- Added in version 5.0.0

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-field_group-admin_footer/#example)

## Example

Link copied

This example demonstrates how to output additional inline style and script tags to customize field group settings.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-field_group-admin_footer/#functionsphp)

#### functions.php

Link copied

```php
<?php
add_action('acf/field_group/admin_footer', 'my_acf_field_group_admin_footer');
function my_acf_field_group_admin_footer() {
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

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-field_group-admin_footer/#related)

## Related

Link copied

- Actions: [acf/field\_group/admin\_head](https://www.advancedcustomfields.com/resources/acf-field_group-admin_head/)
- Actions: [acf/input/admin\_footer](https://www.advancedcustomfields.com/resources/acf-input-admin_footer/)
- Actions: [acf/input/admin\_head](https://www.advancedcustomfields.com/resources/acf-input-admin_head/)
- Actions: [acf/field\_group/admin\_enqueue\_scripts](https://www.advancedcustomfields.com/resources/acf-field_group-admin_enqueue_scripts/)
- Actions: [acf/input/admin\_enqueue\_scripts](https://www.advancedcustomfields.com/resources/acf-input-admin_enqueue_scripts/)

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

[Got it](https://www.advancedcustomfields.com/resources/acf-field_group-admin_footer/#)