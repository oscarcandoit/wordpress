---
url: https://www.advancedcustomfields.com/resources/delete_row
scraped_at: 2025-10-20T02:22:39.427Z
---

# delete\_row()

Last updated Feb 17, 2022

[Link to heading#](https://www.advancedcustomfields.com/resources/delete_row/#overview)

## Overview

Link copied

Deletes a row of data from an existing Repeater or Flexible Content field value.

[Link to heading#](https://www.advancedcustomfields.com/resources/delete_row/#parameters)

## Parameters

Link copied

```php
delete_row($selector, $row, [$post_id])
```

- `$selector` _(string)_ _(Required)_ The field name or field key.
- `$row` _(int)_ _(Required)_ The row number to update.
- `$post_id` _(mixed)_ _(Optional)_ The post ID where the value is saved. Defaults to the current post.

[Link to heading#](https://www.advancedcustomfields.com/resources/delete_row/#return)

## Return

Link copied

_(bool)_ True on successful update, false on failure.

[Link to heading#](https://www.advancedcustomfields.com/resources/delete_row/#change-log)

## Change Log

Link copied

- Added in version 5.3.2

[Link to heading#](https://www.advancedcustomfields.com/resources/delete_row/#examples)

## Examples

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/delete_row/#delete-via-field-name)

### Delete via field name

Link copied

This example shows how to delete a row of data from a field called ‘images’ on the current post being viewed.

```php
// Delete the first row of data.
delete_row('images', 1);
```

[Link to heading#](https://www.advancedcustomfields.com/resources/delete_row/#delete-via-field-key)

### Delete via field key

Link copied

This example shows how to achieve the same as above using the field’s key instead of its name.

```php
// Delete the first row of data.
delete_row('field_123456', 1);
```

[Link to heading#](https://www.advancedcustomfields.com/resources/delete_row/#notes)

## Notes

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/delete_row/#index-offset)

### Index offset

Link copied

When targeting a specific row number, please note that row numbers begin from 1 and not 0. This means that the first row has an index of 1, the second row has an index of 2, and so on.
To begin indexes from 0, please use the [row\_index\_offset](https://www.advancedcustomfields.com/resources/acf-settings/) setting like so.

[Link to heading#](https://www.advancedcustomfields.com/resources/delete_row/#functionsphp)

#### functions.php

Link copied

```php
add_filter('acf/settings/row_index_offset', '__return_zero');
```

[Link to heading#](https://www.advancedcustomfields.com/resources/delete_row/#usage-inside-loops)

### Usage inside loops

Link copied

When you use `delete_row()`, it will update the database and reindex the array of repeater or flexible field items. Therefore, you should not use this function inside a `have_rows` loop to avoid inconsistent data.

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

[Link to heading#](https://www.advancedcustomfields.com/resources/delete_row/#related)

## Related

Link copied

- Functions: [update\_row()](https://www.advancedcustomfields.com/resources/update_row/)
- Functions: [delete\_sub\_row()](https://www.advancedcustomfields.com/resources/delete_sub_row/)
- Functions: [add\_row()](https://www.advancedcustomfields.com/resources/add_row/)
- Functions: [add\_sub\_row()](https://www.advancedcustomfields.com/resources/add_sub_row/)
- Functions: [update\_sub\_row()](https://www.advancedcustomfields.com/resources/update_sub_row/)

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

[Got it](https://www.advancedcustomfields.com/resources/delete_row/#)