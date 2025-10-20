---
url: https://www.advancedcustomfields.com/resources/synchronized-json
scraped_at: 2025-10-20T02:16:48.432Z
---

# Synchronized JSON

Last updated Jun 24, 2016

[Link to heading#](https://www.advancedcustomfields.com/resources/synchronized-json/#overview)

## Overview

Link copied

Synchronized JSON is a feature (added in version 5.1.5) which detects changes to [local JSON](https://www.advancedcustomfields.com/resources/local-json/ "Local JSON") files and allows the user to update the corresponding field groups within the Database. This functionality is visible when viewing the field group admin page but only when ACF has detected there are field groups available for synchronizing.

[![acf-pro-sync-available](https://www.advancedcustomfields.com/wp-content/uploads/2014/12/acf-pro-sync-available.png)](https://www.advancedcustomfields.com/wp-content/uploads/2014/12/acf-pro-sync-available.png)

[Link to heading#](https://www.advancedcustomfields.com/resources/synchronized-json/#available-for-sync)

## Available for sync

Link copied

JSON field groups are determined ‘available for sync’ when either the JSON field group does not exist in the DB (field group key is used to match pair), or when the JSON field group contains a higher ‘modified’ value than the DB post’s modified date. The modified value can be found within the JSON file (assuming the file has been created by ACF PRO version 5.1.5 or later) and is a GMT unix timestamp from when the field group was last saved.

If you do not wish for your field group to qualify for ‘available for sync’, simply add an extra value to the JSON array called ‘private’: `'private' : true`. This may become useful for plugin / theme developers who wish to keep their bundled field groups hidden from the user.

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

[Link to heading#](https://www.advancedcustomfields.com/resources/synchronized-json/#related)

## Related

Link copied

- Features: [Local JSON](https://www.advancedcustomfields.com/resources/local-json/)
- Guides: [Improving ACF Performance](https://www.advancedcustomfields.com/resources/improving-acf-performance/)
- Guides: [Register fields via PHP](https://www.advancedcustomfields.com/resources/register-fields-via-php/)
- Filters: [acf/update\_value](https://www.advancedcustomfields.com/resources/acf-update_value/)
- Filters: [acf/settings](https://www.advancedcustomfields.com/resources/acf-settings/)

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

[Got it](https://www.advancedcustomfields.com/resources/synchronized-json/#)