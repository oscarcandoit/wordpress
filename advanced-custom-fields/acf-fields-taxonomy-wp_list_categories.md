---
url: https://www.advancedcustomfields.com/resources/acf-fields-taxonomy-wp_list_categories
scraped_at: 2025-10-20T02:19:31.931Z
---

# acf/fields/taxonomy/wp\_list\_categories

Last updated Feb 17, 2022

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-fields-taxonomy-wp_list_categories/#description)

## Description

Link copied

Filters the query `$args` used by `WP_Term_Query` to display terms in the Taxonomy field when displayed as a Radio or Checkbox list.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-fields-taxonomy-wp_list_categories/#changelog)

## Changelog

Link copied

- Added in version 4.0.0

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-fields-taxonomy-wp_list_categories/#parameters)

## Parameters

Link copied

```php
apply_filters( 'acf/fields/taxonomy/wp_list_categories', $args, $field );
```

- `$args` _(array)_ The query args. See [wp\_list\_categories()](https://developer.wordpress.org/reference/functions/wp_list_categories/) for available args.
- `$field` _(array)_ The field array containing all settings.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-fields-taxonomy-wp_list_categories/#modifers)

## Modifers

Link copied

This filter provides modifiers to target specific fields. The following filter names are available:

- `acf/fields/taxonomy/wp_list_categories` Applies to all fields.
- `acf/fields/taxonomy/wp_list_categories/name={$name}` Applies to all fields of a specific name.
- `acf/fields/taxonomy/wp_list_categories/key={$key}` Applies to all fields of a specific key.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-fields-taxonomy-wp_list_categories/#example)

## Example

Link copied

This example demonstrates how to modify some of the Taxonomy field wp\_list\_categories args.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-fields-taxonomy-wp_list_categories/#functionsphp)

#### functions.php

Link copied

```php
<?php
add_filter('acf/fields/taxonomy/wp_list_categories', 'my_acf_fields_taxonomy_query', 10, 2);
function my_acf_fields_taxonomy_query( $args, $field ) {

    // Order by most used.
    $args['orderby'] = 'count';
    $args['order'] = 'DESC';

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

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-fields-taxonomy-wp_list_categories/#related)

## Related

Link copied

- Filters: [acf/fields/taxonomy/query](https://www.advancedcustomfields.com/resources/acf-fields-taxonomy-query/)
- Filters: [acf/fields/taxonomy/result](https://www.advancedcustomfields.com/resources/acf-fields-taxonomy-result/)
- Filters: [acf/fields/relationship/query](https://www.advancedcustomfields.com/resources/acf-fields-relationship-query/)
- Filters: [acf/fields/post\_object/query](https://www.advancedcustomfields.com/resources/acf-fields-post_object-query/)
- Filters: [acf/fields/relationship/result](https://www.advancedcustomfields.com/resources/acf-fields-relationship-result/)

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

[Got it](https://www.advancedcustomfields.com/resources/acf-fields-taxonomy-wp_list_categories/#)