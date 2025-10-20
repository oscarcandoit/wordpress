---
url: https://developer.wordpress.org/plugins/wordpress-org/previews-and-blueprints
scraped_at: 2025-10-20T03:17:34.364Z
---

[Skip to content](https://developer.wordpress.org/plugins/wordpress-org/previews-and-blueprints/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Previews and Blueprints


[Home](https://developer.wordpress.org/)[Plugin Handbook](https://developer.wordpress.org/plugins/)[The WordPress.org Plugin Directory](https://developer.wordpress.org/plugins/wordpress-org/)Previews and Blueprints

Search

# Previews and Blueprints

## In this article

Table of Contents

- [The Plugin Preview Button](https://developer.wordpress.org/plugins/wordpress-org/previews-and-blueprints/#the-plugin-preview-button)
- [Enabling Plugin Previews](https://developer.wordpress.org/plugins/wordpress-org/previews-and-blueprints/#enabling-plugin-previews)
- [Blueprints](https://developer.wordpress.org/plugins/wordpress-org/previews-and-blueprints/#blueprints)
- [Using a generated Blueprint file](https://developer.wordpress.org/plugins/wordpress-org/previews-and-blueprints/#using-a-generated-blueprint-file)
- [Committing a Blueprint to Subversion](https://developer.wordpress.org/plugins/wordpress-org/previews-and-blueprints/#committing-a-blueprint-to-subversion)

[↑ Back to top](https://developer.wordpress.org/plugins/wordpress-org/previews-and-blueprints/#wp--skip-link--target)

If you haven’t noticed it yet, the WordPress Playground is an amazing feature that lets anyone safely run a temporary WordPress install within their browser. It uses WASM to run a complete WordPress install – PHP, database, and all – entirely from within your web browser. No server needed, nothing to install.

For a while now Playground has supported loading any plugin or theme from the plugin directory; here’s how.

## [The Plugin Preview Button](https://developer.wordpress.org/plugins/wordpress-org/previews-and-blueprints/\#the-plugin-preview-button)

The Plugin Preview feature adds a convenient button to plugins in the plugin directory, when enabled by a plugin’s developers. The button takes the user to Playground with that plugin installed. It’s right beside the Download button.

The Preview button is not shown by default; it must be explicitly enabled. Developers can use blueprint files in order to configure the preview environment and install dependencies (such as other plugins and themes).

## [Enabling Plugin Previews](https://developer.wordpress.org/plugins/wordpress-org/previews-and-blueprints/\#enabling-plugin-previews)

There are two things required for a plugin preview button to appear to all users:

1. A valid `blueprint.json` file must be provided in a blueprints sub-directory of the plugin’s assets folder.
2. The plugin preview must be set to “public” from the plugin’s Advanced view by a committer.

If a valid `blueprint.json` file is present, then the Preview button will be present for plugin committers only. In which case it will look like this:

[![The Test Preview button allows plugin authors to showcase what their plugin does with one click.](https://i0.wp.com/developer.wordpress.org/files/2024/03/live-preview.png?resize=554%2C140&ssl=1)](https://i0.wp.com/developer.wordpress.org/files/2024/03/live-preview.png?ssl=1)

It’s called Test Preview because that’s why it’s there: to allow plugin committers to test their plugin in the Playground environment and decide whether or not to make it easily available to the public.

## [Blueprints](https://developer.wordpress.org/plugins/wordpress-org/previews-and-blueprints/\#blueprints)

Blueprints are json files used to set up a WordPress Playground instance.

They can be used to specify things like PHP and WP versions, the landing page, and (most importantly) a series of automated steps such as logging in, and installing and activating plugins and themes.

The blueprint for your plugin should be committed to the assets folder with subversion as `assets/blueprints/blueprint.json`. Initially only the one blueprint file is supported, but we expect to allow multiple in future.

Here’s an example of a simple blueprint.json file that you could use as a starting point:

``
[Expand code](https://developer.wordpress.org/plugins/wordpress-org/previews-and-blueprints/#)

[Copy](https://developer.wordpress.org/plugins/wordpress-org/previews-and-blueprints/#)

```json
{
    "landingPage": "/wp-admin/edit.php",
    "preferredVersions": {
        "php": "7.4",
        "wp": "5.9"
    },
    "phpExtensionBundles": [\
        "kitchen-sink"\
    ],
    "steps": [\
        {\
            "step": "login",\
            "username": "admin",\
            "password": "password"\
        }\
    ]
}
```

The features used here are:

- `landingPage`, which specifies the URL of the page that the user will land on when the preview loads.
- `preferredVersions`, which specifies versions of PHP and WordPress.
- `phpExtensionBundles`, which in this case specifies that we want most common PHP extensions to be available (kitchen-sink).
- `steps`, which tells Playground what to do before displaying the landing page. In this case, it will simply log the user in to wp-admin.

Here’s an example of a more advanced blueprint.json that demonstrates some more features you could use to create a rich demo environment for users:

``
[Expand code](https://developer.wordpress.org/plugins/wordpress-org/previews-and-blueprints/#)

[Copy](https://developer.wordpress.org/plugins/wordpress-org/previews-and-blueprints/#)

```json
{
    "landingPage": "/wp-admin/post.php?post=5&action=edit",
    "preferredVersions": {
        "php": "7.4",
        "wp": "5.9"
    },
    "phpExtensionBundles": [\
        "kitchen-sink"\
    ],
    "steps": [\
        {\
            "step": "login",\
            "username": "admin",\
            "password": "password"\
        },\
        {\
            "step": "installPlugin",\
            "pluginZipFile": {\
                "resource": "wordpress.org\/plugins",\
                "slug": "my-imaginary-plugin-dependency"\
            },\
            "options": {\
                "activate": true\
            }\
        },\
        {\
            "step": "installPlugin",\
            "pluginZipFile": {\
                "resource": "wordpress.org\/plugins",\
                "slug": "my-imaginary-plugin"\
            },\
            "options": {\
                "activate": true\
            }\
        },\
        {\
            "step": "installTheme",\
            "themeZipFile": {\
                "resource": "wordpress.org\/themes",\
                "slug": "my-imaginary-theme"\
            }\
        },\
        {\
            "step": "setSiteOptions",\
            "options": {\
                "some_required_option_1": "your_favorite_values",\
                "some_required_option_2": "your_favorite_values"\
            }\
        },\
        {\
            "step": "runPHP",\
            "code": "<?php require_once 'wordpress/wp-load.php'; wp_insert_post(array('post_title' => 'wp-load.php required for WP functionality', 'post_status' => 'publish')); ?>"\
        }\
    ]
}
```

## [Using a generated Blueprint file](https://developer.wordpress.org/plugins/wordpress-org/previews-and-blueprints/\#using-a-generated-blueprint-file)

You might see a notice similar to this on your plugin’s page:

``
[Copy](https://developer.wordpress.org/plugins/wordpress-org/previews-and-blueprints/#)

```
Your plugin does not yet have a blueprint file for user previews. If you'd like to enable previews, please follow these steps to create a blueprint.

1. Test your plugin in Playground.
2. Fix any bugs in your plugin that prevent it from working in Playground.
3. Download blueprint.json
4. Commit your blueprint to svn.

```

The **Test** link will use an auto-generated Blueprint file to load your plugin in Playground, with some default configuration values and steps. The **Download blueprint.json** link will let you download that auto-generated `blueprint.json` file, which you can then modify as needed and commit to Subversion when your plugin is ready for Playground previews.

## [Committing a Blueprint to Subversion](https://developer.wordpress.org/plugins/wordpress-org/previews-and-blueprints/\#committing-a-blueprint-to-subversion)

You must commit your blueprint.json file to your plugin’s assets folder, named like this:

`/assets/blueprints/blueprint.json`

First published

March 14, 2024

Last updated

July 18, 2024

[PreviousPreventing WordPress from Updating Your External PluginPrevious: Preventing WordPress from Updating Your External Plugin](https://developer.wordpress.org/plugins/wordpress-org/preventing-wordpress-from-updating-your-external-plugin/)

[NextRelease Confirmation EmailsNext: Release Confirmation Emails](https://developer.wordpress.org/plugins/wordpress-org/release-confirmation-emails/)

Notifications