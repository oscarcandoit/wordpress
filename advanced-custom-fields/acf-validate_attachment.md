---
url: https://www.advancedcustomfields.com/resources/acf-validate_attachment
scraped_at: 2025-10-20T02:21:37.165Z
---

# acf/validate\_attachment

Last updated Feb 17, 2022

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-validate_attachment/#description)

## Description

Link copied

Used to perform custom validation on an attachment and prevent it being uploaded or selected for a specific field.

Similar to the [acf/upload\_prefilter](https://www.advancedcustomfields.com/resources/acf-upload_prefilter/) filter, this filter can be used to prevent an upload, however, it can also be used to prevent an attachment being selected from a WP media modal.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-validate_attachment/#changelog)

## Changelog

Link copied

- Added in version 5.2.8
- Added `context` parameter in version 5.6.3

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-validate_attachment/#parameters)

## Parameters

Link copied

```php
apply_filters( 'acf/validate_attachment', $errors, $file, $attachment, $field, $context );
```

- `$errors` _(array)_ An array of error messages (strings) for the given attachment. Appending to this array will result in the attachment failing to upload, and the error message displayed to the client.
- `$file` _(array)_ An array of generic file data including type, width, height and size
- `$attachment` _(array)_ The attachment being uploaded/displayed. This data changes depending on context
- `$field` _(array)_ The field array containing all settings.
- `$context` _(string)_ Description of the current context: _upload_, _basic\_upload_ (when uploading) or _prepare_ (when viewing). Added in 5.6.3

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-validate_attachment/#modifers)

## Modifers

Link copied

This filter provides modifiers to target specific fields. The following filter names are available:

- `acf/validate_attachment` Applies to all fields.
- `acf/validate_attachment/type={$type}` Applies to all fields of a specific type.
- `acf/validate_attachment/name={$name}` Applies to all fields of a specific name.
- `acf/validate_attachment/key={$key}` Applies to all fields of a specific key.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-validate_attachment/#example)

## Example

Link copied

This example demonstrates how to validate the file name of all attachments. If the attachment’s file name does not begin with the string "acf-", an error message will be displayed causing the upload/selection to fail.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-validate_attachment/#functionsphp)

#### functions.php

Link copied

```php
<?php
add_filter('acf/validate_attachment', 'my_acf_validate_attachment', 10, 5);
function my_acf_validate_attachment( $errors, $file, $attachment, $field, $context ){

    // Check first 4 characters of the attachment name.
    if( substr($attachment['name'], 0, 4) !== 'acf-' ) {
        $errors[] = __( 'File name must begin with "acf-"' );
    }
    return $errors;
}
```

[![An error message displayed in the WP media modal preventing an attachment from being selected.](https://www.advancedcustomfields.com-content/uploads/2017/08/acf-validate-attachment-screenshot.png)](https://www.advancedcustomfields.com-content/uploads/2017/08/acf-validate-attachment-screenshot.png) An error message displayed in the WP media modal preventing an attachment from being selected.

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

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-validate_attachment/#related)

## Related

Link copied

- Filters: [acf/upload\_prefilter](https://www.advancedcustomfields.com/resources/acf-upload_prefilter/)
- Filters: [acf/validate\_value](https://www.advancedcustomfields.com/resources/acf-validate_value/)
- Filters: [acf/prepare\_field](https://www.advancedcustomfields.com/resources/acf-prepare_field/)
- Filters: [acf/load\_field](https://www.advancedcustomfields.com/resources/acf-load_field/)
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

[Got it](https://www.advancedcustomfields.com/resources/acf-validate_attachment/#)