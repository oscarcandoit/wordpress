---
url: https://developer.wordpress.org/cli/commands/plugin/
scraped_at: 2025-10-20T03:11:10.145Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/plugin/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp plugin


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)wp plugin

Search

# [wp plugin\  <command>](https://developer.wordpress.org/cli/commands/plugin/)

Manages plugins, including installs, activations, and updates.

## In this article

Table of Contents

- [Examples](https://developer.wordpress.org/cli/commands/plugin/#examples)
- [Subcommands](https://developer.wordpress.org/cli/commands/plugin/#subcommands)

[↑ Back to top](https://developer.wordpress.org/cli/commands/plugin/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/extension-command)

[View Open Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Aplugin+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Aplugin+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/extension-command/issues/new)

See the WordPress [Plugin Handbook](https://developer.wordpress.org/plugins/) developer resource for more information on plugins.

### [Examples](https://developer.wordpress.org/cli/commands/plugin/\#examples)

```
# Activate plugin
$ wp plugin activate hello
Plugin 'hello' activated.
Success: Activated 1 of 1 plugins.

# Deactivate plugin
$ wp plugin deactivate hello
Plugin 'hello' deactivated.
Success: Deactivated 1 of 1 plugins.

# Delete plugin
$ wp plugin delete hello
Deleted 'hello' plugin.
Success: Deleted 1 of 1 plugins.

# Install the latest version from wordpress.org and activate
$ wp plugin install bbpress --activate
Installing bbPress (2.5.9)
Downloading install package from https://downloads.wordpress.org/plugin/bbpress.2.5.9.zip...
Using cached file '/home/vagrant/.wp-cli/cache/plugin/bbpress-2.5.9.zip'...
Unpacking the package...
Installing the plugin...
Plugin installed successfully.
Activating 'bbpress'...
Plugin 'bbpress' activated.
Success: Installed 1 of 1 plugins.

```

### [Subcommands](https://developer.wordpress.org/cli/commands/plugin/\#subcommands)

| Name | Description |
| --- | --- |
| [wp plugin activate](https://developer.wordpress.org/cli/commands/plugin/activate/) | Activates one or more plugins. |
| [wp plugin auto-updates](https://developer.wordpress.org/cli/commands/plugin/auto-updates/) | Manages plugin auto-updates. |
| [wp plugin deactivate](https://developer.wordpress.org/cli/commands/plugin/deactivate/) | Deactivates one or more plugins. |
| [wp plugin delete](https://developer.wordpress.org/cli/commands/plugin/delete/) | Deletes plugin files without deactivating or uninstalling. |
| [wp plugin get](https://developer.wordpress.org/cli/commands/plugin/get/) | Gets details about an installed plugin. |
| [wp plugin install](https://developer.wordpress.org/cli/commands/plugin/install/) | Installs one or more plugins. |
| [wp plugin is-active](https://developer.wordpress.org/cli/commands/plugin/is-active/) | Checks if a given plugin is active. |
| [wp plugin is-installed](https://developer.wordpress.org/cli/commands/plugin/is-installed/) | Checks if a given plugin is installed. |
| [wp plugin list](https://developer.wordpress.org/cli/commands/plugin/list/) | Gets a list of plugins. |
| [wp plugin path](https://developer.wordpress.org/cli/commands/plugin/path/) | Gets the path to a plugin or to the plugin directory. |
| [wp plugin search](https://developer.wordpress.org/cli/commands/plugin/search/) | Searches the WordPress.org plugin directory. |
| [wp plugin status](https://developer.wordpress.org/cli/commands/plugin/status/) | Reveals the status of one or all plugins. |
| [wp plugin toggle](https://developer.wordpress.org/cli/commands/plugin/toggle/) | Toggles a plugin’s activation state. |
| [wp plugin uninstall](https://developer.wordpress.org/cli/commands/plugin/uninstall/) | Uninstalls one or more plugins. |
| [wp plugin update](https://developer.wordpress.org/cli/commands/plugin/update/) | Updates one or more plugins. |
| [wp plugin verify-checksums](https://developer.wordpress.org/cli/commands/plugin/verify-checksums/) | Verifies plugin files against WordPress.org’s checksums. |

_Command documentation is regenerated at every release. To add or update an example, please submit a pull request against the corresponding part of the codebase._

Notifications