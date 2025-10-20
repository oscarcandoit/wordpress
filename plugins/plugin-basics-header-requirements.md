---
url: https://developer.wordpress.org/plugins/plugin-basics/header-requirements
scraped_at: 2025-10-20T03:35:56.529Z
retry_attempt: 1
---

[Skip to content](https://developer.wordpress.org/plugins/plugin-basics/header-requirements/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Header Requirements


[Home](https://developer.wordpress.org/)[Plugin Handbook](https://developer.wordpress.org/plugins/)[Plugin Basics](https://developer.wordpress.org/plugins/plugin-basics/)Header Requirements

Search

# Header Requirements

## In this article

Table of Contents

- [Minimum Fields](https://developer.wordpress.org/plugins/plugin-basics/header-requirements/#minimum-fields)
- [Header Fields](https://developer.wordpress.org/plugins/plugin-basics/header-requirements/#header-fields)
- [Notes](https://developer.wordpress.org/plugins/plugin-basics/header-requirements/#notes)

[↑ Back to top](https://developer.wordpress.org/plugins/plugin-basics/header-requirements/#wp--skip-link--target)

As described in [Getting Started](https://developer.wordpress.org/plugins/plugin-basics/#getting-started), the main PHP file should include header comment what tells WordPress that a file is a plugin and provides information about the plugin.

## [Minimum Fields](https://developer.wordpress.org/plugins/plugin-basics/header-requirements/\#minimum-fields)

At a minimum, a header comment must contain the Plugin Name:

``
[Copy](https://developer.wordpress.org/plugins/plugin-basics/header-requirements/#)

```php
/*
 * Plugin Name: YOUR PLUGIN NAME
 */
```

## [Header Fields](https://developer.wordpress.org/plugins/plugin-basics/header-requirements/\#header-fields)

Available header fields:

- **Plugin Name:** ( _required_) The name of your plugin, which will be displayed in the Plugins list in the WordPress Admin.
- **Plugin URI:** The home page of the plugin, which should be a unique URL, preferably on your own website. This _must be unique_ to your plugin. You cannot use a WordPress.org URL here.
- **Description:** A short description of the plugin, as displayed in the Plugins section in the WordPress Admin. Keep this description to fewer than 140 characters.
- **Version:** The current version number of the plugin, such as 1.0 or 1.0.3.
- **Requires at least:** The lowest WordPress version that the plugin will work on.
- **Requires PHP:** The minimum required PHP version.
- **Author:** The name of the plugin author. Multiple authors may be listed using commas.
- **Author URI:** The author’s website or profile on another website, such as WordPress.org.
- **License:** The short name (slug) of the plugin’s license (e.g. GPLv2). More information about licensing can be found in the [WordPress.org guidelines](https://developer.wordpress.org/plugins/wordpress-org/detailed-plugin-guidelines/#1-plugins-must-be-compatible-with-the-gnu-general-public-license).
- **License URI:** A link to the full text of the license (e.g. [https://www.gnu.org/licenses/gpl-2.0.html](https://www.gnu.org/licenses/gpl-2.0.html)).
- **Text Domain:** The [gettext](https://www.gnu.org/software/gettext/) text domain of the plugin. More information can be found in the [Text Domain](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/#text-domains) section of the [How to Internationalize your Plugin](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/) page.
- **Domain Path:** The domain path lets WordPress know where to find the translations. More information can be found in the [Domain Path](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/#domain-path) section of the [How to Internationalize your Plugin](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/) page.
- **Network:** Whether the plugin can only be activated network-wide. Can only be set to _true_, and should be left out when not needed.
- **Update URI:** Allows third-party plugins to avoid accidentally being overwritten with an update of a plugin of a similar name from the WordPress.org Plugin Directory. For more info read related [dev note](https://make.wordpress.org/core/2021/06/29/introducing-update-uri-plugin-header-in-wordpress-5-8/).
- **Requires Plugins**: A comma-separated list of WordPress.org-formatted slugs for its dependencies, such as `my-plugin` ( `my-plugin/my-plugin.php` is not supported). It does not support commas in plugin slugs. For more info read the related [dev note](https://make.wordpress.org/core/2024/03/05/introducing-plugin-dependencies-in-wordpress-6-5/).

A valid PHP file with a header comment might look like this:

``
[Expand code](https://developer.wordpress.org/plugins/plugin-basics/header-requirements/#)

[Copy](https://developer.wordpress.org/plugins/plugin-basics/header-requirements/#)

```php
/*
 * Plugin Name:       My Basics Plugin
 * Plugin URI:        https://example.com/plugins/the-basics/
 * Description:       Handle the basics with this plugin.
 * Version:           1.10.3
 * Requires at least: 5.2
 * Requires PHP:      7.2
 * Author:            John Smith
 * Author URI:        https://author.example.com/
 * License:           GPL v2 or later
 * License URI:       https://www.gnu.org/licenses/gpl-2.0.html
 * Update URI:        https://example.com/my-plugin/
 * Text Domain:       my-basics-plugin
 * Domain Path:       /languages
 * Requires Plugins:  my-plugin, yet-another-plugin
 */
```

Here’s another example which allows file-level PHPDoc DocBlock as well as WordPress plugin file headers:

``
[Expand code](https://developer.wordpress.org/plugins/plugin-basics/header-requirements/#)

[Copy](https://developer.wordpress.org/plugins/plugin-basics/header-requirements/#)

```php
/**
 * Plugin Name
 *
 * @package           PluginPackage
 * @author            Your Name
 * @copyright         2019 Your Name or Company Name
 * @license           GPL-2.0-or-later
 *
 * @wordpress-plugin
 * Plugin Name:       Plugin Name
 * Plugin URI:        https://example.com/plugin-name
 * Description:       Description of the plugin.
 * Version:           1.0.0
 * Requires at least: 5.2
 * Requires PHP:      7.2
 * Author:            Your Name
 * Author URI:        https://example.com
 * Text Domain:       plugin-slug
 * License:           GPL v2 or later
 * License URI:       http://www.gnu.org/licenses/gpl-2.0.txt
 * Update URI:        https://example.com/my-plugin/
 * Requires Plugins:  my-plugin, yet-another-plugin
 */
```

## [Notes](https://developer.wordpress.org/plugins/plugin-basics/header-requirements/\#notes)

When assigning a version number to your project, keep in mind that WordPress uses the PHP version\_compare() function to compare plugin version numbers. Therefore, before you release a new version of your plugin, you should make sure that this PHP function considers the new version to be “greater” than the old one. For example, 1.02 is actually greater than 1.1.

First published

September 16, 2014

Last updated

May 8, 2024

[PreviousPlugin BasicsPrevious: Plugin Basics](https://developer.wordpress.org/plugins/plugin-basics/)

[NextActivation / Deactivation HooksNext: Activation / Deactivation Hooks](https://developer.wordpress.org/plugins/plugin-basics/activation-deactivation-hooks/)

Notifications