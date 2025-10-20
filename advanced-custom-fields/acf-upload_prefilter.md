---
url: https://www.advancedcustomfields.com/resources/acf-upload_prefilter
scraped_at: 2025-10-20T02:21:32.631Z
---

# acf/upload\_prefilter

Last updated Feb 17, 2022

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-upload_prefilter/#description)

## Description

Link copied

Used to perform custom validation on an attachment and prevent it being uploaded.

Similar to the [acf/validate\_attachment](https://www.advancedcustomfields.com/resources/acf-validate_attachment/) filter, this hook can be used to prevent a file being uploaded via the WP media modal.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-upload_prefilter/#changelog)

## Changelog

Link copied

- Added in version 5.1.9

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-upload_prefilter/#parameters)

## Parameters

Link copied

```php
apply_filters( 'acf/upload_prefilter', $errors, $file, $field );
```

- `$errors` _(array)_ An array of error messages (strings) for the given attachment. Appending to this array will result in the attachment failing to upload, and the error message displayed to the client.
- `$file` _(array)_ An array containing the `$_FILE` data for the attachment about to be uploaded
- `$field` _(array)_ The field array containing all settings.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-upload_prefilter/#modifers)

## Modifers

Link copied

This filter provides modifiers to target specific fields. The following filter names are available:

- `acf/upload_prefilter` Applies to all fields.
- `acf/upload_prefilter/type={$type}` Applies to all fields of a specific type.
- `acf/upload_prefilter/name={$name}` Applies to all fields of a specific name.
- `acf/upload_prefilter/key={$key}` Applies to all fields of a specific key.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-upload_prefilter/#example)

## Example

Link copied

This example demonstrates how to restrict all uploads from ACF fields (Image, File, Gallery) to admin users only.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-upload_prefilter/#functionsphp)

#### functions.php

Link copied

```php
<?php
add_filter('acf/upload_prefilter', 'my_acf_upload_prefilter', 10, 3);
function my_acf_upload_prefilter( $errors, $file, $field ){

    // Check if not admin.
    if( !current_user_can('manage_options') ) {
        $errors[] = __( 'Only administrators may upload attachments' );
    }
    return $errors;
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

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-upload_prefilter/#related)

## Related

Link copied

- Filters: [acf/validate\_attachment](https://www.advancedcustomfields.com/resources/acf-validate_attachment/)
- Filters: [acf/validate\_value](https://www.advancedcustomfields.com/resources/acf-validate_value/)
- Filters: [acf/fields/relationship/result](https://www.advancedcustomfields.com/resources/acf-fields-relationship-result/)
- Filters: [acf/load\_field](https://www.advancedcustomfields.com/resources/acf-load_field/)
- Filters: [acf/fields/post\_object/result](https://www.advancedcustomfields.com/resources/acf-fields-post_object-result/)

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

[Got it](https://www.advancedcustomfields.com/resources/acf-upload_prefilter/#)