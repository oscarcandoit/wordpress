---
url: https://www.advancedcustomfields.com/resources/acf-fields-post_object-query
scraped_at: 2025-10-20T02:19:15.035Z
---

# acf/fields/post\_object/query

Last updated Feb 17, 2022

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-fields-post_object-query/#description)

## Description

Link copied

Filters the query `$args` used by `WP_Query` to display posts in the Post Object field.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-fields-post_object-query/#changelog)

## Changelog

Link copied

- Added in version 4.1.2

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-fields-post_object-query/#parameters)

## Parameters

Link copied

```php
apply_filters( 'acf/fields/post_object/query', $args, $field, $post_id );
```

- `$args` _(array)_ The query args. See [WP\_Query](https://developer.wordpress.org/reference/classes/wp_query/) for available args.
- `$field` _(array)_ The field array containing all settings.
- `$post_id` _(int\|string)_ The current post ID being edited.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-fields-post_object-query/#modifers)

## Modifers

Link copied

This filter provides modifiers to target specific fields. The following filter names are available:

- `acf/fields/post_object/query` Applies to all fields.
- `acf/fields/post_object/query/name={$name}` Applies to all fields of a specific name.
- `acf/fields/post_object/query/key={$key}` Applies to all fields of a specific key.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-fields-post_object-query/#example)

## Example

Link copied

This example demonstrates how to modify some of the Post Object query args.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-fields-post_object-query/#functionsphp)

#### functions.php

Link copied

```php
<?php
add_filter('acf/fields/post_object/query', 'my_acf_fields_post_object_query', 10, 3);
function my_acf_fields_post_object_query( $args, $field, $post_id ) {

    // Show 40 posts per AJAX call.
    $args['posts_per_page'] = 40;

    // Restrict results to children of the current post only.
    $args['post_parent'] = $post_id;

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

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-fields-post_object-query/#related)

## Related

Link copied

- Filters: [acf/fields/relationship/query](https://www.advancedcustomfields.com/resources/acf-fields-relationship-query/)
- Filters: [acf/fields/post\_object/result](https://www.advancedcustomfields.com/resources/acf-fields-post_object-result/)
- Filters: [acf/fields/taxonomy/query](https://www.advancedcustomfields.com/resources/acf-fields-taxonomy-query/)
- Filters: [acf/fields/relationship/result](https://www.advancedcustomfields.com/resources/acf-fields-relationship-result/)
- Filters: [acf/fields/user/query](https://www.advancedcustomfields.com/resources/acf-fields-user-query/)

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

[Got it](https://www.advancedcustomfields.com/resources/acf-fields-post_object-query/#)