---
url: https://www.advancedcustomfields.com/resources/acf_get_fields
scraped_at: 2025-10-20T02:28:12.373Z
---

# acf\_get\_fields()

Last updated Jan 29, 2024

[Link to heading#](https://www.advancedcustomfields.com/resources/acf_get_fields/#description)

## Description

Link copied

Retrieves all the fields from a specific field group, returning them as an array of field objects. This function should not be confused with [get\_fields()](https://www.advancedcustomfields.com/resources/get_fields/), which returns an array of field values for a specific post rather than a field group.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf_get_fields/#parameters)

## Parameters

Link copied

```php
acf_get_fields( $parent );
```

- `$parent` _(mixed)_ _(Required)_ The field group’s ID or key.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf_get_fields/#examples)

## Examples

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/acf_get_fields/#basic-usage)

### Basic usage

Link copied

This example demonstrates how to return an array of fields for a given parent. Note that you will have to replace the field group key shown below with your own.

```php
acf_get_fields('group_6525b4469c71d');
```

[Link to heading#](https://www.advancedcustomfields.com/resources/acf_get_fields/#advanced-usage)

### Advanced usage

Link copied

The following example demonstrates how to retrieve the values in the `foreach` for every field contained in the field group and then output them for viewing.

```php
$specifications_group_id = 'group_6525b4469c71d'; // Replace with your group ID
$specifications_fields      = array();

$fields = acf_get_fields( $specifications_group_id );

foreach ( $fields as $field ) {
    $field_value = get_field( $field['name'] );

    if ( ! empty( $field_value ) ) {
        $specifications_fields[ $field['name'] ] = $field_value;
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

[Link to heading#](https://www.advancedcustomfields.com/resources/acf_get_fields/#related)

## Related

Link copied

- Basic: [acf\_get\_field\_groups()](https://www.advancedcustomfields.com/resources/acf_get_field_groups/)
- Basic: [get\_field()](https://www.advancedcustomfields.com/resources/get_field/)
- Functions: [update\_field()](https://www.advancedcustomfields.com/resources/update_field/)
- Filters: [acf/load\_value](https://www.advancedcustomfields.com/resources/acf-load_value/)
- Basic: [get\_field\_object()](https://www.advancedcustomfields.com/resources/get_field_object/)

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

[Got it](https://www.advancedcustomfields.com/resources/acf_get_fields/#)