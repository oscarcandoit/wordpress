---
url: https://www.advancedcustomfields.com/resources/acf-validate_save_post
scraped_at: 2025-10-20T02:27:02.291Z
---

# acf/validate\_save\_post

Last updated Sep 29, 2023

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-validate_save_post/#description)

## Description

Link copied

Fires when validating the `$_POST` data of a submitted form.

Used to add or remove validation errors controlling whether or not the submitted data will be saved.

Please note this is a generic action. If you are looking to validate a _specific_ field value, please use the [acf/validate\_value](https://www.advancedcustomfields.com/resources/acf-validate_value/) filter instead.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-validate_save_post/#changelog)

## Changelog

Link copied

- Added in version 5.0.0

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-validate_save_post/#example)

## Example

Link copied

This example demonstrates how to bypass validation for an administrator, and also to require a custom input value. See the [Notes](https://www.advancedcustomfields.com/resources/acf-validate_save_post/#notes) section below for additional information on the functions used.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-validate_save_post/#functionsphp)

#### functions.php

Link copied

```php
add_action('acf/validate_save_post', 'my_acf_validate_save_post');
function my_acf_validate_save_post() {

    // Remove all errors if the user is an administrator.
    if( current_user_can('manage_options') ) {
        acf_reset_validation_errors();
    }

    // Require custom input value.
    if( empty($_POST[‘acf’][‘field_xxxxxx’] ) ) {
        acf_add_validation_error( 'acf[field_xxxxxx]', 'Please check this input to proceed' );
    }
}
```

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-validate_save_post/#notes)

## Notes

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-validate_save_post/#additional-functions)

### Additional functions

Link copied

The following additional functions are made available during this action.

- **acf\_add\_validation\_error()**


Adds a validation error and prevents the submitted data from being saved.


```php
acf_add_validation_error($input, [$message])
```


  - `$input` _(string)_ _(Required)_ The input used here should be an ACF field key, rather than the field name.
  - `$message` _(string)_ _(Optional)_ The error message to display.
- **acf\_reset\_validation\_errors()**


Removes all validation errors and allows the submitted data to be saved.


```php
acf_reset_validation_errors()
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

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-validate_save_post/#related)

## Related

Link copied

- Actions: [acf/save\_post](https://www.advancedcustomfields.com/resources/acf-save_post/)
- Filters: [acf/validate\_value](https://www.advancedcustomfields.com/resources/acf-validate_value/)
- Filters: [acf/validate\_attachment](https://www.advancedcustomfields.com/resources/acf-validate_attachment/)
- Filters: [acf/upload\_prefilter](https://www.advancedcustomfields.com/resources/acf-upload_prefilter/)
- Actions: [acf/init](https://www.advancedcustomfields.com/resources/acf-init/)

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

[Got it](https://www.advancedcustomfields.com/resources/acf-validate_save_post/#)