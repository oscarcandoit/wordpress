---
url: https://www.advancedcustomfields.com/resources/how-to-include-acf-in-a-plugin-or-theme
scraped_at: 2025-10-20T02:28:58.613Z
---

# How to Include ACF PRO in a Plugin or Theme

Last updated Feb 27, 2024

[Link to heading#](https://www.advancedcustomfields.com/resources/how-to-include-acf-in-a-plugin-or-theme/#overview)

## Overview

Link copied

To include ACF PRO within your plugin or theme, first make sure you are following the [rules and conditions](https://www.advancedcustomfields.com/resources/including-acf-within-a-plugin-or-theme/), and then download the appropriate ACF plugin files and copy them into your plugin or theme.

We recommend using the folder `includes/acf` within your codebase.

Next, use the following code as a starter to customize and include the ACF plugin in your plugin or theme.

[Link to heading#](https://www.advancedcustomfields.com/resources/how-to-include-acf-in-a-plugin-or-theme/#detecting-if-the-acf-pro-plugin-is-installed)

## Detecting if the ACF PRO Plugin Is Installed

Link copied

A user of your plugin or theme might also be using ACF PRO for their site build. In that case, you should not proceed with bundling ACF PRO if the plugin is detected.

Use the following code to check if ACF or ACF PRO is installed:

```php
if ( ! function_exists( 'is_plugin_active' ) ) {
    include_once ABSPATH . 'wp-admin/includes/plugin.php';
}

// Check if ACF PRO is active
if ( is_plugin_active( 'advanced-custom-fields-pro/acf.php' ) ) {
    // Abort all bundling, ACF PRO plugin takes priority
    return;
}
```

If the ACF PRO plugin is detected, you should not proceed with the following instructions.

[Link to heading#](https://www.advancedcustomfields.com/resources/how-to-include-acf-in-a-plugin-or-theme/#bootstrap-the-bundled-acf)

## Bootstrap the Bundled ACF

Link copied

First you should check if another plugin or theme active on the site is also bundling ACF PRO, if so then you shouldn’t bundle.

```php
// Check if another plugin or theme has bundled ACF
if ( defined( 'MY_ACF_PATH' ) ) {
    return;
}
```

Then you will need to tell your plugin or theme to load the ACF files from where they are stored in your codebase:

For a theme:

```php
// Define path and URL to the ACF plugin.
define( 'MY_ACF_PATH', get_stylesheet_directory() . '/includes/acf/' );
define( 'MY_ACF_URL', get_stylesheet_directory_uri() . '/includes/acf/' );
```

For a plugin

```php
define( 'MY_ACF_PATH', __DIR__ . '/acf/' );
define( 'MY_ACF_URL', plugin_dir_url( __FILE__ ) . 'acf/' );
```

Then you will need to tell ACF that the codebase lives somewhere else:

```php
// Include the ACF plugin.
include_once( MY_ACF_PATH . 'acf.php' );

// Customize the URL setting to fix incorrect asset URLs.
add_filter('acf/settings/url', 'my_acf_settings_url');
function my_acf_settings_url( $url ) {
    return MY_ACF_URL;
}
```

[Link to heading#](https://www.advancedcustomfields.com/resources/how-to-include-acf-in-a-plugin-or-theme/#detecting-if-the-free-acf-plugin-is-installed)

## Detecting if the free ACF Plugin Is Installed

Link copied

If the free ACF plugin is installed on the site, as users often want to use ACF themselves without realizing another plugin has bundled ACF PRO, we need to ensure they can still use it.

This involves checking if the plugin is activated, and then deactivating ACF free and showing a notice to the user that your product and ACF free can’t be active at the same time.

```php
<?php
// Check if the ACF free plugin is activated
if ( is_plugin_active( 'advanced-custom-fields/acf.php' ) ) {
    // Free plugin activated
    // Free plugin activated, show notice
    add_action( 'admin_notices', function () {
        ?>
        <div class="updated" style="border-left: 4px solid #ffba00;">
            <p>The ACF plugin cannot be activated at the same time as Third-Party Product and has been deactivated. Please keep ACF installed to allow you to use ACF functionality.</p>
        </div>
        <?php
    }, 99 );

    // Disable ACF free plugin
    deactivate_plugins( 'advanced-custom-fields/acf.php' );
}
```

In the following section we’ll show how ACF free users still can access the ACF admin screens.

[Link to heading#](https://www.advancedcustomfields.com/resources/how-to-include-acf-in-a-plugin-or-theme/#disabling-the-acf-menu)

## Disabling the ACF Menu

Link copied

**Your users should not be able to manage ACF field groups, fields, or options pages**. Unless they have the free ACF plugin installed. Therefore you are required to hide the ACF admin menu using the following code:

```php
// Check if ACF free is installed
if ( ! file_exists( WP_PLUGIN_DIR . '/advanced-custom-fields/acf.php' ) ) {
    // Free plugin not installed
    // Hide the ACF admin menu item.
    add_filter( 'acf/settings/show_admin', '__return_false' );
    // Hide the ACF Updates menu
    add_filter( 'acf/settings/show_updates', '__return_false', 100 );
}
```

This means that if the user has intended to use ACF free (with the plugin installed but not activated) they will see the ACF menu and can access the ACF admin screens of the bundled ACF PRO plugin. However, they will not be able to use the PRO features or fields unless they have an active license key which they can activate.

[Link to heading#](https://www.advancedcustomfields.com/resources/how-to-include-acf-in-a-plugin-or-theme/#including-fields-definitions)

## Including Fields Definitions

Link copied

Along with the plugin files itself, you will also need to include the field group and option pages definitions. We recommend either registering your field groups with PHP, or including a local JSON folder of the JSON file exports of your field groups and option pages.

- [Local JSON](https://www.advancedcustomfields.com/resources/local-json/)
- [Register fields via PHP](https://www.advancedcustomfields.com/resources/register-fields-via-php/)

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

[Link to heading#](https://www.advancedcustomfields.com/resources/how-to-include-acf-in-a-plugin-or-theme/#related)

## Related

Link copied

- Getting Started: [Installing ACF With Composer](https://www.advancedcustomfields.com/resources/installing-acf-with-composer/)
- Getting Started: [Installing the Free ACF Plugin](https://www.advancedcustomfields.com/resources/installation/)
- Filters: [acf/settings](https://www.advancedcustomfields.com/resources/acf-settings/)
- Guides: [Including ACF Within a Plugin or Theme](https://www.advancedcustomfields.com/resources/including-acf-within-a-plugin-or-theme/)
- Guides: [Upgrade Guide – Version 4](https://www.advancedcustomfields.com/resources/upgrade-guide-version-4/)

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

[Got it](https://www.advancedcustomfields.com/resources/how-to-include-acf-in-a-plugin-or-theme/#)