---
url: https://www.advancedcustomfields.com/resources/upgrade-guide-acf-pro
scraped_at: 2025-10-20T02:17:32.895Z
---

# Upgrade Guide - ACF PRO

## Welcome to the upgrade guide for Advanced Custom Fields PRO. This guide will walk you through the upgrade process from free to PRO and answer any questions you may have about our most powerful version yet!

On this page: [Upgrade Steps](https://www.advancedcustomfields.com/resources/upgrade-guide-acf-pro/#upgrade-steps) \- [Whats New](https://www.advancedcustomfields.com/resources/upgrade-guide-acf-pro/#whats-new) \- [Developer Notes](https://www.advancedcustomfields.com/resources/upgrade-guide-acf-pro/#developer-notes) \- [FAQ](https://www.advancedcustomfields.com/resources/upgrade-guide-acf-pro/#faq)

## Upgrade Steps

Upgrading from ACF to ACF PRO is simple, here's how.

## _1_ Purchase a license.

ACF PRO is a premium plugin and requires a license in order to access the plugin files.

[View License Pricing](https://www.advancedcustomfields.com/pro/)

![](https://www.advancedcustomfields.com/wp-content/themes/acf/templates/images/acf-upgrade-pro-step-1.png)

## _2_ Download.

Log into your [ACF account](https://www.advancedcustomfields.com/my-account/) and download the ACF PRO plugin .zip file to your desktop.

![](https://www.advancedcustomfields.com/wp-content/themes/acf/templates/images/acf-upgrade-pro-step-2.png)

## _3_ Install.

Log into your WordPress website and use the **Plugins > Add New** to upload the ACF PRO plugin .zip.

![](https://www.advancedcustomfields.com/wp-content/themes/acf/templates/images/acf-upgrade-pro-step-3.png)

## _4_ Activate.

From the **Plugins** page, activate the ACF PRO plugin!

![](https://www.advancedcustomfields.com/wp-content/themes/acf/templates/images/acf-upgrade-pro-step-4.png)

## _5_ Clean Up.

ACF PRO is an **independent plugin** and does **not** require the free version to be installed.

You can now deactivate ACF free and any ACF premium plugins.

![](https://www.advancedcustomfields.com/wp-content/themes/acf/templates/images/acf-upgrade-pro-step-5.png)

## _6_ Upgrade Database.

Next, you will be prompted for a Database Upgrade. ACF PRO will configure some settings and ready your fields!

![](https://www.advancedcustomfields.com/wp-content/themes/acf/templates/images/acf-upgrade-version-5-step-3.png)

## _7_ Enable Updates.

Lastly, Jump back over to your ACF account and copy your ACF PRO license into the **Custom Fields > Updates** page to enable plugin updates!

![](https://www.advancedcustomfields.com/wp-content/themes/acf/templates/images/acf-upgrade-pro-step-7.png)

## Enjoy!

**Nice work, you are now updated!** Be sure to take a quick look over your website to ensure everything is as it should be and don't hesitate to [contact our support team](https://support.advancedcustomfields.com/new-ticket/) with any questions or concerns.

![](https://www.advancedcustomfields.com/wp-content/themes/acf/templates/images/see-whats-new.png)

![](https://www.advancedcustomfields.com/wp-content/themes/acf/templates/images/acf-upgrade-version-5-whats-new.jpg)

## What's New?

Here's a look at the new and exciting features in ACF version 5!

### Link Field

The Link field provides a simple way to select or define a link (url, title, target).

### Group Field

The Group field provides a simple way to create a group of fields.

### oEmbed Field

The oEmbed field allows an easy way to embed videos, images, tweets, audio, and other content.

### Clone Field Pro

The clone field allows you to select and display existing fields.

### More AJAX

More fields use AJAX powered search to speed up page loading

### Local JSON

New auto export to JSON feature improves speed and allows for syncronisation. [Learn more](https://www.advancedcustomfields.com/resources/local-json/)

### Easy Import / Export

Both import and export of field groups can easily be done through a new tools page

### New Form Locations

Fields can now be mapped to menus, menu items, comments, widgets and all user forms!

### More Customization

New PHP (and JS) actions and filters have been added to allow for more customization

### Fresh UI

The entire plugin has had a design refresh including new field types, settings and design!

### New Settings

Field group settings have been added for Active, Label Placement, Instructions Placement and Description.

### Better Front End Forms

acf\_form() can now create a new post on submission with lots of new settings

### Better Validation

Form validation is now done via PHP + AJAX in favour of only JS

### Moving Fields

New field group functionality allows you to move a field between groups & parents

### More!

This is just a handful of improvements found in ACF 5! You will need to update in order to find the rest!

## Developer Notes

We made some changes. Here are the ones you should know about.

| Name | Notes |
| --- | --- |
| ACF PRO | We have moved away from selling individual add-ons towards an all inclusive PRO plugin!<br>Because **ACF PRO** is a single plugin combining ACF with all our premium features, we can deliver a higher standard of product including:<br>1. More features, more often<br>2. Better compatibility<br>3. Faster updates (less plugins)<br>4. Faster websites (less assets)<br>To learn more about premium features, please checkout the [ACF PRO](https://www.advancedcustomfields.com/pro/) page. |
| ACF 5 | Welcome to the future! ACF version 5 is our latest architecture powering both our free and PRO plugins.<br>Although sometimes confused as the same, ACF 5 is simply "version 5" - the next major version scheduled for release this year and currently available via [Early Access](https://www.advancedcustomfields.com/resources/upgrade-guide-version-5/). ACF PRO is our professional plugin that combines ACF 5 with our premium features such as the repeater field. |
| Add-ons | Now that ACF PRO is distributing our premium functionality, we will no longer develop individual Add-ons and will eventually remove them from the website. |
| Database Upgrade | After updating to ACF 5, you will be prompted to upgrade the Database.<br>This is a necessary step to migrate across your field and field group settings from version 4.x. This upgrade will also copy across any taxonomy term values from the 'wp\_options' table to the 'wp\_termmeta' table.<br>No data is deleted or modified during this upgrade. |
| Template Functions | No changes to report here 😁. You can expect every `get_field()` and `the_field()` to work just the same! |
| Field Groups | Field Group settings are saved in the wp\_posts table _(same as before)_ but with a post\_type of **'acf-field-group'** (previously 'acf'). New settings have also been added including Active, Label Placement, Instructions Placement and Description. |
| Fields | Field settings are now also saved in the wp\_posts table with a post type of **'acf-field'**. New settings have also been added including Wrapper Attributes, Return Type and many more depending on the field type! |
| wp\_termmeta | Taxonomy term values are now saved to the 'wp\_termmeta' table _(previously saved to the wp\_options table)_. No change is required to template code as the database upgrade will copy across all taxonomy term values to the wp\_termmeta table. |
| select2 | ACF 5 includes the Select2 JS library for powerful AJAX based selection in many of it's field's (select, post\_type, taxonomy, user)! |
| Markup | ACF 5 produces new and improved HTML, CSS and JS throughout the plugin allowing for a faster experience and better customisation! Within these changes is a different class naming for field wrapper elements:<br>This change looks like `<div class="field_type-{$type}">` to `<div class="acf-field-{$type}">`, and although minor, may cause issues with existing custom CSS and JS. If your theme relies on the old class names, you can easily add them with the following code:<br>```php<br>/* Enable ACF 4 class names */<br>add_filter('acf/compatibility/field_wrapper_class', '__return_true');<br>``` |
| $\_POST | Field values are now sent in the $\_POST data using `$_POST['acf']` instead of `$_POST['fields']`. |
| Export | ACF version 5 includes a .json based export and import tool. Previous version of ACF used the WP .xml export which is currently not compatible. We will be working on a solution for this shortly! |

## FAQ

Have questions? We have answers.

## Do I need to make any changes?

No, you do not need to make any changes to your theme. ACF PRO is still the same plugin you use and love, and will work in the same way. If your theme contains heavy ACF customisation, it will be wise to review your code and check for any issues.

## Do I need both ACF and ACF PRO?

No, ACF PRO is an independent plugin and does not require the free version to be installed. Once ACF PRO is active, you can deactivate the free version and any ACF premium add-ons.

## Will my Add-ons work?

Premium ACF Add-ons are no longer needed when ACF PRO is installed. ACF PRO contains all our premium functionaily wrapped up in a single easy to install plugin!

Any 3rd party plugin that supports ACF5 will work the same in ACF PRO.

## Do I need to buy ACF PRO?

Yes, ACF PRO is a premium plugin and requires a license purchase to access the plugin files. [View License Pricing](https://www.advancedcustomfields.com/pro/)

## Can I roll back?

Yes, although it is a manual process. All versions of the ACF plugin can be [found here](https://www.advancedcustomfields.com/downloads/). Simply download, extract and replace your 'plugins/advanced-custom-fields' plugin folder.

## Should I backup?

It is always a good idea to backup your website before updating a plugin to a new major version, however, this is not required. ACF version 5 does not delete or modify any existing data during the 'DB Upgrade' - only new data is created.

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

[Got it](https://www.advancedcustomfields.com/resources/upgrade-guide-acf-pro/#)