---
url: https://www.advancedcustomfields.com/resources/acf-fields-user-result
scraped_at: 2025-10-20T02:25:53.225Z
---

# acf/fields/user/result

Last updated Jul 14, 2023

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-fields-user-result/#description)

## Description

Link copied

Filters the text displayed for each user.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-fields-user-result/#parameters)

## Parameters

Link copied

```php
apply_filters( 'acf/fields/user/result', $text, $user, $field, $post_id );
```

- `$text` _(string)_ The text displayed for this user.
- `$user` _(WP\_User)_ The user object.
- `$field` _(array)_ The field array containing all settings.
- `$post_id` _(WP\_Post)_ The post ID where the value is saved.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-fields-user-result/#modifiers)

## Modifiers

Link copied

This filter provides modifiers to target specific fields. The following filter names are available:

- `acf/fields/user/result` Applies to all fields.
- `acf/fields/user/result/name={$name}` Applies to all fields of a specific name.
- `acf/fields/user/result/key={$key}` Applies to all fields of a specific key.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-fields-user-result/#example)

## Example

Link copied

This example demonstrates how to return user meta, in this case the user’s `preferred_name_field` appended to the standard result.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-fields-user-result/#functionsphp)

#### functions.php

Link copied

```php
<?php
add_filter('acf/fields/user/result/name=subscriber_field_name', 'my_acf_fields_user_result', 10, 4);

function my_acf_fields_user_result( $text, $user, $field, $post_id ) {

    //Retrieve the preferred name field value from user
    $recipient = get_field( 'preferred_name_field', 'user_' . $user->ID );

    $text .= ' (' . $recipient . ')';

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

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-fields-user-result/#related)

## Related

Link copied

- Filters: [acf/fields/post\_object/result](https://www.advancedcustomfields.com/resources/acf-fields-post_object-result/)
- Filters: [acf/fields/relationship/result](https://www.advancedcustomfields.com/resources/acf-fields-relationship-result/)
- Filters: [acf/fields/taxonomy/result](https://www.advancedcustomfields.com/resources/acf-fields-taxonomy-result/)
- Filters: [acf/fields/user/query](https://www.advancedcustomfields.com/resources/acf-fields-user-query/)
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

[Got it](https://www.advancedcustomfields.com/resources/acf-fields-user-result/#)