---
url: https://www.advancedcustomfields.com/resources/acf-shortcode-prevent_access
scraped_at: 2025-10-20T02:31:23.703Z
---

# acf/shortcode/prevent\_access

Last updated Jul 18, 2024

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-shortcode-prevent_access/#description)

## Description

Link copied

Allows you to limit the fields which can be output by the ACF Shortcode. Returning true from this filter will prevent the value being output by the shortcode.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-shortcode-prevent_access/#changelog)

## Changelog

Link copied

- Added in version 6.2.7

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-shortcode-prevent_access/#parameters)

## Parameters

Link copied

```php
apply_filters( 'acf/shortcode/prevent_access', $access_prevented, $atts, $decoded_post_id, $decoded_post_type, $field_type, $field )
```

- `$access_prevented` _(boolean)_ The current access disabled state. False by default, will be true if another filter has prevented access to the requested field value.
- `$atts` _(array)_ The full array of attributes provided as part of the shortcode. This array is likely to contain `field` as per the [shortcode documentation](https://www.advancedcustomfields.com/resources/shortcode/)
- `$decoded_post_id` _(int\|string)_ This is the decoded ID for the item being retrieved. It may be a user ID, a term ID, an option page prefix or any ID of any other place where ACF can store data; use with `$decoded_post_type` to know which.
- `$decoded_post_type` _(string)_ A string containing the type of object being queried. post, term, comment, option, or user
- `$field_type` _(string)_ A string of the field type being slug being output. For example, `text` or `text_area`
- `$field` _(array)_ The full array of the field object, including its value.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-shortcode-prevent_access/#example-deny-access-to-options-pages)

### Example: Deny access to options pages

Link copied

This example prevents the ACF Shortcode outputting any values stored in an options page.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-shortcode-prevent_access/#functionsphp)

#### functions.php

Link copied

```php
<?php
function my_acf_prevent_access_to_options( $access_prevented, $atts, $decoded_post_id, $decoded_post_type ) {
    if ( 'option' === $decoded_post_type ) {
        return true;
    }
    return $access_prevented;
}
add_filter( 'acf/shortcode/prevent_access', 'my_acf_prevent_access_to_options', 10, 4 );
```

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-shortcode-prevent_access/#example-deny-access-to-field-values-on-private-posts)

### Example: Deny access to field values on private posts

Link copied

This example prevents the ACF Shortcode outputting any values stored in a post which is not publicly visible.

_Please note: Since ACF 6.3.4, this behaviour has become default._

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-shortcode-prevent_access/#functionsphp)

#### functions.php

Link copied

```php
<?php
function my_acf_prevent_access_to_fields_on_private_posts( $access_prevented, $atts, $decoded_post_id, $decoded_post_type ) {
    if ( 'post' === $decoded_post_type && ! is_post_publicly_viewable( $decoded_post_id ) ) {
        return true;
    }
    return $access_prevented;
}
add_filter( 'acf/shortcode/prevent_access', 'my_acf_prevent_access_to_fields_on_private_posts', 10, 4 );
```

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-shortcode-prevent_access/#example-deny-access-to-every-field-apart-from-myfieldname)

### Example: Deny access to every field apart from “my\_field\_name”

Link copied

This example prevents the ACF Shortcode outputting any values other than the “my\_field\_name” field.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-shortcode-prevent_access/#functionsphp)

#### functions.php

Link copied

```php
<?php
function my_acf_prevent_access_to_all_but_one_field( $access_prevented, $atts, $decoded_post_id, $decoded_post_type, $field_type, $field_array ) {
    if ( 'my_field_name' === $field_array['name'] ) {
        return false;
    }
    return true;
}
add_filter( 'acf/shortcode/prevent_access', 'my_acf_prevent_access_to_all_but_one_field', 10, 6 );
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

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-shortcode-prevent_access/#related)

## Related

Link copied

- Filters: [acf/format\_value](https://www.advancedcustomfields.com/resources/acf-format_value/)
- Filters: [acf/fields/post\_object/result](https://www.advancedcustomfields.com/resources/acf-fields-post_object-result/)
- Filters: [acf/load\_value](https://www.advancedcustomfields.com/resources/acf-load_value/)
- Filters: [acf/update\_value](https://www.advancedcustomfields.com/resources/acf-update_value/)
- Filters: [acf/fields/taxonomy/result](https://www.advancedcustomfields.com/resources/acf-fields-taxonomy-result/)

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

[Got it](https://www.advancedcustomfields.com/resources/acf-shortcode-prevent_access/#)