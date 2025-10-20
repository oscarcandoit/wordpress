---
url: https://www.advancedcustomfields.com/resources/upgrade-guide-version-4
scraped_at: 2025-10-20T02:17:24.671Z
---

# Upgrade Guide – Version 4

Last updated Oct 5, 2017

[Link to heading#](https://www.advancedcustomfields.com/resources/upgrade-guide-version-4/#overview)

## Overview

Link copied

The ACF plugin has undergone some major changes in version 4 to adhere to the new terms & conditions set by WordPress.

To make your upgrade a seamless operation, please read this guide before updating.

[Link to heading#](https://www.advancedcustomfields.com/resources/upgrade-guide-version-4/#database)

## Database

Link copied

No changes have been made to any data stored in the database. Upgrading and downgrading is as easy as changing the plugin files!

[Link to heading#](https://www.advancedcustomfields.com/resources/upgrade-guide-version-4/#add-ons)

## Add-ons

Link copied

Previously, all Add-ons were unlocked via an activation code (purchased from the ACF Add-ons store). New to v4, all Add-ons act as separate plugins which need to be individually downloaded, installed and updated.

You can find all purchased add-ons via your store account here: [https://www.advancedcustomfields.com/my-account](https://www.advancedcustomfields.com/my-account).

You may also download any previously activated add-ons from within the ACF plugin. After upgrading to v4, you will be redirected to the what’s new page where you can see and download v4 add-ons which were previously activated.

[Link to heading#](https://www.advancedcustomfields.com/resources/upgrade-guide-version-4/#custom-field-types)

## Custom Field Types

Link copied

Creating your own field type has never been easier! Unfortunately, version 3 field types are not compatible with version 4.
Migrating your field types is easy, please [follow this tutorial](https://www.advancedcustomfields.com/docs/tutorials/creating-a-new-field-type/) to learn more.

You will find that some functions have changed names. I advise that you start with a blank dummy.php field file and copy across your old functions one by one into the new function spaces.

[Link to heading#](https://www.advancedcustomfields.com/resources/upgrade-guide-version-4/#-actions--filters)

## Actions / Filters

Link copied

Many of the actions & filters have changed. Please see the following table to find the appropriate changes.

[Link to heading#](https://www.advancedcustomfields.com/resources/upgrade-guide-version-4/#actions)

### Actions

Link copied

| Version 3 | Version 4 |
| --- | --- |
| [acf\_save\_post](https://www.advancedcustomfields.com/resources/actions/acf_save_post/ "acf_save_post") | [acf/save\_post](https://www.advancedcustomfields.com/resources/actions/acfsave_post/ "acf/save_post") |
| [acf\_head-input](https://www.advancedcustomfields.com/resources/actions/acf_head-input/ "acf_head-input") | [acf/input/admin\_head](https://www.advancedcustomfields.com/resources/actions/acfinputadmin_head/ "acf/input/admin_head") |
| [acf\_print\_styles-input](https://www.advancedcustomfields.com/resources/actions/acf_print_styles-input/ "acf_print_styles-input") | acf/input/admin\_enqueue\_scripts |
| [acf\_print\_scripts-input](https://www.advancedcustomfields.com/resources/actions/acf_print_scripts-input/ "acf_print_scripts-input") | acf/input/admin\_enqueue\_scripts |
| [acf\_head-fields](https://www.advancedcustomfields.com/resources/actions/acf_head-fields/ "acf_head-fields") | [acf/field\_group/admin\_head](https://www.advancedcustomfields.com/resources/actions/acffield_groupadmin_head/ "acf/field_group/admin_head") |
| acf\_print\_styles-fields | acf/field\_group/admin\_enqueue\_scripts |
| acf\_print\_scripts-fields | acf/field\_group/admin\_enqueue\_scripts |

[Link to heading#](https://www.advancedcustomfields.com/resources/upgrade-guide-version-4/#filters)

### Filters

Link copied

| Version 3 | Version 4 |
| --- | --- |
| [acf\_load\_field](https://www.advancedcustomfields.com/resources/filters/acf_load_field/ "acf_load_field") | [acf/load\_field](https://www.advancedcustomfields.com/resources/filters/acfload_field/ "acf/load_field") |
| acf\_load\_field-{$field\_type} | acf/load\_field/type={$field\_type} |
| acf\_load\_field-{$field\_name} | acf/load\_field/name={$field\_name} |
| acf\_load\_field-{$field\_key} | acf/load\_field/key={$field\_key} |
| [acf\_load\_value](https://www.advancedcustomfields.com/resources/filters/acf_load_value/ "acf_load_value") | [acf/load\_value](https://www.advancedcustomfields.com/resources/filters/acfload_value/ "acf/load_value") |
| acf\_load\_value-{$field\_type} | acf/load\_value/type={$field\_type} |
| acf\_load\_value-{$field\_name} | acf/load\_value/name={$field\_name} |
| acf\_load\_value-{$field\_key} | acf/load\_value/key={$field\_key} |
| [acf\_update\_value](https://www.advancedcustomfields.com/resources/filters/acf_update_value/ "acf_update_value") | [acf/update\_value](https://www.advancedcustomfields.com/resources/filters/acfupdate_value/ "acf/update_value") |
| acf\_update\_value-{$field\_type} | acf/update\_value/type={$field\_type} |
| acf\_update\_value-{$field\_name} | acf/update\_value/name={$field\_name} |
| acf\_update\_value-{$field\_key} | acf/update\_value/key={$field\_key} |
| acf\_settings | [acf/options\_page/settings](https://www.advancedcustomfields.com/resources/filters/acfoptions_pagesettings/) |
| acf\_options\_page\_title | \[Removed\] |
| acf\_form\_pre\_save\_post | acf/pre\_save\_post |

[Link to heading#](https://www.advancedcustomfields.com/resources/upgrade-guide-version-4/#options-page)

## Options Page

Link copied

Previously, the Options Page Add-on used 1 function and 2 hooks to modify it’s settings. These were:

- function: register\_options\_page()
- filter: acf\_options\_page\_title
- filter: acf\_settings

Both the filters have been removed, however, the ‘register\_options\_page()’ function is still available and a new filter ‘ [acf/options\_page/settings](https://www.advancedcustomfields.com/resources/filters/acfoptions_pagesettings/)‘ can be used to customize the title, capability and sub pages.

[Link to heading#](https://www.advancedcustomfields.com/resources/upgrade-guide-version-4/#acfsettings)

## acf\_settings

Link copied

This filter has been removed as it is no longer needed to hold activation codes or the options page settings. If you were previously using this filter to modify the soptions page’s settings, please use the new filter ‘ [acf/options\_page/settings](https://www.advancedcustomfields.com/resources/filters/acfoptions_pagesettings/)‘.

[Link to heading#](https://www.advancedcustomfields.com/resources/upgrade-guide-version-4/#functions)

## Functions

Link copied

All previous API functions will continue to work in the exact same way. 3 new functions have been added! These are:

- get\_field\_objects – mixture between get\_fields and get\_field\_object
- get\_sub\_field\_object – mixture between get\_sub\_field and get\_field\_object
- create\_field – creates the HTML for a field
- delete\_field – deletes a field value from the DB

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

[Link to heading#](https://www.advancedcustomfields.com/resources/upgrade-guide-version-4/#related)

## Related

Link copied

- Guides: [Creating a new field type](https://www.advancedcustomfields.com/resources/creating-a-new-field-type/)
- Guides: [How to Update](https://www.advancedcustomfields.com/resources/how-to-update/)
- Videos: [Installing ACF and ACF PRO](https://www.advancedcustomfields.com/resources/installing-acf-and-acf-pro/)
- Actions: [acf/input/admin\_enqueue\_scripts](https://www.advancedcustomfields.com/resources/acf-input-admin_enqueue_scripts/)
- Guides: [Adding custom javascript to fields](https://www.advancedcustomfields.com/resources/adding-custom-javascript-fields/)

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

[Got it](https://www.advancedcustomfields.com/resources/upgrade-guide-version-4/#)