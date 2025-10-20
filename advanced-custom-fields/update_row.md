---
url: https://www.advancedcustomfields.com/resources/update_row
scraped_at: 2025-10-20T02:23:04.218Z
---

# update\_row()

Last updated Feb 17, 2022

[Link to heading#](https://www.advancedcustomfields.com/resources/update_row/#overview)

## Overview

Link copied

Updates a row of data for an existing Repeater or Flexible Content field value.

[Link to heading#](https://www.advancedcustomfields.com/resources/update_row/#parameters)

## Parameters

Link copied

```php
update_row($selector, $row, $value, [$post_id])
```

- `$selector` _(string)_ _(Required)_ The field name or field key.
- `$row` _(int)_ _(Required)_ The row number to update.
- `$value` _(array)_ _(Required)_ The new row data.
- `$post_id` _(mixed)_ _(Optional)_ The post ID where the value is saved. Defaults to the current post.

[Link to heading#](https://www.advancedcustomfields.com/resources/update_row/#return)

## Return

Link copied

_(bool)_ True on successful update, false on failure.

[Link to heading#](https://www.advancedcustomfields.com/resources/update_row/#change-log)

## Change Log

Link copied

- Added in version 5.3.2

[Link to heading#](https://www.advancedcustomfields.com/resources/update_row/#examples)

## Examples

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/update_row/#add-a-new-row-using-field-names)

### Add a new row using field names

Link copied

This example shows how to update the first row of data of an existing repeater field called ‘images’. This repeater field contains 3 sub fields (‘image’, ‘alt’, ‘link’).
Please see notes regarding index offset.

```php
$row = array(
    'image' => 123,
    'alt'   => 'Another great sunset',
    'link'  => 'http://website.com'
);

update_row('images', 1, $row);
```

[Link to heading#](https://www.advancedcustomfields.com/resources/update_row/#notes)

## Notes

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/update_row/#index-offset)

### Index offset

Link copied

When targeting a specific row number, please note that row numbers begin from 1 and not 0. This means that the first row has an index of 1, the second row has an index of 2, and so on.
To begin indexes from 0, please use the [row\_index\_offset](https://www.advancedcustomfields.com/resources/acf-settings/) setting like so.

[Link to heading#](https://www.advancedcustomfields.com/resources/update_row/#functionsphp)

#### functions.php

Link copied

```php
add_filter('acf/settings/row_index_offset', '__return_zero');
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

[Link to heading#](https://www.advancedcustomfields.com/resources/update_row/#related)

## Related

Link copied

- Functions: [add\_row()](https://www.advancedcustomfields.com/resources/add_row/)
- Functions: [delete\_row()](https://www.advancedcustomfields.com/resources/delete_row/)
- Functions: [add\_sub\_row()](https://www.advancedcustomfields.com/resources/add_sub_row/)
- Functions: [update\_sub\_row()](https://www.advancedcustomfields.com/resources/update_sub_row/)
- Functions: [delete\_sub\_row()](https://www.advancedcustomfields.com/resources/delete_sub_row/)

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

[Got it](https://www.advancedcustomfields.com/resources/update_row/#)