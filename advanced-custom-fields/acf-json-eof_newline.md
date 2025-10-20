---
url: https://www.advancedcustomfields.com/resources/acf-json-eof_newline
scraped_at: 2025-10-20T02:29:49.908Z
---

# acf/json/eof\_newline

Last updated Apr 4, 2024

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-json-eof_newline/#description)

## Description

Link copied

Used to change the newline character at the end of JSON files.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-json-eof_newline/#changelog)

## Changelog

Link copied

- Added in version 6.2.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-json-eof_newline/#parameters)

## Parameters

Link copied

```php
apply_filters( 'acf/json/eof_newline', $newline_character );
```

- `$newline_character` _(string)_ The current newline character, `PHP_EOL` by default.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-json-eof_newline/#example)

## Example

Link copied

This example demonstrates how to change the newline character at the end of JSON files.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-json-eof_newline/#functionsphp)

#### functions.php

Link copied

```php
<?php

function custom_acf_json_eof_newline( $newline_character ) {
    return "\r\n";
}
add_filter( 'acf/json/eof_newline', 'custom_acf_json_eof_newline' );
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

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-json-eof_newline/#related)

## Related

Link copied

- Filters: [acf/json/save\_file\_name](https://www.advancedcustomfields.com/resources/acf-json-save_file_name/)
- Filters: [acf/update\_value](https://www.advancedcustomfields.com/resources/acf-update_value/)
- Filters: [acf/load\_field](https://www.advancedcustomfields.com/resources/acf-load_field/)
- Filters: [acf/pre\_save\_post](https://www.advancedcustomfields.com/resources/acf-pre_save_post/)
- Filters: [acf/shortcode/prevent\_access](https://www.advancedcustomfields.com/resources/acf-shortcode-prevent_access/)

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

[Got it](https://www.advancedcustomfields.com/resources/acf-json-eof_newline/#)