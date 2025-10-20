---
url: https://www.advancedcustomfields.com/resources/acf-fields-taxonomy-result
scraped_at: 2025-10-20T02:19:35.421Z
---

# acf/fields/taxonomy/result

Last updated Feb 17, 2022

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-fields-taxonomy-result/#description)

## Description

Link copied

Filters the text displayed for each term in the Taxonomy field when displayed as a Select or Multiselect dropdown.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-fields-taxonomy-result/#changelog)

## Changelog

Link copied

- Added in version 5.0.0

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-fields-taxonomy-result/#parameters)

## Parameters

Link copied

```php
apply_filters( 'acf/fields/taxonomy/result', $text, $term, $field, $post_id );
```

- `$text` _(string)_ The text displayed for this term (the term name).
- `$term` _(WP\_Term)_ The term object.
- `$field` _(array)_ The field array containing all settings.
- `$post_id` _(int\|string)_ The current post ID being edited.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-fields-taxonomy-result/#modifers)

## Modifers

Link copied

This filter provides modifiers to target specific fields. The following filter names are available:

- `acf/fields/taxonomy/result` Applies to all fields.
- `acf/fields/taxonomy/result/name={$name}` Applies to all fields of a specific name.
- `acf/fields/taxonomy/result/key={$key}` Applies to all fields of a specific key.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-fields-taxonomy-result/#example)

## Example

Link copied

This example demonstrates how to append the term slug to each result.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-fields-taxonomy-result/#functionsphp)

#### functions.php

Link copied

```php
<?php
add_filter('acf/fields/taxonomy/result', 'my_acf_fields_taxonomy_result', 10, 4);
function my_acf_fields_taxonomy_result( $text, $term, $field, $post_id ) {
    $text .= ' (' . $term->slug .  ')';
    return $text;
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

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-fields-taxonomy-result/#related)

## Related

Link copied

- Filters: [acf/fields/post\_object/result](https://www.advancedcustomfields.com/resources/acf-fields-post_object-result/)
- Filters: [acf/fields/taxonomy/query](https://www.advancedcustomfields.com/resources/acf-fields-taxonomy-query/)
- Filters: [acf/fields/relationship/result](https://www.advancedcustomfields.com/resources/acf-fields-relationship-result/)
- Filters: [acf/load\_value](https://www.advancedcustomfields.com/resources/acf-load_value/)
- Filters: [acf/format\_value](https://www.advancedcustomfields.com/resources/acf-format_value/)

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

[Got it](https://www.advancedcustomfields.com/resources/acf-fields-taxonomy-result/#)