---
url: https://www.advancedcustomfields.com/resources/field-settings
scraped_at: 2025-10-20T02:23:40.031Z
---

# Field Settings

Last updated Sep 21, 2022

[Link to heading#](https://www.advancedcustomfields.com/resources/field-settings/#overview)

## Overview

Link copied

Each field contains settings to determine where and how data is loaded and saved. These settings can be customized when [editing a field group](https://www.advancedcustomfields.com/resources/creating-a-field-group/ "Creating a Field Group"). All fields share some common settings, but also offer unique settings per field type. These unique settings can be found by reading more about the [field type](https://www.advancedcustomfields.com/resources/#field-types/). Below is a screenshot showing the available field settings for a text field.

![Screenshot of the settings available for a text field.](https://www.advancedcustomfields.com/wp-content/uploads/2014/11/acf-common-field-settings-1.png)

[Link to heading#](https://www.advancedcustomfields.com/resources/field-settings/#common-settings)

## Common Settings

Link copied

| Name | Description |
| --- | --- |
| Field Label | This is the label which appears on the edit page when entering a value. Required. |
| Field Name | This is the name used to save and load data from the database. This name must be a single word, no spaces, underscores and dashes allowed. Required. |
| Field Type | The type of field will change the settings available, the interface when entering data, and the value returned from the database. Required. |
| Instructions | This text appears on the edit page when entering a value. |
| Required | Required fields will cause validation to run when saving a post. When attempting to save an empty value to a required field, an error message will display. |
| Conditional Logic | Once enabled, more settings will appear to customize the logic which determines if the current field should be visible or not. Groups of conditional logic can be created to allow for multiple and/or statements. The available ‘toggle’ fields are limited to those which are of the type select, checkbox, true/false, radio. |
| Wrapper Attributes | These attributes will be used to create the wrapping DOM element for the field. Added in v5.0.0 |

[Link to heading#](https://www.advancedcustomfields.com/resources/field-settings/#customization)

## Customization

Link copied

Outside of the “Edit field group” UI, it is possible to modify a field’s settings via the [acf/load\_field](https://www.advancedcustomfields.com/resources/acf-load_field/) filter. This filter exposes the `$field` settings array for each field and allows customization to all settings.

This example shows how to modify a specific field (called ‘events’) via this filter to customize settings unavailable to the UI.

[Link to heading#](https://www.advancedcustomfields.com/resources/field-settings/#functionsphp)

#### functions.php

Link copied

```php
<?php

function my_acf_load_field( $field ) {

    // make required
    $field['required'] = true;


    // customize instructions with icon
    $field['instructions'] = '<i class="help" title="Instructions here"></i>';


    // customize wrapper element
    $field['wrapper']['id'] = 'my-custom-id';
    $field['wrapper']['data-jsify'] = '123';
    $field['wrapper']['title'] = 'Text here';


    // return
    return $field;

}

add_filter('acf/load_field/name=event', 'my_acf_load_field');

?>
```

```html
<!-- event field markup -->
<div id="my-custom-id" class="acf-field acf-field-text acf-field-5927ba4cecf19" data-jsify="123" title="Text here">
    <div class="acf-label">
        <label for="menu-item-acf-6363-field_5927ba4cecf19">
            Icon <i class="help" title="Instructions here"></i> <span class="acf-required">*</span>
        </label>
    </div>
    <div class="acf-input">
        ...
    </div>
</div>
```

Save

Save

Save

Save

Save

Save

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

[Link to heading#](https://www.advancedcustomfields.com/resources/field-settings/#related)

## Related

Link copied

- Basic: [get\_field\_object()](https://www.advancedcustomfields.com/resources/get_field_object/)
- Basic: [get\_field\_objects()](https://www.advancedcustomfields.com/resources/get_field_objects/)
- Choice: [Radio Button](https://www.advancedcustomfields.com/resources/radio-button/)
- Filters: [acf/load\_field](https://www.advancedcustomfields.com/resources/acf-load_field/)
- Functions: [acf\_form()](https://www.advancedcustomfields.com/resources/acf_form/)

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

[Got it](https://www.advancedcustomfields.com/resources/field-settings/#)