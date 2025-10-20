---
url: https://www.advancedcustomfields.com/resources/installing-acf-with-composer
scraped_at: 2025-10-20T02:33:48.662Z
---

# Installing ACF With Composer

Last updated Jul 2, 2025

[Link to heading#](https://www.advancedcustomfields.com/resources/installing-acf-with-composer/#overview)

## Overview

Link copied

Both ACF and ACF PRO can be installed using [Composer](https://getcomposer.org/).

These instructions cover how to install the free version of ACF with Composer. Please view [Installing ACF PRO with Composer](https://www.advancedcustomfields.com/resources/installing-acf-pro-with-composer/) for details of how to use ACF PRO with Composer.

[Link to heading#](https://www.advancedcustomfields.com/resources/installing-acf-with-composer/#add-our-repository)

## Add Our Repository

Link copied

Add our repository to your `composer.json` file:

```json
"repositories": [\
    {\
        "type":"composer",\
        "url":"https://composer.advancedcustomfields.com"\
    }\
]
```

[Link to heading#](https://www.advancedcustomfields.com/resources/installing-acf-with-composer/#install-the-plugin)

## Install the Plugin

Link copied

From the CLI, require ACF using the following command:

```shell-session
composer require wpengine/advanced-custom-fields
```

[Link to heading#](https://www.advancedcustomfields.com/resources/installing-acf-with-composer/#version-constraints)

## Version Constraints

Link copied

You can use any Composer version constraints, or specify the exact version of the plugin:

```json
"require": {
    "wpengine/advanced-custom-fields": "6.3.9"
}
```

[Link to heading#](https://www.advancedcustomfields.com/resources/installing-acf-with-composer/#customizing-install-locations)

## Customizing Install Locations

Link copied

We use [composer/installers](https://github.com/composer/installers) to automatically install our plugin package to `wp-content/plugins/`. However, you can customize the install location by adding the following to your `composer.json` file:

```json
"extra": {
    "installer-paths": {
        "wp-content/plugins/{$name}/": ["type:wordpress-plugin"]
    }
}
```

[Link to heading#](https://www.advancedcustomfields.com/resources/installing-acf-with-composer/#installing-as-an-mu-plugin)

### Installing as an MU Plugin

Link copied

If you prefer to install ACF as a [must use plugin (mu-plugin)](https://wordpress.org/documentation/article/must-use-plugins/), to ensure it will always be loaded by WordPress and can’t be deactivated from the admin dashboard like a normal plugin, you can alter the install location by adding the following to your `composer.json` file:

```json
"extra": {
    "installer-paths": {
        "wp-content/mu-plugins/{$name}/": ["wpengine/advanced-custom-fields"]
    }
}
```

However, plugin directories inside the `mu-plugin` directory will not be loaded automatically by WordPress, so you would need to require it manually with an `acf.php` file in the `mu-plugin` directory root:

```php
<?php
require_once WPMU_PLUGIN_DIR . '/advanced-custom-fields/acf.php';
```

As an alternative, there is a [package](https://packagist.org/packages/boxuk/wp-muplugin-loader) that automatically handles loading directories in the `mu-plugin` directory.

[Link to heading#](https://www.advancedcustomfields.com/resources/installing-acf-with-composer/#example-composerjson)

## Example composer.json

Link copied

```json
{
    "name": "wpengine/composer-test.dev",
    "description": "ACF in a WordPress site",
    "repositories": [\
        {\
            "type":"composer",\
            "url":"https://composer.advancedcustomfields.com"\
        }\
    ],
    "require": {
        "wpengine/advanced-custom-fields": "^6"
    }
}
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

[Link to heading#](https://www.advancedcustomfields.com/resources/installing-acf-with-composer/#related)

## Related

Link copied

- Getting Started: [Installing the Free ACF Plugin](https://www.advancedcustomfields.com/resources/installation/)
- Getting Started: [Installing ACF PRO With Composer](https://www.advancedcustomfields.com/resources/installing-acf-pro-with-composer/)
- Guides: [Upgrade Guide – Version 4](https://www.advancedcustomfields.com/resources/upgrade-guide-version-4/)
- Videos: [Installing ACF and ACF PRO](https://www.advancedcustomfields.com/resources/installing-acf-and-acf-pro/)
- Guides: [How to Update](https://www.advancedcustomfields.com/resources/how-to-update/)

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

[Got it](https://www.advancedcustomfields.com/resources/installing-acf-with-composer/#)