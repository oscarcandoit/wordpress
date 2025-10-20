---
url: https://www.advancedcustomfields.com/resources/acf-json-save_file_name
scraped_at: 2025-10-20T02:29:54.630Z
---

# acf/json/save\_file\_name

Last updated Apr 4, 2024

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-json-save_file_name/#description)

## Description

Link copied

Used to change the filename of files saved by the ACF local JSON feature.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-json-save_file_name/#changelog)

## Changelog

Link copied

- Added in version 6.2.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-json-save_file_name/#parameters)

## Parameters

Link copied

```php
apply_filters( 'acf/json/save_file_name', $filename, $post, $load_path );
```

- `$filename` _(string)_ The current filename being filtered.
- `$post` _(array)_ An array of settings for the field group, post type, taxonomy, or options page being saved.
- `$load_path` _(string)_ The path on the server that the JSON file was loaded from.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-json-save_file_name/#example)

## Example

Link copied

This example demonstrates how to change the filename of all JSON files to the ACF title.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-json-save_file_name/#functionsphp)

#### functions.php

Link copied

```php
<?php

function custom_acf_json_filename( $filename, $post, $load_path ) {
    $filename = str_replace(
        array(
            ' ',
            '_',
        ),
        array(
            '-',
            '-'
        ),
        $post['title']
    );

    $filename = strtolower( $filename ) . '.json';

    return $filename;
}
add_filter( 'acf/json/save_file_name', 'custom_acf_json_filename', 10, 3 );
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

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-json-save_file_name/#related)

## Related

Link copied

- Filters: [acf/load\_field](https://www.advancedcustomfields.com/resources/acf-load_field/)
- Filters: [acf/load\_value](https://www.advancedcustomfields.com/resources/acf-load_value/)
- Filters: [acf/update\_value](https://www.advancedcustomfields.com/resources/acf-update_value/)
- Features: [Local JSON](https://www.advancedcustomfields.com/resources/local-json/)
- Filters: [acf/fields/taxonomy/result](https://www.advancedcustomfields.com/resources/acf-fields-taxonomy-result/)

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

[Got it](https://www.advancedcustomfields.com/resources/acf-json-save_file_name/#)