---
url: https://www.advancedcustomfields.com/resources/installing-acf-pro-with-composer
scraped_at: 2025-10-20T02:31:58.706Z
---

# Installing ACF PRO With Composer

Last updated Oct 31, 2024

[Link to heading#](https://www.advancedcustomfields.com/resources/installing-acf-pro-with-composer/#overview)

## Overview

Link copied

ACF PRO can be installed using [Composer](https://getcomposer.org/). Please see [Installing ACF With Composer](https://www.advancedcustomfields.com/resources/installing-acf-with-composer/) for details on installing the free ACF plugin with Composer.

[Link to heading#](https://www.advancedcustomfields.com/resources/installing-acf-pro-with-composer/#generate-api-credentials)

## Generate API Credentials

Link copied

Visit [**My Account**](https://www.advancedcustomfields.com/my-account/), navigate to the [**Licenses**](https://www.advancedcustomfields.com/my-account/view-licenses/) ​​ tab, and then click **Install using Composer** for your license.

This will reveal a panel where you can generate an `auth.json` credentials file to be used with Composer.

![A screenshot showing how a sample ACF my-account page with composer instructions visible](https://www.advancedcustomfields.com/wp-content/uploads/2023/12/acf-pro-composer-install-my-account-v2.png)

The `auth.json` file is made up of a username and password field. The username and password are used by Composer to authenticate to our API with HTTP basic authentication.

The username is the ACF PRO license key, and the password is the site URL (including https:// or http://) that the license is active for.

```json
{
  "http-basic": {
    "connect.advancedcustomfields.com": {
      "username": "Dvl2P9fLovYy2oJkdYOPiCrHXcRgGrmk9WR62HdErPasPsV43COx0anwTizc9XFrY8qysqqZ",
      "password": "https://mysite.com"
    }
  }
}
```

The password can be an existing site that is already active for the license key, and there’s a dropdown of already activated sites that can be selected and will automatically populate the ‘password’ field in the sample `auth.json` code. Alternatively, you can enter a new site URL in the textbox on the right to populate the `auth.json`. This site URL will be activated for the license in your account upon Composer installation. Any activation of a new URL will be subject to the activation limits for the license.

If you are using Composer to install your plugins in an automated way for new builds where you don’t know the final site URL, we recommend using an existing production URL that has been activated for the license key.

We also recommend that you [define your license key in code](https://www.advancedcustomfields.com/resources/how-to-activate/#wp-configphp). Otherwise, you’ll have to activate ACF PRO on each site by manually entering the license key in the ‘Updates’ page of ACF’s admin. You’ll be unable to use the PRO features of ACF until a license key has been entered, either programmatically or manually.

[Link to heading#](https://www.advancedcustomfields.com/resources/installing-acf-pro-with-composer/#using-version-control)

### Using Version Control

Link copied

If you are using a version control system for your site, we recommend you add the `auth.json` file to your ignore file, e.g., `.gitignore`. This prevents the license key from being included in the repository.

Create the `.gitignore` file in the root of your local Git, if you don’t already have one:

```php
touch .gitignore
```

Next, add a rule to ignore the `auth.json` file:

```php
# Exclude auth.json from Git repo
auth.json
```

Make sure you create the `auth.json` file on the live server when you deploy your site if you’ve included it in your `.gitignore`.

Developers working with the site locally will also have to create the `auth.json` file and add the license key to it before running the Composer install command.

[Link to heading#](https://www.advancedcustomfields.com/resources/installing-acf-pro-with-composer/#add-our-repository)

## Add Our Repository

Link copied

Add our repository to your `composer.json` file:

```json
"repositories": [\
    {\
        "type":"composer",\
        "url":"https://connect.advancedcustomfields.com"\
    }\
]
```

[Link to heading#](https://www.advancedcustomfields.com/resources/installing-acf-pro-with-composer/#install-the-plugin)

## Install the Plugin

Link copied

From the CLI, require ACF PRO using the following command:

```shell-session
composer require wpengine/advanced-custom-fields-pro
```

[Link to heading#](https://www.advancedcustomfields.com/resources/installing-acf-pro-with-composer/#version-constraints)

## Version Constraints

Link copied

You can use any Composer version constraints, or specify the exact version of the plugin:

```json
"require": {
    "wpengine/advanced-custom-fields-pro": "6.3.1.2"
}
```

[Link to heading#](https://www.advancedcustomfields.com/resources/installing-acf-pro-with-composer/#customizing-install-locations)

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

[Link to heading#](https://www.advancedcustomfields.com/resources/installing-acf-pro-with-composer/#installing-as-an-mu-plugin)

### Installing as an MU Plugin

Link copied

If you prefer to install ACF PRO as a [must use plugin (mu-plugin)](https://wordpress.org/documentation/article/must-use-plugins/), to ensure it will always be loaded by WordPress and can’t be deactivated from the admin dashboard like a normal plugin, you can alter the install location by adding the following to your `composer.json` file:

```json
"extra": {
    "installer-paths": {
        "wp-content/mu-plugins/{$name}/": ["wpengine/advanced-custom-fields-pro"]
    }
}
```

However, plugin directories inside the `mu-plugin` directory will not be loaded automatically by WordPress, so you would need to require it manually with an `acf.php` file in the `mu-plugin` directory root:

```php
<?php
require_once WPMU_PLUGIN_DIR . '/advanced-custom-fields-pro/acf.php';
```

As an alternative, there is a [package](https://packagist.org/packages/boxuk/wp-muplugin-loader) that automatically handles loading directories in the `mu-plugin` directory.

[Link to heading#](https://www.advancedcustomfields.com/resources/installing-acf-pro-with-composer/#example-composerjson)

## Example composer.json

Link copied

```json
{
    "name": "wpengine/composer-test.dev",
    "description": "ACF PRO in a WordPress site",
    "repositories": [\
        {\
            "type":"composer",\
            "url":"https://connect.advancedcustomfields.com"\
        }\
    ],
    "require": {
        "wpengine/advanced-custom-fields-pro": "^6.0",
    }
}
```

[Link to heading#](https://www.advancedcustomfields.com/resources/installing-acf-pro-with-composer/#build-systems-and-environment-variables)

## Build Systems and Environment Variables

Link copied

Instead of `auth.json`, you can provide the basic authentication via the `COMPOSER_AUTH` environment variable if your deployment system does not support adding files pre-build. This should be a json encoded string matching the pattern below:

```json
export COMPOSER_AUTH='{"http-basic": {"connect.advancedcustomfields.com": {"username": "Dvl2P9fLovYy2oJkdYOPiCrHXcRgGrmk9WR62HdErPasPsV43COx0anwTizc9XFrY8qysqqZ", "password": "https://mysite.com"}}}'
```

If you are using [Roots Trellis](https://roots.io/trellis/) for deployments, you can make use of the [Composer HTTP Basic Authentication feature](https://roots.io/trellis/docs/composer-http-basic-authentication/) supported by your Ansible vault.

[Link to heading#](https://www.advancedcustomfields.com/resources/installing-acf-pro-with-composer/#troubleshooting)

## Troubleshooting

Link copied

Error codes from Composer downloads match the HTTP standard. For example, 400 means you’ve requested an invalid version, 401 means you’ve provided an invalid license key or site URL, and 402 means your license has no sites left or has expired.

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

[Link to heading#](https://www.advancedcustomfields.com/resources/installing-acf-pro-with-composer/#related)

## Related

Link copied

- Getting Started: [Installing ACF With Composer](https://www.advancedcustomfields.com/resources/installing-acf-with-composer/)
- Getting Started: [Installing the Free ACF Plugin](https://www.advancedcustomfields.com/resources/installation/)
- Guides: [How to Activate ACF PRO](https://www.advancedcustomfields.com/resources/how-to-activate/)
- Guides: [How to Update](https://www.advancedcustomfields.com/resources/how-to-update/)
- Videos: [Installing ACF and ACF PRO](https://www.advancedcustomfields.com/resources/installing-acf-and-acf-pro/)

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

[Got it](https://www.advancedcustomfields.com/resources/installing-acf-pro-with-composer/#)