---
url: https://www.advancedcustomfields.com/resources/acf-fields-user-query
scraped_at: 2025-10-20T02:29:45.812Z
---

# acf/fields/user/query

Last updated Apr 4, 2024

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-fields-user-query/#description)

## Description

Link copied

Filters the query `$args` used by `WP_Query` to display text for each user.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-fields-user-query/#parameters)

## Parameters

Link copied

```php
apply_filters( 'acf/fields/user/query', $args, $field, $post_id );
```

- `$array` _(array)_ The query args. See [WP\_Query](https://developer.wordpress.org/reference/classes/wp_query/) for available args.
- `$field` _(array)_ The field array containing all settings.
- `$post_id` _(WP\_Post)_ The post ID where the value is saved.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-fields-user-query/#modifiers)

## Modifiers

Link copied

This filter provides modifiers to target specific fields. The following filter names are available:

- `acf/fields/user/query` Applies to all fields.
- `acf/fields/user/query/name={$name}` Applies to all fields of a specific name.
- `acf/fields/user/query/key={$key}` Applies to all fields of a specific key.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-fields-user-query/#example)

## Example

Link copied

This example demonstrates how to modify some of the User field query args. The `$args` returned are passed into a `WP_User_Query`. See the [WP\_User\_Query documentation](https://developer.wordpress.org/reference/classes/wp_user_query/) for a full list of supported parameters.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-fields-user-query/#functionsphp)

#### functions.php

Link copied

```php
<?php
add_filter('acf/fields/user/query', 'my_acf_fields_user_query', 10, 3);
function my_acf_fields_user_query( $args, $field, $post_id ) {

    // Show 40 users per AJAX call
    $args['number'] = 40;

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

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-fields-user-query/#related)

## Related

Link copied

- Filters: [acf/fields/post\_object/query](https://www.advancedcustomfields.com/resources/acf-fields-post_object-query/)
- Filters: [acf/fields/relationship/query](https://www.advancedcustomfields.com/resources/acf-fields-relationship-query/)
- Filters: [acf/fields/taxonomy/query](https://www.advancedcustomfields.com/resources/acf-fields-taxonomy-query/)
- Filters: [acf/fields/user/result](https://www.advancedcustomfields.com/resources/acf-fields-user-result/)
- Filters: [acf/load\_value](https://www.advancedcustomfields.com/resources/acf-load_value/)

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

[Got it](https://www.advancedcustomfields.com/resources/acf-fields-user-query/#)