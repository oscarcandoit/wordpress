---
url: https://www.advancedcustomfields.com/resources/integrating-custom-field-types
scraped_at: 2025-10-20T03:55:05.530Z
attempt: 1
---

# Integrating Custom Field Types With the WordPress REST API

Last updated Oct 13, 2022

[Link to heading#](https://www.advancedcustomfields.com/resources/integrating-custom-field-types/#integrating-custom-field-types-with-the-wordpress-rest-api)

## Integrating Custom Field Types With the WordPress REST API

Link copied

Since version 5.11, Advanced Custom Fields has included support for viewing and updating custom fields [via the WordPress REST API](https://www.advancedcustomfields.com/resources/wp-rest-api-integration/). The integration works for the default ACF field types, as well as the majority of [custom field types](https://www.advancedcustomfields.com/resources/creating-a-new-field-type/) registered by other plugins. However, depending on how the custom field types are registered, some extra code might be required to fully integrate them with the REST API.

This doc will cover adding a custom field type to the REST API, adding or modifying a field type schema, and removing a field type from the REST API.

[Link to heading#](https://www.advancedcustomfields.com/resources/integrating-custom-field-types/#adding-a-custom-field-type-to-the-rest-api)

## Adding a Custom Field Type to the REST API

Link copied

Field types registered by first creating a new field type class that extends the `acf_field` class, and then registering that class using the `acf_register_field_type()` function, should work with the REST API automatically. However, this is only true provided that the new field type class extending `acf_field` does not set the `show_in_rest` property to `false`.

```php php
class hfm_font_size extends acf_field {

    // Set $show_in_rest to true to allow the field to show up in the REST API.
    // This field is also set as true by default in the acf_field class.
    public $show_in_rest = false;

    ...
```

For field types that are not registered with `acf_register_field_type()`, such as field types that just construct themselves inside the `acf/include_field_types` action hook, it is possible to include them in the REST API by using the `acf/rest/get_fields` filter as shown below:

```php php
add_filter( 'acf/rest/get_fields', function ( $fields, $resource, $http_method ) {
    if ( ! is_array( $fields ) ) {
        return $fields;
    }

    // Get our field type by the field name.
    $field_type = acf_get_field_type( 'font_size' );

    // If our field hasn't been registered and initialized by ACF, do so now.
    if ( ! $field_type instanceof acf_field ) {
        // Initialize the class containing our custom field type. If there are any constructor args, you will need to pass those in as well.
        $field = new hfm_font_size();
        acf_register_field_type( $field );
    }

    // Get the field array (by the field name) and add it to the array of fields supported by REST.
    $fields[] = acf_get_field( 'font_size');

    return $fields;
}, 10, 3 );
```

The above example adds a custom `font_size` field type to the REST API. It does this by retrieving the field type from ACF, constructing the `hfm_font_size` class that extends `acf_field` if it wasn’t already, and then adds the field to the array of fields that are available to the REST API.

[Link to heading#](https://www.advancedcustomfields.com/resources/integrating-custom-field-types/#adding-or-updating-schema-for-custom-field-types)

## Adding or Updating Schema for Custom Field Types

Link copied

By default, ACF will add a basic schema for custom field types extending the `acf_field` class. It does this in the `acf_field::get_rest_schema()` method, which can be overridden in the class extending `acf_field`:

```php php
class hfm_font_size extends acf_field {

    // override the default acf_field::get_rest_schema() method
    public function get_rest_schema( array $field ) {
        $schema = array(
            'type'     => array( 'int', 'null' ),
            'required' => true,
        );

        if ( isset( $field['default_value'] ) && '' !== $field['default_value'] ) {
            $schema['default'] = $field['default_value'];
        }

        return $schema;
    }

    …
}
```

Additionally, you can set the schema by using the `acf/rest/get_field_schema` filter. For more information on that, see “Controlling a Field’s Schema” in [Extending the REST API System](https://www.advancedcustomfields.com/resources/rest-api/#extending-the%20rest%20api%20system).

[Link to heading#](https://www.advancedcustomfields.com/resources/integrating-custom-field-types/#excluding-a-field-type-from-the-rest-api)

## Excluding a Field Type From the REST API

Link copied

If the field type was registered with `acf_register_field_type()` and extends the `acf_field` class, you can use the `$show_in_rest` property to prevent that field type from showing up in the REST API:

```php php
class hfm_font_size extends acf_field {

    // Set $show_in_rest to false to prevent it from showing up in the REST API.
    public $show_in_rest = false;

    ...
}
```

Much like registering fields, it is also possible to exclude a field type using the `acf/rest/get_fields` filter:

```php php
add_filter( 'acf/rest/get_fields', function ( $fields, $resource, $http_method ) {
    if ( ! is_array( $fields ) ) {
        return $fields;
    }

    foreach ( $fields as $field_key => $field_array ) {
        if ( 'font_size'  === $field_array['name'] ) {
            unset( $fields[ $field_key ] );
        }
    }

    return $fields;
}, 10, 3 );
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

[Link to heading#](https://www.advancedcustomfields.com/resources/integrating-custom-field-types/#related)

## Related

Link copied

- Features: [WP REST API Integration](https://www.advancedcustomfields.com/resources/wp-rest-api-integration/)
- Guides: [Creating a new field type](https://www.advancedcustomfields.com/resources/creating-a-new-field-type/)
- Guides: [Upgrade Guide – Version 4](https://www.advancedcustomfields.com/resources/upgrade-guide-version-4/)
- Field Types: [User](https://www.advancedcustomfields.com/resources/user/)
- Guides: [ACF Security Principles](https://www.advancedcustomfields.com/resources/acf-security-principles/)

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

[Got it](https://www.advancedcustomfields.com/resources/integrating-custom-field-types/#)