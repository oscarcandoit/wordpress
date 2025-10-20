---
url: https://www.advancedcustomfields.com/resources/upgrade-guide-version-5
scraped_at: 2025-10-20T02:16:56.479Z
---

# Upgrade Guide - Version 5

## Welcome to the upgrade guide for Advanced Custom Fields version 5. This guide will walk you through the update process and answer any questions you may have about our most exciting version yet!

On this page: [Upgrade Steps](https://www.advancedcustomfields.com/resources/upgrade-guide-version-5/#upgrade-steps) \- [Whats New](https://www.advancedcustomfields.com/resources/upgrade-guide-version-5/#whats-new) \- [Developer Notes](https://www.advancedcustomfields.com/resources/upgrade-guide-version-5/#developer-notes) \- [FAQ](https://www.advancedcustomfields.com/resources/upgrade-guide-version-5/#faq) \- [Troubleshooting](https://www.advancedcustomfields.com/resources/upgrade-guide-version-5/#troubleshooting)

## Upgrade Steps

Upgrading ACF to version 5 is simple, here's how.

## _1_ Update ACF.

Log into your WordPress website and use the **Plugins page** to view and update the Advanced Custom Fields plugin.

![](https://www.advancedcustomfields.com/wp-content/themes/acf/templates/images/acf-upgrade-version-5-step-1.png)

## _2_ Update Add-ons.

Does your website use the **Repeater field**, **Flexible Content field**, **Gallery field** or **Options Page** add-ons? Be sure to update these too.

![](https://www.advancedcustomfields.com/wp-content/themes/acf/templates/images/acf-upgrade-version-5-step-2.png)

## _3_ Upgrade Database.

Last but not least, you will be prompted for a Database Upgrade. ACF 5 will configure some settings and ready your fields!

![](https://www.advancedcustomfields.com/wp-content/themes/acf/templates/images/acf-upgrade-version-5-step-3.png)

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
| Add-ons | **Add-ons work with ACF 5!** We have released **v2.0.0** updates for all ACF Add-ons and will continue to release minor updates to address compatibility fixes.<br>Now that ACF PRO is distributing our premium functionality, we will no longer develop individual Add-ons and will eventually remove them from the website. |
| Database Upgrade | After updating to ACF 5, you will be prompted to upgrade the Database.<br>This is a necessary step to migrate across your field and field group settings from version 4.x. This upgrade will also copy across any taxonomy term values from the 'wp\_options' table to the 'wp\_termmeta' table.<br>No data is deleted or modified during this upgrade. |
| Template Functions | No changes to report here 😁. You can expect every `get_field()` and `the_field()` to work just the same! |
| Field Groups | Field Group settings are saved in the wp\_posts table _(same as before)_ but with a post\_type of **'acf-field-group'** (previously 'acf'). New settings have also been added including Active, Label Placement, Instructions Placement and Description. |
| Fields | Field settings are now also saved in the wp\_posts table with a post type of **'acf-field'**. New settings have also been added including Wrapper Attributes, Return Type and many more depending on the field type! |
| Values | No changes to report here 😁. Field values will continue to save into their respective 'termmeta' tables. |
| wp\_termmeta | Taxonomy term values are now saved to the 'wp\_termmeta' table _(previously saved to the wp\_options table)_. No change is required to template code as the database upgrade will copy across all taxonomy term values to the wp\_termmeta table. |
| select2 | ACF 5 includes the Select2 JS library for powerful AJAX based selection in many of it's field's (select, post\_type, taxonomy, user)! |
| Markup | ACF 5 produces new and improved HTML, CSS and JS throughout the plugin allowing for a faster experience and better customisation! Within these changes is a different class naming for field wrapper elements:<br>This change looks like `<div class="field_type-{$type}">` to `<div class="acf-field-{$type}">`, and although minor, may cause issues with existing custom CSS and JS. If your theme relies on the old class names, you can easily add them with the following code:<br>```php<br>/* Enable ACF 4 class names */<br>add_filter('acf/compatibility/field_wrapper_class', '__return_true');<br>``` |
| $\_POST | Field values are now sent in the $\_POST data using `$_POST['acf']` instead of `$_POST['fields']`. |
| Export | ACF version 5 includes a .json based export and import tool. Previous version of ACF used the WP .xml export which is currently not compatible. We will be working on a solution for this shortly! |
| Default metabox | You may notice that the default WP metabox for "Custom Fields" is no longer available when editing a post. This is due to a setting in ACF which hides it. You can easily show it again with a single line of code in your functions.php file:<br>```php<br>/* Enable WP custom fields metabox */<br>add_filter('acf/settings/remove_wp_meta_box', '__return_true');<br>``` |

## FAQ

Have questions? We have answers.

## Do I need to make any changes?

No, you do not need to make any changes to your theme. ACF version 5 is still the same plugin you use and love, and will work in the same way. If your theme contains heavy ACF customisation, it will be wise to review your code and check for any issues.

## Will my Add-ons work?

Yes, we have released updates for all official ACF Add-ons (Repeater, Gallery, Flexible Content & Options Page) making them fully compatible with ACF version 5! Please update your ACF add-ons to version 2.

## Do I need to buy ACF 5?

No, ACF version 5 is a free update. If you require professional features such as the repeater field, please take a look at the [ACF PRO page](https://www.advancedcustomfields.com/pro/).

## Can I roll back?

Yes, although it is a manual process. All versions of the ACF plugin can be [found here](https://www.advancedcustomfields.com/downloads/). Simply download, extract and replace your 'plugins/advanced-custom-fields' plugin folder

## Should I backup?

It is always a good idea to backup your website before updating a plugin to a new major version, however, this is not required. ACF version 5 does not delete or modify any existing data during the 'DB Upgrade' - only new data is created.

## What can go wrong?

Not much. The upgrade process does not modify any existing data, so you can always roll back if you run into trouble. We cover a few of the known issues on our [Update Questions](https://www.advancedcustomfields.com/resources/frequently-asked-questions/#updates-questions/) FAQs.

## Troubleshooting

Some tips to quickly identify and fix issues.

[Rolling back to version 4.0](https://www.advancedcustomfields.com/resources/upgrade-guide-version-5/#)

If you’d like to go back to an earlier version of ACF, we recommend using this [rollback plugin](https://wordpress.org/plugins/wp-rollback/), which is available from the WordPress repository. Once installed, use the Dashboard > Plugins page to Rollback the ACF plugin.

Alternatively, you can rollback manually by [downloading an older version](https://www.advancedcustomfields.com/downloads/) of ACF and uploading it to your server via your favourite FTP application. Replacing the ACF plugin folder will not affect your data in any way and is a completely safe way to rollback 👍.

[White screen of death](https://www.advancedcustomfields.com/resources/upgrade-guide-version-5/#)

A white screen of death is almost always caused by PHP code errors or memory limit exhaustion. The first thing you should do is determine whether or not the admin on your site is working. If the front-end of the website is down, but the admin is working, chances are you have a PHP error in your theme or plugin. To view the error, [enable WP\_DEBUG](https://www.advancedcustomfields.com/resources/debug/) in your wp-config.php file and reload the page.

Use the errors displayed to find the culprit code and try to solve the problem. If you need any assistance, [submit a bug report](https://www.advancedcustomfields.com/contact/) to our support team (be sure to include the errors you copied earlier).

If you need a quick fix, please rollback to version 4.4.12.

[No database upgrade prompt](https://www.advancedcustomfields.com/resources/upgrade-guide-version-5/#)

After upgrading a website from ACF4 to ACF5 you will be prompted to upgrade the database. This prompt is visible when logged into the website's dashboard. If for some reason this prompt does not appear, please consider the following possibilities:

- You have already upgraded in the past. The upgrade prompt will only run once, even if you have rolled back.
- There may be another plugin / theme code hiding the prompt.
- Your DB wp\_options table contains a modified "acf\_version" value.

An easy way to check if the upgrade has been run in the past is to check your database wp\_options table and find the "acf\_version" row. This option contains the last known version of ACF installed. If the version is higher than 5.0, the upgrade has already run and will not appear.

It is possible to force ACF to run the upgrade again by editing this row in your DB and changing the option value to "4.4.12". Please be sure to backup your database before making this change to avoid any "duplicate data" created in the second upgrade. If you’re still having troubles, please [contact support](https://www.advancedcustomfields.com/contact/).

[Database upgrade error](https://www.advancedcustomfields.com/resources/upgrade-guide-version-5/#)

During the database upgrade process, it is possible that an error may be thrown. This is most likely to occur when a large amount of termmeta exits on a website with a low amount of available PHP memory.

If you unfortunately run into an error during the upgrade, **don’t panic**. The upgrade process does not modify or delete any existing data, it only creates new data. This means you can rollback safely to an older version.

Please be sure to [contact support](https://www.advancedcustomfields.com/contact/) with a detailed report of the issue including any errors that were reported and we will do our best to help solve the issue.

[Fields are no longer visible](https://www.advancedcustomfields.com/resources/upgrade-guide-version-5/#)

If you’ve upgraded from version 4 to version 5 of ACF and you can’t see you fields, first of all, **don’t panic**! Version 5 uses a different data structure so they might not be visible, but your fields and their values are still there.

You should see a database upgrade prompt at the top of the page on your WordPress dashboard. All you need to do is click the button to run the database upgrade process. Your fields should re-ppear once that process has been completed

If you’re still having difficulties, please [get in touch](https://www.advancedcustomfields.com/contact).

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

[Got it](https://www.advancedcustomfields.com/resources/upgrade-guide-version-5/#)