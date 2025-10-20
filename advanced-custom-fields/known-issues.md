---
url: https://www.advancedcustomfields.com/resources/known-issues
scraped_at: 2025-10-20T02:23:47.323Z
---

# Known Issues

Last updated Oct 13, 2022

[Link to heading#](https://www.advancedcustomfields.com/resources/known-issues/#overview)

## Overview

Link copied

Welcome to the known issues guide for the Advanced Custom Fields plugin. This guide contains information and solutions for common problems found in each release. If you are experiencing an issue with the ACF plugin, please continue reading and [contact our support team](https://support.advancedcustomfields.com/new-ticket/) with any questions.

[Link to heading#](https://www.advancedcustomfields.com/resources/known-issues/#gutenberg-issues)

## Gutenberg Issues

Link copied

[Empty metaboxes are shown in Gutenberg _![](https://www.advancedcustomfields.com/wp-content/themes/acf/assets/images/ui-icons/plus.svg)_](https://www.advancedcustomfields.com/resources/known-issues/#)

All field groups created with the Advanced Custom Fields plugin are shown as empty visible metaboxes when editing a post irrelevant of those field group’s location rules.

This is due to a decision in Gutenberg to override the `display:none` CSS that ACF adds to “placeholder” metaboxes – used to update metaboxes dynamically whilst editing the post.

Status: Resolved.

[Metabox styling is broken in Gutenberg _![](https://www.advancedcustomfields.com/wp-content/themes/acf/assets/images/ui-icons/plus.svg)_](https://www.advancedcustomfields.com/resources/known-issues/#)

All field groups shown in the “content area” look awkward, detached and slightly broken.
More care should have gone into the styling of metaboxes to avoid such a disjointed UI and UX.

Status: This is also a [known issue](https://github.com/WordPress/gutenberg/issues/12101) that has been bumped to WordPress 5.0.1.

[Field validation does not work in Gutenberg _![](https://www.advancedcustomfields.com/wp-content/themes/acf/assets/images/ui-icons/plus.svg)_](https://www.advancedcustomfields.com/resources/known-issues/#)

Another highly used feature in ACF is our AJAX powered validation. This allows developers to highly customize the validation process via PHP whilst providing convenient feedback to the user when a field value does not meet its requirements.

Status: We’re continuing to work on bringing validation to AJAX blocks. We’ve been waiting for the Gutenberg team to provide custom validation hooks which would make this possible in a unified way, and hook into all the default page save logic.

[Link to heading#](https://www.advancedcustomfields.com/resources/known-issues/#acf-5711)

## ACF 5.7.11

Link copied

[Multisite issues _![](https://www.advancedcustomfields.com/wp-content/themes/acf/assets/images/ui-icons/plus.svg)_](https://www.advancedcustomfields.com/resources/known-issues/#)

A bug was reported where consecutive `get_field()` calls would use the same cached value even if the site was switched via `switch_to_blog()`.

Status: Solved. Please [re-download](https://www.advancedcustomfields.com/my-account/) the ACF PRO plugin files.

[Post template location rule issue _![](https://www.advancedcustomfields.com/wp-content/themes/acf/assets/images/ui-icons/plus.svg)_](https://www.advancedcustomfields.com/resources/known-issues/#)

A bug within the post\_template location rule class caused incorrect choices to appear in the location rule dropdown. Choices were displayed as “Template Title” => “template-file-name.php” instead of “template-file-name.php” => “Template Title”.

Status: Solved. Please [re-download](https://www.advancedcustomfields.com/my-account/) the ACF PRO plugin files.

[Text input maxlength issue _![](https://www.advancedcustomfields.com/wp-content/themes/acf/assets/images/ui-icons/plus.svg)_](https://www.advancedcustomfields.com/resources/known-issues/#)

A bug found in the text and textarea field validation function caused an incorrect character count when validating a value containing special characters.

Status: Solved. Please [re-download](https://www.advancedcustomfields.com/my-account/) the ACF PRO plugin files.

[Field group metabox order issue _![](https://www.advancedcustomfields.com/wp-content/themes/acf/assets/images/ui-icons/plus.svg)_](https://www.advancedcustomfields.com/resources/known-issues/#)

A bug found in the “Local Fields” logic caused all metaboxes to appear in reverse order.

Status: Solved. Please [re-download](https://www.advancedcustomfields.com/my-account/) the ACF PRO plugin files.

[Revision and preview issue _![](https://www.advancedcustomfields.com/wp-content/themes/acf/assets/images/ui-icons/plus.svg)_](https://www.advancedcustomfields.com/resources/known-issues/#)

A bug found in the `acf_get_meta()` function caused issues when copying meta values for revisions and previews. This bug affected serialized array values and caused the flexible content field to appear empty when previewing or restoring a revision.

Status: Solved. Please [re-download](https://www.advancedcustomfields.com/my-account/) the ACF PRO plugin files.

[get\_field\_object() issue _![](https://www.advancedcustomfields.com/wp-content/themes/acf/assets/images/ui-icons/plus.svg)_](https://www.advancedcustomfields.com/resources/known-issues/#)

A bug found in the `get_field_object()` function prevented a field from being loaded by it’s key.

Status: Solved. Please [re-download](https://www.advancedcustomfields.com/my-account/) the ACF PRO plugin files.

[get\_sub\_field() issue _![](https://www.advancedcustomfields.com/wp-content/themes/acf/assets/images/ui-icons/plus.svg)_](https://www.advancedcustomfields.com/resources/known-issues/#)

A bug found in the `get_sub_field()` function caused incorrect values to be returned for some sub fields. This issue was seen most when a sub field existed with a “name” value equal to a “field type” such as “text” or “image”.

Status: Solved. Please [re-download](https://www.advancedcustomfields.com/my-account/) the ACF PRO plugin files.

[Field group sync issue _![](https://www.advancedcustomfields.com/wp-content/themes/acf/assets/images/ui-icons/plus.svg)_](https://www.advancedcustomfields.com/resources/known-issues/#)

A bug found in the logic for syncing field groups (from Local JSON) caused the imported fields to lose their children.

Status: Solved. Please [re-download](https://www.advancedcustomfields.com/my-account/) the ACF PRO plugin files.

[Values contain backslashes _![](https://www.advancedcustomfields.com/wp-content/themes/acf/assets/images/ui-icons/plus.svg)_](https://www.advancedcustomfields.com/resources/known-issues/#)

A bug found in `acf_update_metadata()` function caused values from the Options Page to be incorrectly escaped causing multiple backslashes.

Status: Solved. Please [re-download](https://www.advancedcustomfields.com/my-account/) the ACF PRO plugin files.

[Undefined function register\_field\_group() _![](https://www.advancedcustomfields.com/wp-content/themes/acf/assets/images/ui-icons/plus.svg)_](https://www.advancedcustomfields.com/resources/known-issues/#)

The function `register_field_group()` was accidentally removed.

Status: Solved. Please [re-download](https://www.advancedcustomfields.com/my-account/) the ACF PRO plugin files.

[Link to heading#](https://www.advancedcustomfields.com/resources/known-issues/#acf-572)

## ACF 5.7.2

Link copied

[JS error Object.e.getPreference _![](https://www.advancedcustomfields.com/wp-content/themes/acf/assets/images/ui-icons/plus.svg)_](https://www.advancedcustomfields.com/resources/known-issues/#)

A bug was quickly reported and fixed that throws a JS error called `Object.e.getPreference`. JS errors have a tendency to snowball into bigger problems such as unresponsive buttons and broken functionality. If you are experiencing any issues when editing a post, please re-download the ACF PRO plugin files to get the patched JS.

Tip: You can also trick ACF into re-updating itself by editing the main “acf.php” plugin file and changing the two references of “5.7.2” to “5.7.1”. This will allow WP to check for plugin updates and you can then re-update the plugin.

Status: Solved. Please [re-download](https://www.advancedcustomfields.com/my-account/) the ACF PRO plugin files.

[Link to heading#](https://www.advancedcustomfields.com/resources/known-issues/#acf-570)

## ACF 5.7.0

Link copied

[Empty field returns Default Value _![](https://www.advancedcustomfields.com/wp-content/themes/acf/assets/images/ui-icons/plus.svg)_](https://www.advancedcustomfields.com/resources/known-issues/#)

A bug has been found where ACF is incorrectly returning the “default value” for fields that have no value. If you are experiencing any issues where ACF functions are returning undesired values, please edit the file ‘includes/api/api-field.php’ and change line 1083 to the following:

[Link to heading#](https://www.advancedcustomfields.com/resources/known-issues/#api-fieldphp)

#### api-field.php

Link copied

```php
function acf_maybe_get_field( $selector, $post_id = false, $strict = true ) {
```

Status: Solved. Please [re-download](https://www.advancedcustomfields.com/my-account/) the ACF PRO plugin files.

[Link to heading#](https://www.advancedcustomfields.com/resources/known-issues/#acf-566)

## ACF 5.6.6

Link copied

[Conditional logic issues _![](https://www.advancedcustomfields.com/wp-content/themes/acf/assets/images/ui-icons/plus.svg)_](https://www.advancedcustomfields.com/resources/known-issues/#)

A bug in conditional logic JS is causing validation issues for newly added flexible content layouts. If you are experiencing any incorrect validation errors, please re-download the plugin files and [contact our support team](https://support.advancedcustomfields.com/new-ticket/) if problems persist.

Status: Solved. Please [re-download](https://www.advancedcustomfields.com/my-account/) the ACF PRO plugin files.

[Link to heading#](https://www.advancedcustomfields.com/resources/known-issues/#acf-563)

## ACF 5.6.3

Link copied

[Google Map API URL isues _![](https://www.advancedcustomfields.com/wp-content/themes/acf/assets/images/ui-icons/plus.svg)_](https://www.advancedcustomfields.com/resources/known-issues/#)

An over eager `esc_js()` function is causing character issues with the **acf.fields.google\_map.url** value. This may prevent the Google Map autocomplete feature from working. Please edit the file ‘includes/fields/class-acf-field-google-map.php’ and change line 300 to the following:

[Link to heading#](https://www.advancedcustomfields.com/resources/known-issues/#class-acf-field-google-mapphp)

#### class-acf-field-google-map.php

Link copied

```php
if( acf ) acf.fields.google_map.url = '<?php echo $url; ?>';
```

Status: Solved. Please [re-download](https://www.advancedcustomfields.com/my-account/) the ACF PRO plugin files.

[Link to heading#](https://www.advancedcustomfields.com/resources/known-issues/#acf-562)

## ACF 5.6.2

Link copied

[Range field won't save decimal values _![](https://www.advancedcustomfields.com/wp-content/themes/acf/assets/images/ui-icons/plus.svg)_](https://www.advancedcustomfields.com/resources/known-issues/#)

This bug is caused by a missing **step** attribute on the number input. Please edit the file ‘includes/fields/class-acf-field-range.php’ and change line 101 to the following:

[Link to heading#](https://www.advancedcustomfields.com/resources/known-issues/#class-acf-field-rangephp)

#### class-acf-field-range.php

Link copied

```php
$html .= acf_get_text_input(array(
    'type'  => 'number',
    'id'    => $atts['id'] . '-alt',
    'value' => $atts['value'],
    'step'  => $atts['step']
));
```

Status: Solved for 5.6.3.

[Clone field issues within a flexible content layout _![](https://www.advancedcustomfields.com/wp-content/themes/acf/assets/images/ui-icons/plus.svg)_](https://www.advancedcustomfields.com/resources/known-issues/#)

A bug in the [Clone field](https://www.advancedcustomfields.com/resources/clone/) is causing display problems when used as a sub field within a [Flexible Content](https://www.advancedcustomfields.com/resources/flexible-content/) layout.

Status: Solved. Please [re-download](https://www.advancedcustomfields.com/my-account/) the ACF PRO plugin files.

[Link to heading#](https://www.advancedcustomfields.com/resources/known-issues/#acf-560)

## ACF 5.6.0

Link copied

[Custom Fields metabox disappeared _![](https://www.advancedcustomfields.com/wp-content/themes/acf/assets/images/ui-icons/plus.svg)_](https://www.advancedcustomfields.com/resources/known-issues/#)

This is expected behavior added in v5.5.13 and enabled by default in 5.6.0. ACF now removes the default WP custom fields metabox in an attempt to **speed up the load times** of the post edit page. This feature can be disabled with the following code.

[Link to heading#](https://www.advancedcustomfields.com/resources/known-issues/#functionsphp)

#### functions.php

Link copied

```php
add_filter('acf/settings/remove_wp_meta_box', '__return_false');
```

[Post and Page location rules appearing everywhere _![](https://www.advancedcustomfields.com/wp-content/themes/acf/assets/images/ui-icons/plus.svg)_](https://www.advancedcustomfields.com/resources/known-issues/#)

A bug in the location rule logic is causing both the Post and Page rules to incorrectly match when using the **!=** operator.

Status: Solved. Please [re-download](https://www.advancedcustomfields.com/my-account/) the ACF PRO plugin files.

[User Role location rule not working _![](https://www.advancedcustomfields.com/wp-content/themes/acf/assets/images/ui-icons/plus.svg)_](https://www.advancedcustomfields.com/resources/known-issues/#)

A bug in this location rule is preventing the **‘all’** value from working as expected. Please note that **‘user\_role = all’** can be achieved with the User Form location rule. Try changing the rule to **‘user\_form = all’**.

Status: Solved. Please [re-download](https://www.advancedcustomfields.com/my-account/) the ACF PRO plugin files.

[Double fields _![](https://www.advancedcustomfields.com/wp-content/themes/acf/assets/images/ui-icons/plus.svg)_](https://www.advancedcustomfields.com/resources/known-issues/#)

Recent changes to the core `acf_field` class have caused a conflict with some 3rd party field types (such as the image crop and component field types) that extend core ACF fields (such as the image and repeater field types) causing the core fields to render twice. Its most likely that the 3rd party plugin has released an update to solve this issue, but if not, please add an empty `initialize()` to the 3rd party field class. More info can be found on [this github issue](https://github.com/andersthorborg/ACF-Image-Crop/issues/45).

```php
function initialize() {

        /* do nothing */

    }
```

[Issues modifying $\_POST data and the acf/save\_post action _![](https://www.advancedcustomfields.com/wp-content/themes/acf/assets/images/ui-icons/plus.svg)_](https://www.advancedcustomfields.com/resources/known-issues/#)

Recent changes to the ‘acf/save\_post’ action are preventing any modifications to the `$_POST['acf']` data (during the ‘acf/save\_post’ action) to be ignored. Also, any custom code triggering the ‘acf/save\_post’ action will fail silently unless an array of values is defined as a second parameter.

Status: Solved. Please [re-download](https://www.advancedcustomfields.com/my-account/) the ACF PRO plugin files.

[Basic uploaded not saving correctly in acf\_form() _![](https://www.advancedcustomfields.com/wp-content/themes/acf/assets/images/ui-icons/plus.svg)_](https://www.advancedcustomfields.com/resources/known-issues/#)

This problem is caused by the above **Issues modifying $\_POST data and the acf/save\_post action** issue and is preventing the basic uploader from saving the uploaded attachment ID.

Status: Solved. Please [re-download](https://www.advancedcustomfields.com/my-account/) the ACF PRO plugin files.

[Multiple values (select, checkbox, etc) not saving to Menus or Menu Items _![](https://www.advancedcustomfields.com/wp-content/themes/acf/assets/images/ui-icons/plus.svg)_](https://www.advancedcustomfields.com/resources/known-issues/#)

This problem is being caused by some WP core code modifying the $\_POST data during the menu save action. The intention of this WP code is to prevent PHP `max_input_vars` limitations – which is great – but is preventing multiple ‘array type’ values form being saved.

We have opened a ticket with WP and found a neat fix for ACF PRO!

Status: Solved. Please [re-download](https://www.advancedcustomfields.com/my-account/) the ACF PRO plugin files.

[WPML loading incorrect Options Page language _![](https://www.advancedcustomfields.com/wp-content/themes/acf/assets/images/ui-icons/plus.svg)_](https://www.advancedcustomfields.com/resources/known-issues/#)

This problem is being caused by a minor change to the options page logic and will affect those who register options pages directly in the functions.php file root (not within the ‘acf/init’ action).

Status: Solved. Please [re-download](https://www.advancedcustomfields.com/my-account/) the ACF PRO plugin files.

[Link to heading#](https://www.advancedcustomfields.com/resources/known-issues/#acf-600)

## ACF 6.0.0

Link copied

[Repeater pagination not available in Flexible Content and Repeater subfields _![](https://www.advancedcustomfields.com/wp-content/themes/acf/assets/images/ui-icons/plus.svg)_](https://www.advancedcustomfields.com/resources/known-issues/#)

Currently you cannot enable pagination for Repeater fields if they are subfields of a Flexible Content or Repeater field. We will be introducing support for this in a later version.

[ACF Blocks render templates cannot start with a html comment _![](https://www.advancedcustomfields.com/wp-content/themes/acf/assets/images/ui-icons/plus.svg)_](https://www.advancedcustomfields.com/resources/known-issues/#)

For ACF Blocks using `blockVersion: 2` and `jsx: true` (both defaults for block.json blocks), your php template for the block cannot start with a HTML comment. If it does, your block will crash when injecting the preview from the server as React cannot add references to HTML comments, and ACF Blocks needs to attach one to the first element in your template.

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

[Link to heading#](https://www.advancedcustomfields.com/resources/known-issues/#related)

## Related

Link copied

- Basic: [Text](https://www.advancedcustomfields.com/resources/text/)
- Videos: [ACF Unlocks the True Power of WordPress](https://www.advancedcustomfields.com/resources/acf-unlocks-the-true-power-of-wordpress/)

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

[Got it](https://www.advancedcustomfields.com/resources/known-issues/#)