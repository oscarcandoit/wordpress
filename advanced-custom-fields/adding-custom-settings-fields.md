---
url: https://www.advancedcustomfields.com/resources/adding-custom-settings-fields
scraped_at: 2025-10-20T02:25:03.176Z
---

# Adding Custom Settings to Fields

Last updated Apr 24, 2023

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-custom-settings-fields/#overview)

## Overview

Link copied

Each ACF field type may contain several different settings that can be used to customize the appearance and functionality of the field. There are two main types of these settings: global and type-specific.

Global field settings are registered once and show up for every field type. An example of a global setting would be the “Field Name” setting – this shows up for every ACF field as it is necessary for the fields to function.

Type-specific settings are registered for each field type and can be used for more granular control for a specific field. For example, the Image field has type-specific settings for the min/max image size, as well as the allowed file types for the image.

This doc will explain how you can add custom field settings to both existing field types and your own custom field types.

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-custom-settings-fields/#change-log)

### Changelog

Link copied

- Field type settings have been moved into [different tabs](https://www.advancedcustomfields.com/resources/adding-custom-settings-fields/#adding-settings%20for%20a%20specific%20field%20type) in version 6.0
- Field type settings are now rendered in [div tags instead of tr tags](https://www.advancedcustomfields.com/resources/adding-custom-settings-fields/#acf_render_field_setting) in version 6.0
- Instructions provided to field type settings are now [rendered as tooltips](https://www.advancedcustomfields.com/resources/adding-custom-settings-fields/#field-setting-instructions) in version 6.0
- `acf_render_field_setting()` function added in version 5.0

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-custom-settings-fields/#global-settings)

## Adding a Global Field Setting

Link copied

As mentioned above, global field settings are displayed for every field type. In ACF 6, these settings are displayed on the “General” tab for each field.

![A screenshot of the new global field setting.](https://www.advancedcustomfields.com/wp-content/uploads/2022/09/global-field-setting.png)

The following example shows how to add a new setting called “Admin Only” which will add a true/false toggle to all fields, allowing them to be hidden from non-admin users.

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-custom-settings-fields/#1-adding-the-setting)

### 1\. Adding the Setting

Link copied

Global settings can be added using the `acf/render_field_settings` action hook and the `acf_render_field_setting()` function. The following snippet will add a global setting to the “General” tab for all field types. Please note that the third parameter for `acf_render_field_setting()` is set to `true` to acknowledge this is a global setting.

```php
function my_admin_only_render_field_settings( $field ) {
    acf_render_field_setting( $field, array(
        'label'        => __( 'Admin Only?', 'my-textdomain' ),
        'instructions' => '',
        'name'         => 'admin_only',
        'type'         => 'true_false',
        'ui'           => 1,
    ), true ); // If adding a setting globally, you MUST pass true as the third parameter!
}
add_action( 'acf/render_field_settings', 'my_admin_only_render_field_settings' );
```

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-custom-settings-fields/#2-using-the-setting)

### 2\. Using the Setting

Link copied

With the new “Admin Only?” setting added, we can hook into any part of ACF and use the setting. The following code will hook into the `acf/prepare_field` filter which is run just before a field is rendered into a form. This will allow us to check if the current user is an administrator, and if not, prevent the field from being displayed:

```php
function my_admin_only_prepare_field( $field ) {
    // Bail early if no 'admin_only' setting or if set to false.
    if ( empty( $field['admin_only'] ) ) {
        return $field;
    }

    // Prevent field from displaying if current user is not an admin.
    if ( ! current_user_can( 'manage_options' ) ) {
        return false;
    }

    // Return the original field otherwise.
    return $field;
}
add_filter( 'acf/prepare_field', 'my_admin_only_prepare_field' );
```

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-custom-settings-fields/#3-testing-the-setting)

### 3\. Testing the Setting

Link copied

With the above code added to the `functions.php` file and a field using the “Admin Only?” setting, we can now login with either an administrator or editor account and note the field’s existence!

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-custom-settings-fields/#type-specific-fields)

## Adding Settings for a Specific Field Type

Link copied

Field settings can be added or restricted to individual field types (text, image, etc.). In ACF 6.0 and above, these settings can also be shown in specific tabs within a field type (General, Validation, Presentation, or Conditional Logic).

The following action hooks can be used for adding field settings to these tabs:

- `acf/render_field_settings/type={type}` (legacy action for the “General” tab – can be used in ACF 5 to add field type-specific settings)
- `acf/render_field_general_settings/type={type}` (for adding settings to the “General” tab)
- `acf/render_field_validation_settings/type={type}` (for adding settings to the “Validation” tab)
- `acf/render_field_presentation_settings/type={type}` (for adding settings to the “Presentation” tab)
- `acf/render_field_conditional_logic_settings/type={type}` (for adding settings to the “Conditional Logic” tab)

These filters are also applied on the `acf_field` base class, so if you have a custom field type that extends `acf_field`, you can instead just add one or more of the following methods to your custom class:

- `render_field_settings()`
- `render_field_general_settings()`
- `render_field_validation_settings()`
- `render_field_presentation_settings()`
- `render_field_conditional_logic_settings()`

The following example will add a new “Exclude Words” setting to the “Validation” tab of the textarea field type. This adds a text input which we’ll later use to store a list of words that shouldn’t be allowed in textareas.

![A screenshot of the new field type specific setting.](https://www.advancedcustomfields.com/wp-content/uploads/2022/09/type-specific-field-setting.png)

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-custom-settings-fields/#1-adding-the-setting)

### 1\. Adding the Setting

Link copied

Since this example is adding a setting to the “Validation” tab, we’ll be using the `acf/render_field_validation_settings/type={$type}` action hook to render the setting.

Please note that the third parameter for the `acf_render_field_setting()` function is excluded – making it specific to the field, rather than a global setting as shown above.

```php
function my_textarea_render_field_settings( $field ) {
    acf_render_field_setting( $field, array(
        'label'        => __( 'Exclude Words', 'my-textdomain' ),
        'instructions' => __( 'Enter words separated by a comma', 'my-textdomain' ),
        'name'         => 'exclude_words',
        'type'         => 'text',
    ) );
}
add_action( 'acf/render_field_validation_settings/type=textarea', 'my_textarea_render_field_settings' );
```

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-custom-settings-fields/#2-using-the-setting)

### 2\. Using the Setting

Link copied

With the new “Exclude Words” setting added and a new textarea field added (using the setting), we can hook into any part of ACF and use the setting. The following code will hook into the `acf/validate_value` filter which is run during validation. This will allow us to check if the current value contains any words from the exclude list and notify the user via a validation error message.

```php
function my_textarea_validate_value( $valid, $value, $field, $input ) {
    // Bail early if the field is already invalid.
    if ( ! $valid ) {
        return $valid;
    }

    // Bail early if the "Exclude Words" setting is not set.
    if ( empty( $field['exclude_words'] ) ) {
        return $valid;
    }

    // Explode the words into an array we can loop over.
    $words = explode( ',', $field['exclude_words'] );
    $words = array_map( 'trim', $words ); // Trim white spaces.
    $words = array_values( $words ); // Remove empty values.

    foreach( $words as $word ) {
        // Check if the word exists.
        if( stripos( $value, $word ) !== false ) {
            $valid = sprintf( __( 'Value must not include "%s"', 'my-textdomain' ), $word );
            break;
        }
    }

    return $valid;
}
add_filter( 'acf/validate_value/type=textarea', 'my_textarea_validate_value', 10, 4 );
```

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-custom-settings-fields/#3-testing-the-setting)

### 3\. Testing the Setting

Link copied

With the above code added to the `functions.php` file and a field using the ‘exclude\_words’ setting, we can now edit a post and attempt to save a value.

![A screenshot of the custom error message added above.](https://www.advancedcustomfields.com/wp-content/uploads/2022/09/custom-validation.png)

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-custom-settings-fields/#custom-field-setting-tab)

### Adding a Custom Field Setting Tab

Link copied

With our new tab format introduced in ACF 6.0, plugins which add settings to fields can add do so with the new `acf/field_group/additional_field_settings_tabs` filter introduced in ACF 6.1.

For example, to add a new Tab called ‘My Settings’ to every field, you’d use:

```php
add_filter( 'acf/field_group/additional_field_settings_tabs', function ( $tabs ) {
    $tabs['my-settings'] = 'My Settings';

    return $tabs;
} );
```

To add a field to this new tab you would use the `acf/field_group/render_field_settings_tab/$tab-key` filter::

```php
add_action( 'acf/field_group/render_field_settings_tab/my-settings', function ( $field ) {
    acf_render_field_setting(
        $field,
        array(
            'label'        => 'Admin Only?',
            'instructions' => '',
            'name'         => 'admin_only',
            'type'         => 'true_false',
            'ui'           => 1,
        ),
        true
    );
} );
```

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-custom-settings-fields/#custom-group-settings-tab)

### Adding a Custom Tab to the Field Group Settings

Link copied

It is also possible to add a custom settings tab to the ‘Settings’ meta box at the bottom of the Field Group editor screen using the `acf/field_group/additional_group_settings_tabs` filter in the same way as above.

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-custom-settings-fields/#upgrade-existing-field-settings)

## Upgrading Existing Field Settings to ACF 6

Link copied

Custom field settings that were added using the `acf/render_field_settings` or `acf/render_field_settings/type={type}` action hooks will continue to work in ACF 6, with the settings appearing on the “General” tab for any fields those settings were added to.

However, there are some changes in ACF 6 that may require some additional code.

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-custom-settings-fields/#moving-field-setting)

### Moving an Existing Field Setting into a Different Tab

Link copied

If you want to move your custom field setting to a different tab and also support users who may still be on ACF 5, you’ll likely need to add some code to make sure that the setting is registered differently on ACF 5 and 6 to prevent the setting from showing up twice.

One way to do that would be to update your existing field setting code to return early if on ACF 6.0 or above.

```php
function render_field_settings( $field ) {
    // We’re on ACF 6.0 or above, so we don’t need to register the setting here.
    if ( version_compare( ACF_MAJOR_VERSION, '6.0', '>=' ) ) {
        return;
    }

    // Rest of field settings code.
}
```

You could then add a separate function that hooks on one of the tab-specific action hooks as mentioned [above](https://www.advancedcustomfields.com/resources/adding-custom-settings-fields/#adding-settings%20for%20a%20specific%20field%20type).

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-custom-settings-fields/#acf_render_field_setting)

### Changes to acf\_render\_field\_setting() in ACF 6

Link copied

In ACF 5, field settings were rendered as table rows inside a parent table with a class of `.acf-table`. In ACF 6 and above, field type settings are no longer rendered inside of a table.

As a result, the `acf_render_field_setting()` function has been updated to render the field settings created by that function inside of `<div>` elements by default.

This likely won’t cause any issues if you’re using `acf_render_field_setting()` in one of the action hooks mentioned above or in a class that extends `acf_field`.

While not recommended, it is possible to use the `acf_render_field_setting()` function outside of those action hooks. In that case, we would recommend checking any settings created with that function to ensure that they are displayed as expected, and updating your code as necessary.

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-custom-settings-fields/#field-setting-instructions)

### Changes to Field Setting Instructions in ACF 6

Link copied

In ACF 6, the value of the `instructions` parameter passed to `acf_render_field_settings()` is now rendered as a tooltip to reduce UI clutter.

![A tooltip in ACF 6.](https://www.advancedcustomfields.com/wp-content/uploads/2022/09/acf-tooltip-instructions.png)

If you would rather display the `instructions` inline with the field setting (such as in ACF 5), you can do so by changing the `instructions` parameter to `hint`:

```php
function my_textarea_render_field_settings( $field ) {
    acf_render_field_setting( $field, array(
        'label' => __( 'Exclude Words', 'my-textdomain' ),
        'hint'  => __( 'Enter words separated by a comma', 'my-textdomain' ),
        'name'  => 'exclude_words',
        'type'  => 'text',
    ) );
}
add_action( 'acf/render_field_validation_settings/type=textarea', 'my_textarea_render_field_settings' );
```

This will render the provided hint text underneath the field setting:

![An ACF field setting hint.](https://www.advancedcustomfields.com/wp-content/uploads/2022/09/acf-hint-instructions.png)

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-custom-settings-fields/#conclusion)

## Conclusion

Link copied

Adding extra field settings in ACF is easy and the possibilities are endless!

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

[Link to heading#](https://www.advancedcustomfields.com/resources/adding-custom-settings-fields/#related)

## Related

Link copied

- Actions: [acf/render\_field](https://www.advancedcustomfields.com/resources/acf-render_field/)
- Getting Started: [Field Settings](https://www.advancedcustomfields.com/resources/field-settings/)
- Guides: [Creating a new field type](https://www.advancedcustomfields.com/resources/creating-a-new-field-type/)
- Features: [Conditional Logic](https://www.advancedcustomfields.com/resources/conditional-logic/)
- Functions: [acf\_register\_block\_type()](https://www.advancedcustomfields.com/resources/acf_register_block_type/)

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

[Got it](https://www.advancedcustomfields.com/resources/adding-custom-settings-fields/#)