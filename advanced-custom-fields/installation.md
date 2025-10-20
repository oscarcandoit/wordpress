---
url: https://www.advancedcustomfields.com/resources/installation
scraped_at: 2025-10-20T02:31:42.560Z
---

# Installing the Free ACF Plugin

Last updated Oct 23, 2024

[Link to heading#](https://www.advancedcustomfields.com/resources/installation/#overview)

## Overview

Link copied

For instructions on how to install the ACF PRO plugin, please see [this guide](https://www.advancedcustomfields.com/resources/how-to-activate/).

The methods outlined below will work on _any_ host. In addition, WordPress sites hosted on WP Engine or Flywheel can use the process outlined [here](https://www.advancedcustomfields.com/resources/installation/#install-acf-wp-engine-flywheel-hosted-websites).

[Link to heading#](https://www.advancedcustomfields.com/resources/installation/#method-1-wp-admin-upload)

## Method 1: wp-admin upload

Link copied

1. Download Advanced Custom Fields from [https://advancedcustomfields.com/latest/](https://advancedcustomfields.com/latest/).
2. Log in to your WP install.
3. From the [Administration Screen](https://wordpress.org/documentation/article/administration-screens/), click on the [Plugin](https://wordpress.org/documentation/article/administration-screens/#plugins-add-functionality-to-your-blog) menu.
4. Under Plugins, click the **Add New Plugin** sub menu.
5. Click **Upload Plugin** at the top of the page.
6. Click **Choose File** and select the file you downloaded earlier.


![The "Add Plugins" screen in WordPress, showing an ACF zip file ready to install. ](https://www.advancedcustomfields.com/wp-content/uploads/2024/10/Install-ACF-Upload-Plugin-Zip.png)

7. Click **Install Now**, and then **Activate Plugin**.


![The installation screen in the WordPress admin, showing that ACF is installed and ready to activate. ](https://www.advancedcustomfields.com/wp-content/uploads/2024/10/Install-ACF-Activate-Plugin.png)

8. After installation, you will find a new menu item, “ACF”.


[Link to heading#](https://www.advancedcustomfields.com/resources/installation/#method-2-ftp)

## Method 2: FTP

Link copied

1. Download the [Advanced Custom Fields plugin](https://advancedcustomfields.com/latest).
2. Upload `advanced-custom-fields` to the `/wp-content/plugins/` directory.
3. Activate the plugin through the “Plugins” menu in WordPress.
4. After installation, you will find a new menu item, “ACF”.

[Link to heading#](https://www.advancedcustomfields.com/resources/installation/#method-3-wp-cli)

## Method 3: WP-CLI

Link copied

1. Open a terminal.
2. Navigate to the root of your WordPress install.
3. Use the `wp plugin` command to install ACF.
4. Activate the plugin via WP-CLI or in the WordPress admin.

Make sure to use the commands to install from a local or remote zip file, rather than installing via the plugin’s slug. Installing via the plugin’s slug will _not_ install ACF.

The command below will download the latest version of ACF from our servers and then activate it on your site. To install a local zip file, replace `https://advancedcustomfields.com/latest/` with the path to your file.

```php
wp plugin install --activate https://advancedcustomfields.com/latest/
```

[Link to heading#](https://www.advancedcustomfields.com/resources/installation/#method-4-composer)

## Method 4: Composer

Link copied

1. Add the ACF repository to your `composer.json` file.



```json
"repositories": [\
       {\
           "type":"composer",\
           "url":"https://composer.advancedcustomfields.com"\
       }\
]
```

2. From the CLI, require ACF using the following command:





```shell-session
composer require wpengine/advanced-custom-fields
```


The steps outlined above will install the free version of ACF with [Composer](https://getcomposer.org/). Please see [Installing ACF With Composer](https://www.advancedcustomfields.com/resources/installing-acf-with-composer/) for more information, including how to use version constraints, installing ACF as a must-use plugin, and customizing install locations.

ACF PRO can also be installed with Composer, as detailed in [Installing ACF PRO with Composer](https://www.advancedcustomfields.com/resources/installing-acf-pro-with-composer/).

[Link to heading#](https://www.advancedcustomfields.com/resources/installation/#install-acf-wp-engine-flywheel-hosted-websites)

## Installing on WP Engine and Flywheel Hosted Websites

Link copied

The above methods will work for all WordPress sites. The following steps will also work for WordPress sites hosted on WP Engine and Flywheel.

1. Log in to your WP install.
2. From the Administration ScreenPanels, click on **the Plugins** Menu.
3. Under Plugins, click the **“Add New Plugin**” sub menu.
4. Search for “Advanced Custom Fields”.
5. Find the Advanced Custom Fields plugin by WP Engine in the search results, and click **Install**.
6. Activate the plugin through the “‘Plugins”’ menu in WordPress.
7. After installation, you will find a new menu item, “ACF”.

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

[Link to heading#](https://www.advancedcustomfields.com/resources/installation/#related)

## Related

Link copied

- Getting Started: [Installing ACF With Composer](https://www.advancedcustomfields.com/resources/installing-acf-with-composer/)
- Guides: [How to Update](https://www.advancedcustomfields.com/resources/how-to-update/)
- Videos: [Installing ACF and ACF PRO](https://www.advancedcustomfields.com/resources/installing-acf-and-acf-pro/)
- Guides: [Upgrade Guide – Version 4](https://www.advancedcustomfields.com/resources/upgrade-guide-version-4/)
- Getting Started: [Installing ACF PRO With Composer](https://www.advancedcustomfields.com/resources/installing-acf-pro-with-composer/)

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

[Got it](https://www.advancedcustomfields.com/resources/installation/#)